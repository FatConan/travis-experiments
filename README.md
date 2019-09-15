# travis-experiments

## Just messsin' 

The repo is just a quick test to try out techniques for authenticating to a third party server for the purposes of performing basic deployment actions such as rsyncing the built item to a remote location.

For my purposes I've found the following basic technique works:

Encrypt a key for accessing the remote server and add it to the `.travis.yml`
``` travis encrypt-file depoly_key --add ```
This will add the key decryption command to the travis script
I've found that the file permissions aren't preserved when doing this and so to use the key I've found I have to lock down the extracted file afterwards
``` chmod 400 deploy_key ```
