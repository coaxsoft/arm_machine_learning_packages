# ARM-ready machine learning packages

This repository contains pre-compiled for M1 packages. 

The idea of this repo is to have one storage for the packages and then
just include them as urls in your project's package manager.

Examples of usage of the libraries with the common package managers.

### Pipenv

```yaml
scipy = {version = "~1.8", markers = "platfotm_machine == 'x86_64'"}
scipy_m1 = {url = <github_url_to_package>, markers = "platfotm_machine == 'arm64'"}
```

### Poetry

```yaml
scipy = [
  {version = "~1.8", markers = "platfotm_machine == 'x86_64'"},
  {url = <github_url_to_package>, markers = "platfotm_machine == 'arm64'"},
]
```

## Issues & Help Wanted

There is an issue with `scipy`. If you install current scipy from `wheels/scipy...`
you may see an error

```shell
ImportError: dlopen(.venv/lib/python3.9/site-packages/scipy/special/_ufuncs.cpython-39-darwin.so, 2): Symbol not found: _cephes_cosdg
  Referenced from: .venv/lib/python3.9/site-packages/scipy/special/_ufuncs.cpython-39-darwin.so
  Expected in: flat namespace
 in .venv/lib/python3.9/site-packages/scipy/special/_ufuncs.cpython-39-darwin.so
```

Help wanted resolving this problem. The closest issue found is [scipy#5093](https://github.com/scipy/scipy/issues/5093)
