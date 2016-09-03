FROM openjdk:8

# Install the tools needed for the installation
RUN apt-get update && \
    apt-get install -y wget

# Download the SDK
RUN cd /opt && \
    wget https://dl.google.com/android/android-sdk_r24.4.1-linux.tgz && \
    tar -xzf android-sdk_r24.4.1-linux.tgz

ENV ANDROID_HOME=/opt/android-sdk-linux
ENV PATH ${PATH}:${ANDROID_HOME}/tools:${ANDROID_HOME}/platform-tools
ENV ANDROID_BUILD_TOOLS_VERSION=24.0.2
ENV ANDROID_API="android-24"

RUN echo y | android update sdk -a -u -t platform-tools,${ANDROID_API},build-tools-${ANDROID_BUILD_TOOLS_VERSION} && \
    chmod a+x  -R $ANDROID_HOME && \
    chown -R root:root $ANDROID_HOME 

