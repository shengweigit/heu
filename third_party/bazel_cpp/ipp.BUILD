# Copyright 2022 Ant Group Co., Ltd.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#   http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.

load("@yacl//bazel:yacl.bzl", "yacl_cmake_external")

package(default_visibility = ["//visibility:public"])

filegroup(
    name = "all_srcs",
    srcs = glob(["**"]),
)

yacl_cmake_external(
    name = "ipp",
    cache_entries = {
        "ARCH": "intel64",
        "OPENSSL_INCLUDE_DIR": "$EXT_BUILD_DEPS/openssl/include",
        "OPENSSL_LIBRARIES": "$EXT_BUILD_DEPS/openssl/lib",
        "OPENSSL_ROOT_DIR": "$EXT_BUILD_DEPS/openssl",
        "CMAKE_BUILD_TYPE": "Release",
    },
    lib_source = ":all_srcs",
    out_static_libs = [
        "intel64/libippcp.a",
        "intel64/libcrypto_mb.a",
    ],
    deps = [
        "@com_github_openssl_openssl//:openssl",
    ],
)
