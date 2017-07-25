# Binder Repository with Secrets

This repository uses a convention of defining an encrypted .env file `secrets.encrypted.env` in the `$REPO_DIR` which is decrypted by the JupyterHub (BinderHub) that consumes the image, and mounts the result.

The public AGE key (see `age.public.txt`) can be used to encrypt this environment with
```shell
sops encrypt --age "$(cat age.public.txt)" secret.env --output secret.encrypted.env
```
