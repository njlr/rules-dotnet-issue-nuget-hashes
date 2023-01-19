load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

# http_archive(
#   name = "bazel_skylib",
#   urls = [
#     "https://mirror.bazel.build/github.com/bazelbuild/bazel-skylib/releases/download/1.2.1/bazel-skylib-1.2.1.tar.gz",
#     "https://github.com/bazelbuild/bazel-skylib/releases/download/1.2.1/bazel-skylib-1.2.1.tar.gz",
#   ],
#   sha256 = "f7be3474d42aae265405a592bb7da8e171919d74c16f082a5457840f06054728",
# )

# load("@bazel_skylib//:workspace.bzl", "bazel_skylib_workspace")

# bazel_skylib_workspace()

http_archive(
    name = "rules_dotnet",
    sha256 = "c2d20df062fa34fdc7103d54ae44a2e3d715e2728c1fc21f7df450061ffb7726",
    strip_prefix = "rules_dotnet-0.8.4",
    url = "https://github.com/bazelbuild/rules_dotnet/archive/refs/tags/v0.8.4.tar.gz",
)

load(
  "@rules_dotnet//dotnet:repositories.bzl",
  "dotnet_register_toolchains",
  "rules_dotnet_dependencies",
)

rules_dotnet_dependencies()

dotnet_register_toolchains("dotnet", "6.0.300")

load("@rules_dotnet//dotnet:rules_dotnet_nuget_packages.bzl", "rules_dotnet_nuget_packages")

rules_dotnet_nuget_packages()

load("@rules_dotnet//dotnet:paket2bazel_dependencies.bzl", "paket2bazel_dependencies")

paket2bazel_dependencies()

load("//deps:paket.bzl", "paket")

paket()
