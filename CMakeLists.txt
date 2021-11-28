cmake_minimum_required(VERSION 3.20)
project(drivedownloader)

include(ExternalProject)
include(FetchContent)

set(OPENSSL_PREFIX ${CMAKE_CURRENT_BINARY_DIR}/openssl-prefix)
set(ENV{OPENSSL_ROOT_DIR} ${OPENSSL_PREFIX})

ExternalProject_Add(
        openssl
        URL https://www.openssl.org/source/openssl-3.0.0.tar.gz
        URL_HASH SHA1=3be896f1b33bc01af874ccca701a6f700af9de20
        CONFIGURE_COMMAND   ${OPENSSL_PREFIX}/src/openssl/config --prefix=${OPENSSL_PREFIX}
        INSTALL_COMMAND     make install
        COMMAND             ln -s ${OPENSSL_PREFIX}/lib64 ${OPENSSL_PREFIX}/lib
)

set(LIBCURL_PREFIX ${CMAKE_CURRENT_BINARY_DIR}/libcurl-prefix)

ExternalProject_Add(
        libcurl
        GIT_REPOSITORY https://github.com/curl/curl.git
        GIT_TAG        curl-7_80_0
        CMAKE_ARGS     -D CMAKE_INSTALL_PREFIX=${LIBCURL_PREFIX}
        DEPENDS        openssl
)

set(CMAKE_CXX_STANDARD 20)


add_executable(drivedownloader main.cpp)
add_dependencies(drivedownloader libcurl)
