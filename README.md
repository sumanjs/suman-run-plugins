
# Suman Run Plugins

# To contribute see CONTRIBUTING.md

Users use the plugins in this package by including a @config.json file in their tests

```json
// @config.json
{
  "@run": {
    "plugin": {
      "location": "npm",
      "value": "suman-run-plugins/plugins/x"
    }
  }
}
```

## About

Each plugin is versioned separately - as each plugin is published separately to NPM, like so:

`@suman-run-plugins/x`


## As a whole

You can import either:

`suman-run-plugins/plugins/x`    # will always be the latest version, is bundled with suman

or

`@suman-run-plugins/x`           # can be installed in package.json and versioned
