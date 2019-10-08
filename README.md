stoplight/spectral mirror
===========================

Mirror of `stoplight/spectral` package for pre-commit.

For pre-commit: see https://github.com/pre-commit/pre-commit

For `@stoplight/spectral`: see https://github.com/stoplightio/spectral


### Using stoplight/spectral with pre-commit

Add this to your `.pre-commit-config.yaml`:

    -   repo: https://github.com/luzfcb/mirrors-stoplight-spectral
        rev: ''  # Use the sha / tag you want to point at
        hooks:
        - id: stoplight/spectral


By default only be analyzed files matched with the regex: `(openapi|swagger)(2|3|)((\.[0-9])|)\.(yaml|json)$`
See a regex sample here: https://regex101.com/r/cYniFH/1 

The default regex can be overridden using the `files` parameter

    -   repo: https://github.com/luzfcb/mirrors-stoplight-spectral
        rev: ''  # Use the sha / tag you want to point at
        hooks:
        - id: stoplight/spectral
          files: cloudformation/service/swagger\.yaml$

Additional arguments `spectral lint` can be added using the `args` parameter


    -   repo: https://github.com/luzfcb/mirrors-stoplight-spectral
        rev: ''  # Use the sha / tag you want to point at
        hooks:
        - id: stoplight/spectral
          args: ['--ruleset', 'rule_set_file.yaml']



### Development


Update available versions Spectral in this repository:


```bash
pip install -e git+https://github.com/luzfcb/pre-commit-mirror-maker.git@add-name-argument#egg=pre_commit_mirror_maker

git clone git@github.com:luzfcb/mirrors-stoplight-spectral.git

pre-commit-mirror mirrors-stoplight-spectral --entry "spectral lint" --language node --package-name @stoplight/spectral  --files-regex "(openapi|swagger)(2|3|)((\.[0-9])|)\.(yaml|json)$" --require-serial --name stoplight/spectral
```
