# Copyright 2018 The Bazel Authors. All rights reserved.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#    http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.
load("@io_bazel_rules_kotlin//kotlin:js.bzl", "kt_js_library")
load("@build_bazel_rules_nodejs//:index.bzl", "nodejs_binary")

kt_js_library(
    name = "app",
    srcs = ["Main.kt"],
    visibility = ["//visibility:public"],
    deps = [
        "//:kotlinx-coroutines-core",
    ],
)

nodejs_binary(
    name = "coroutines-helloworld",
    data = [":app"],
    entry_point = ":app.js",
    node_modules = "@node_ws//:node_modules",
    visibility = ["//visibility:public"],
)
