
############ Python pre-amble
load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive", "http_file")

# Update the SHA and PYTHON_VERSION to the lastest version available here:
# https://github.com/bazelbuild/rules_python/releases.

SHA="84aec9e21cc56fbc7f1335035a71c850d1b9b5cc6ff497306f84cced9a769841"

PYTHON_VERSION="0.23.1"

http_archive(
    name = "rules_python",
    sha256 = SHA,
    strip_prefix = "rules_python-{}".format(PYTHON_VERSION),
    url = "https://github.com/bazelbuild/rules_python/releases/download/{0}/rules_python-{0}.tar.gz".format(PYTHON_VERSION),
)

load("@rules_python//python:repositories.bzl", "py_repositories", "python_register_toolchains")

py_repositories()

python_register_toolchains(
    name = "python_3_11",
    python_version = "3.11",
)

load("@python_3_11//:defs.bzl", "interpreter")

load("@rules_python//python:pip.bzl", "pip_parse")

pip_parse(
    python_interpreter_target = interpreter,
)

### Ruff

RUFF_VERSION = "0.3.5"

# https://github.com/bazelbuild/bazel/issues/20269
http_file(
    name = "ruff-osx-tar",
    sha256 = "75522512ed44a554968483e205f3c7260b7e05c90462a9edf69c8f0d737ddf1d",
    urls = ["https://github.com/astral-sh/ruff/releases/download/v{0}/ruff-{0}-aarch64-apple-darwin.tar.gz".format(RUFF_VERSION)],
)

http_archive(
    name = "ruff-linux",
    build_file_content = 'exports_files(["ruff"])',
    sha256 = "4326f4121b7fb2f4adbffcc6d07a595f5869a95b70793b70c16951715dc601de",
    urls = ["https://github.com/astral-sh/ruff/releases/download/v{0}/ruff-{0}-x86_64-unknown-linux-gnu.tar.gz".format(RUFF_VERSION)],
)
