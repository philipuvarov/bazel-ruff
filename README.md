# bazel-ruff

An example to support the [blogpost](https://philuvarov.io/bazel-can-be-ruff/) on how to configure
Ruff with Bazel.

Interesting parts of the configuration are located in the [WORKSPACE](https://github.com/philipuvarov/bazel-ruff/blob/main/WORKSPACE#L36) and [tools/BUILD.bazel](https://github.com/philipuvarov/bazel-ruff/blob/main/tools/BUILD.bazel) files.


## Running Ruff

**Lint and fix:**

```shell
bazel run //tools:ruff -- check --fix
```

**Format:**
```shell
baze run //tools:ruff -- format
```
