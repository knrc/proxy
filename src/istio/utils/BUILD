# Copyright 2018 Istio Authors. All Rights Reserved.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#     http://www.apache.org/licenses/LICENSE-2.0

# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.

licenses(["notice"])

cc_library(
    name = "utils_lib",
    srcs = [
        "local_attributes.cc",
        "logger.cc",
        "protobuf.cc",
        "status.cc",
        "utils.cc"
    ],
    hdrs = [
        "logger.h",
        "utils.h",
    ],
    visibility = ["//visibility:public"],
    deps = [
        ":attribute_names_lib",
        "//external:protobuf",
        "//include/istio/utils:headers_lib",
        "//include/istio/utils:attribute_names_header",
        "//external:mixer_client_config_cc_proto",
    ],
)

cc_test(
    name = "utils_test",
    size = "small",
    srcs = ["utils_test.cc"],
    deps = [
        ":utils_lib",
        "//external:googletest_main",
    ],
)

cc_test(
    name = "simple_lru_cache_test",
    size = "small",
    srcs = ["simple_lru_cache_test.cc"],
    linkopts = [
        "-lm",
        "-lpthread",
    ],
    linkstatic = 1,
    deps = [
        "//external:googletest_main",
        "//include/istio/utils:simple_lru_cache",
    ],
)

cc_test(
    name = "logger_test",
    size = "small",
    srcs = ["logger_test.cc"],
    deps = [
        ":utils_lib",
        "//external:googletest_main",
    ],
)

cc_library(
    name = "attribute_names_lib",
    srcs = [
        "attribute_names.cc",
    ],
    visibility = ["//visibility:public"],
    deps = [
        "//include/istio/utils:attribute_names_header",
    ],
)
