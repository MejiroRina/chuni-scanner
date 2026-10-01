# chuni scanner

**chuni scanner** is a companion project for [HarukiBot](https://github.com/Team-Haruki), it can scan all the chunithm music data and upsert to MySQL.

## Requirements
+ `Python >= 3.12`

## CI and releases

The workflows are thin callers of the shared templates in
[seiunx-dev/ci-templates](https://github.com/seiunx-dev/ci-templates) (`@v1`). Reuse the
templates first; customize in the caller only when they genuinely cannot meet a need,
with a comment saying why.

- `ci.yml`: ruff check + format check, `compileall`, and the sdist/wheel build on every
  PR and main push. The single required check is `CI OK`.
- `release.yml`: bump `version` in `pyproject.toml` in a PR, merge, then push the tag
  `vX.Y.Z`. The gate checks that the tag matches `pyproject.toml` and that the tagged
  commit's `CI OK` is green, then the dist is built and published to PyPI (trusted
  publishing). Running it by hand (`workflow_dispatch`) is a dry run that only builds.

## License

This project is licensed under the MIT License.