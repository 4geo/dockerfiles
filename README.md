# Prepare Ionic for Android build
```bash
docker pull fourgeo/ionic-android
docker run --tty --interactive  --volume=`pwd`:/opt/workspace/  fourgeo/ionic-android /bin/bash
```
# Prepare ppm for Android
Get the [Dockerfile](https://raw.githubusercontent.com/c0d3r85/dockerfiles/master/ppm-prepare-android/Dockerfile)
cd to Dockerfile location
```bash
docker build -t fourgeo-ppm-android --rm=true --force-rm=true --build-arg uid=`id -u` --build-arg gid=`id -g` .
docker run --tty --volume="${HOME}/projects/4geo.world/cordova/iWorld":/home/developer/project fourgeo-ppm-android
docker run --tty --interactive --volume="${HOME}/projects/4geo.world/cordova/iWorld":/home/developer/project fourgeo-ppm-android /bin/bash
```
Then you should be able to build apk (gulp && ionic prepare android && ionic build android --debug)
