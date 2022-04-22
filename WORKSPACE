# -*- python -*-

# Copyright 2018-2020 Josh Pieper, jjp@pobox.com.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#     http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.

workspace(name = "com_github_mjbots_rules_mbed")

BAZEL_VERSION = "3.4.1"
BAZEL_VERSION_SHA = "1a64c807716e10c872f1618852d95f4893d81667fe6e691ef696489103c9b460"

load("//:rules.bzl", "mbed_register")
load("//tools/workspace/mbed:repository.bzl", "mbed_repository")

mbed_register()

mbed_repository(
    name = "com_github_ARMmbed_mbed-os_g474",
    target = "targets/TARGET_STM/TARGET_STM32G4/TARGET_STM32G474xE/TARGET_NUCLEO_G474RE",
    config = {
        "MBED_CONF_RTOS_PRESENT": "0",
        "DEVICE_STDIO_MESSAGES": "0",
        "MBED_CONF_TARGET_CONSOLE_UART": "1",
    },
)

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

RULES_MBED_COMMIT = "master"

http_archive(
    name = "rules_mbed",
    url = "https://github.com/mjbots/bazel_deps/archive/{}.zip".format(RULES_MBED_COMMIT),
    sha256 = "9e234ffe6ff6c64ed33fd77d82a27bc0f4fb782f4818b7a45730f2d4709ab054",
    strip_prefix = "rules_mbed-{}".format(RULES_MBED_COMMIT),
)

load("@rules_mbed//:rules.bzl", "mbed_register")
mbed_register(config = {
    "mbed_target": "targets/TARGET_STM/TARGET_STM32F4/TARGET_STM32F411xE/TARGET_NUCLEO_F411RE",
    "mbed_config": None,
  }
)