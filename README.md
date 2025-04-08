
## Validating sudospawner configured correctly

https://jupyterhub.readthedocs.io/en/stable/howto/configuration/config-sudo.html

### test sudo setup
Passes
```sh
sudo -u ubuntu sudo -n -u $USER /opt/jupyterhub/bin/sudospawner --help
```

```sh
sudo -u ubuntu sudo -n -u $USER echo 'fail'
sudo: a password is required
```

## Test that PAM works

```shell
 sudo -u ubuntu /opt/jupyterhub/bin/python3 -c "import pamela, getpass; print(pamela.authenticate('$USER', getpass.getpass()))"
Password:
None
```

wrong password leads to 

`pamela.PAMError: [PAM Error 7] Authentication failure`
