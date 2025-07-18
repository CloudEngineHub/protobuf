# Copyright (c) 2009-2021, Google LLC
# All rights reserved.
#
# Use of this source code is governed by a BSD-style
# license that can be found in the LICENSE file or at
# https://developers.google.com/open-source/licenses/bsd

load("@rules_cc//cc:cc_library.bzl", "cc_library")
load("@rules_cc//cc:cc_test.bzl", "cc_test")
load("//upb/bazel:build_defs.bzl", "UPB_DEFAULT_COPTS")

package(default_applicable_licenses = ["//:license"])

cc_library(
    name = "base",
    srcs = [
        "status.c",
    ],
    hdrs = [
        "descriptor_constants.h",
        "status.h",
        "status.hpp",
        "string_view.h",
        "upcast.h",
    ],
    copts = UPB_DEFAULT_COPTS,
    visibility = ["//visibility:public"],
    deps = [
        "//upb/port",
    ],
)

cc_library(
    name = "internal",
    hdrs = [
        "internal/endian.h",
        "internal/log2.h",
    ],
    copts = UPB_DEFAULT_COPTS,
    visibility = ["//visibility:public"],
    deps = ["//upb/port"],
)

cc_test(
    name = "string_view_test",
    srcs = ["string_view_test.cc"],
    deps = [
        ":base",
        "@googletest//:gtest",
        "@googletest//:gtest_main",
    ],
)

filegroup(
    name = "source_files",
    srcs = glob(
        [
            "**/*.c",
            "**/*.h",
            "**/*.hpp",
        ],
    ),
    visibility = [
        "//python/dist:__pkg__",
        "//upb/cmake:__pkg__",
    ],
)
