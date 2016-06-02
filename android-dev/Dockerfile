FROM fourgeo/android-sdk:latest

MAINTAINER Ivan Fastov "c0d3r85@gmail.com"

ENV ANDROID_NDK_HOME /opt/android-ndk
ENV ANDROID_NDK_VERSION r10e
# RUN apt-get update
RUN wget -q http://dl.google.com/android/ndk/android-ndk-$ANDROID_NDK_VERSION-linux-x86_64.bin --output-document=/tmp/android-ndk.bin && chmod a+x /tmp/android-ndk.bin
RUN apt-get install build-essential -y --force-yes

RUN cd /tmp && \
  /tmp/android-ndk.bin && \
  mv /tmp/android-ndk-$ANDROID_NDK_VERSION /opt/android-ndk && \
  rm -rf /tmp/android-ndk*

ENV PATH ${PATH}:${ANDROID_NDK_HOME}
RUN apt-get clean
WORKDIR /opt/workspace
