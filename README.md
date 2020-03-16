# ftp-action

Automate copying your files via ftp using this GitHub action.

## Example usage

```
name: Deploy via ftp
on: push
jobs:
  deploy:
    name: Deploy
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@master
    - name: Upload ftp
      uses: sebastianpopp/ftp-action@releases/v1
      with:
        host: ${{ secrets.FTP_SERVER }}
        user: ${{ secrets.FTP_USERNAME }}
        password: ${{ secrets.FTP_PASSWORD }}
        forceSsl: true
        localDir: "dist"
        remoteDir: "www"
```

## Input parameters

Input parameter | Description | Required | Default
--- | --- | --- | ---
host | FTP server name | Yes | N/A
user | FTP username | Yes | N/A
password | FTP password | Yes | N/A
forceSsl | Force SSL encryption | No | false
localDir | The local directory to copy | No | .
remoteDir | The remote directory to copy to | No | .
