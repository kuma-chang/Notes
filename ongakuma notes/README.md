# ongakuma notes

- [ongakuma notes](#ongakuma-notes)
  - [venv](#venv)
  - [nvm npm](#nvm-npm)
  - [VS Code extensions](#vs-code-extensions)
  - [Set up Django](#set-up-django)
  - [Add model to database](#add-model-to-database)
  - [Add API view](#add-api-view)

## venv

- Set up venv

  ``` bash
  python3 -m venv tutorial-env
  ```

- Start up venv

  ```bash
  source tutorial-evn/bin/activate
  ```

- Exit venv

  ```bash
  deactivate
  ```

- export requirements

  ```bash
  pip freeze > requirements.txt
  ```

- install requirements.txt

  ```bash
  pip install -r requirements.txt
  ```

## nvm npm

- install nvm
  - run

    ```bash
    curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
    ```
  
  - make sure `~/.zshrc` has the following lines

    ```bash
    export NVM_DIR="$HOME/.nvm"
    [ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
    [ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion
    ```

- install npm/node
  - list remote available versions of node

    ```bash
    nvm ls-remote
    ```

  - install specific version of node

    ```bash
    nvm install 20.11.1
    ```

## VS Code extensions

- Prettier
- Python
- Django
- React(ES7+ React/Redux/React-Native snippets)
- JavaScript(JavaScript (ES6) code snippets)

## Set up Django

- Install Django

  ```bash
  pip install django djangorestframework
  ```

- Start project and app

  ```bash
  django-admin startproject music_controller
  django-admin startapp api
  ```

- link new app to project
  - in `music_controller/settings.py/INSTALLED_APPS` add the following

    ```python
    'api.apps.ApiConfig',
    'rest_framework'
    ```

- update the database

  ```bash
  python ./manage.py makemigrations
  python ./manage.py migrate
  ```

- run server

  ```bash
  python ./manage.py runserver
  ```

- set up new view
  - `project/urls.py/urlpatterns` add `path('', include('app.urls'))`
  - `app/urls.py` add route points to endpoint func in `app/views.py`
  - `app/views.py` add endpoint func

## Add model to database

- Add model class in `app/models.py`

  ```python
  class Room(models.Model):
    code = models.CharField(max_length=8, default="", unique=True)
    host = models.CharField(max_length=50, unique=True)
    guest_can_pause = models.BooleanField(null=False, default=False)
    votes_to_skip = models.IntegerField(null=False, default=1)
    created_at = models.DateTimeField(auto_now_add=True)
  ```

## Add API view

- Add  model serializer in `app/serializers.py`

  ```python
  class RoomSerializer(serializers.ModelSerializer):
    class Meta:
        model = Room
        fields = ('id', 'code', 'host', 'guest_can_pause',
                  'votes_to_skip', 'created_at')
  ```

- Add view in `app/views.py`
  - CreateAPIView: with create ui
  - ListAPIView: view only

  ```python
  class RoomView (generics.CreateAPIView):
    queryset = Room.objects.all()
    serializer_class = RoomSerializer
  ```

- link view to url in `api/urls.py`

  ```python
  urlpatterns = [
    path('', RoomView.as_view()),
  ]
  ```
