# pyproject-info
Expose information from pyproject.toml in GitHub Actions

Currently just the detected src path:

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
```