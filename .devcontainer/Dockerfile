FROM mcr.microsoft.com/devcontainers/cpp:ubuntu

RUN apt-get update && \
    apt-get install -y --no-install-recommends \
        curl bison ninja-build \
        libsqlite3-dev libboost-all-dev doxygen graphviz \
        git-lfs \
    && apt-get clean && rm -rf /var/lib/apt/lists/*

# Cap'n Protoのソースをダウンロード・ビルド・インストール
RUN wget https://capnproto.org/capnproto-c++-1.2.0.tar.gz && \
    tar -xzf capnproto-c++-1.2.0.tar.gz && \
    cd capnproto-c++-1.2.0 && \
    ./configure && make -j$(nproc) && make install && cd .. && \
    rm -rf capnproto-c++-1.2.0 capnproto-c++-1.2.0.tar.gz

# Cap'n ProtoのCMake設定パス環境変数の設定
ENV CapnProto_DIR=/usr/local/lib/cmake/CapnProto
