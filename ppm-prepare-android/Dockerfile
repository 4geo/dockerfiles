FROM fourgeo/ionic-android:latest

MAINTAINER Ivan Fastov "c0d3r85@gmail.com"
ENV HOME=/home/developer PLATFORM=android ANDROID_HOME=/opt/android-sdk-linux
RUN chmod 755 "${ANDROID_HOME}/tools/android"
ARG uid=0
ARG gid=0
RUN groupadd -g $gid developer
RUN useradd -u $uid -g $gid -m developer
USER developer
WORKDIR $HOME/project
CMD npm install && \
    gulp checkout --name 'personal-pages-mobile' && \
    rm -rf ./platforms && \
    rm -rf ./plugins && \
    rm -rf ./hooks && \
    rm -rf www/resources/map && \
    sed -i 's/^[[:space:]]*"phonegap-plugin-push",//' package.json && \
    ./bootstrap-personal-page-mobile.sh && \
    ionic state reset && \
    ionic platform add android@4.1.1 && \
    cp patches/android/build-extras.gradle platforms/android/
