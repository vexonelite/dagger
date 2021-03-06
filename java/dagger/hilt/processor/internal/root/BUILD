# Copyright (C) 2020 The Dagger Authors.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
# http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.

# Description:
#   Annotation processor for Hilt.

package(default_visibility = ["//:src"])

java_plugin(
    name = "plugin",
    generates_api = 1,
    processor_class = "dagger.hilt.processor.internal.root.RootProcessor",
    deps = [
        ":processor_lib",
    ],
)

java_library(
    name = "processor_lib",
    srcs = [
        "RootFileFormatter.java",
        "RootGenerator.java",
        "RootProcessor.java",
        "TestComponentDataGenerator.java",
        "TestComponentDataSupplierGenerator.java",
        "TestInjectorGenerator.java",
    ],
    deps = [
        ":root_metadata",
        ":root_type",
        "//java/dagger/hilt/processor/internal:base_processor",
        "//java/dagger/hilt/processor/internal:classnames",
        "//java/dagger/hilt/processor/internal:component_descriptor",
        "//java/dagger/hilt/processor/internal:component_names",
        "//java/dagger/hilt/processor/internal:processor_errors",
        "//java/dagger/hilt/processor/internal:processors",
        "//java/dagger/hilt/processor/internal/aggregateddeps:component_dependencies",
        "//java/dagger/hilt/processor/internal/definecomponent:define_components",
        "//java/dagger/hilt/processor/internal/generatesrootinput:generates_root_inputs",
        "//java/dagger/internal/codegen/extension",
        "//java/dagger/internal/guava:base",
        "//java/dagger/internal/guava:collect",
        "@google_bazel_common//third_party/java/auto:common",
        "@google_bazel_common//third_party/java/auto:service",
        "@google_bazel_common//third_party/java/incap",
        "@google_bazel_common//third_party/java/javapoet",
    ],
)

java_library(
    name = "root_metadata",
    srcs = [
        "Root.java",
        "RootMetadata.java",
        "TestRootMetadata.java",
    ],
    deps = [
        ":root_type",
        "//java/dagger/hilt/processor/internal:classnames",
        "//java/dagger/hilt/processor/internal:component_descriptor",
        "//java/dagger/hilt/processor/internal:processor_errors",
        "//java/dagger/hilt/processor/internal:processors",
        "//java/dagger/hilt/processor/internal/aggregateddeps:component_dependencies",
        "//java/dagger/hilt/processor/internal/aliasof:alias_ofs",
        "//java/dagger/internal/codegen/extension",
        "//java/dagger/internal/guava:base",
        "//java/dagger/internal/guava:collect",
        "@google_bazel_common//third_party/java/auto:common",
        "@google_bazel_common//third_party/java/auto:value",
        "@google_bazel_common//third_party/java/javapoet",
    ],
)

java_library(
    name = "root_type",
    srcs = ["RootType.java"],
    deps = [
        "//java/dagger/hilt/processor/internal:classnames",
        "//java/dagger/hilt/processor/internal:processor_errors",
        "//java/dagger/hilt/processor/internal:processors",
        "@google_bazel_common//third_party/java/javapoet",
    ],
)

filegroup(
    name = "srcs_filegroup",
    srcs = glob(["*"]),
)
