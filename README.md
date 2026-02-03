# pyproject-info
Expose information from pyproject.toml in GitHub Actions

Currently the detected src path and PyPI project path:



## Outputs



- `path`: Detected package path (e.g. `src/mypackage`)

- `pypi`: PyPI project path (e.g. `p/project-name`, `n/numpy`)



## Usage



```yaml

- name: Detect package path

  id: pkg

  uses: actions/pyproject-info



- name: Download version

  uses: actions/download-artifact@v6

  with:

    name: version.py

    path: ${{ steps.pkg.outputs.path }}



- name: Link to PyPI

  run: echo "Check it out at https://pypi.org/${{ steps.pkg.outputs.pypi }}"

```
