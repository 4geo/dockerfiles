# Prepare Ionic for Android build
```bash
docker pull fourgeo/ionic-android
docker run --tty --interactive  --user=`id -u`:`id -g` --volume=`pwd`:/opt/workspace/  fourgeo/ionic-android /bin/bash
```
