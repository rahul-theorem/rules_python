load("@aspect_bazel_lib//lib:write_source_files.bzl", "write_source_files")
load("@rules_python//python:pip.bzl", "compile_pip_requirements")

# This rule adds a convenient way to update the requirements.txt
# lockfile based on the requirements.in.
compile_pip_requirements(name = "requirements")

# Similarly ensures that the requirements.bzl file is updated
# based on the requirements.txt lockfile.
write_source_files(
    name = "vendor_requirements",
    files = {
        "requirements.bzl": "@pip_parsed//:requirements.bzl",
    },
)

