# ongakuma notes

- [ongakuma notes](#ongakuma-notes)
  - [venv](#venv)
  - [nvm npm](#nvm-npm)

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

  - list remote available versions of node

    ```bash
    nvm ls-remote
    ```

  - install specific version of node

    ```bash
    nvm install 20.11.1
    ```
