1、pull docker代码
2、从docker hub拉取包含所有开发环境的docker镜像：docker pull dockercore/docker
3、运行并进入开发容器：docker run --rm -i --privileged -e BUILDFLAGS -e KEEPBUNDLE -e DOCKER_BUILD_GOGC -e DOCKER_BUILD_PKGS -e DOCKER_CLIENTONLY -e DOCKER_DEBUG -e DOCKER_EXPERIMENTAL -e DOCKER_GITCOMMIT -e DOCKER_GRAPHDRIVER=devicemapper -e DOCKER_INCREMENTAL_BINARY -e DOCKER_REMAP_ROOT -e DOCKER_STORAGE_OPTS -e DOCKER_USERLANDPROXY -e TESTDIRS -e TESTFLAGS -e TIMEOUT -v "/home/wangkun/code/docker/bundles:/go/src/github.com/docker/docker/bundles" -t "dockercore/docker:latest" bash
4、编译源码：DOCKER_GITCOMMIT=3385658 ./hack/make.sh binary
5、复制bundles文件夹下docker相关的二进制文件到/usr/bin下
6、systemctl restart docker
