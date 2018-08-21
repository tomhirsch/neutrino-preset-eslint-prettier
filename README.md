# `@usertech/neutrino-preset-eslint-prettier`

> Work in Progress - the default eslint and prettier settings are open for discussion

Preset for neutrino which sets up `eslint` linting configured for use with prettier.

    // .neutrinorc.js
    module.exports = {
        use: [
            ['@usertech/neutrino-preset-eslint-prettier'],
            ...
        ],
    }

Create `.eslintrc.js` to provide config for your IDE.

    // .eslintrc.js
    const { Neutrino } = require("neutrino");

    module.exports = Neutrino({ root: __dirname })
    	.use(".neutrinorc.js")
    	.call("eslintrc");


Create `.prettierrc.yml` to set up `@usertech` standard rules.

    # .prettierrc.yml
    printWidth: 100
    parser: flow
    useTabs: true
    singleQuote: true
    trailingComma: all
    arrowParens: always

`lint` command is added in a same way as if `@neutrinojs/eslint` was used alone.

    {
      ...
      "scripts": {
        ...
        "lint": "neutrino lint",
        ...
      },
      ...
    }

So you can run

    $ yarn lint
    $ yarn lint --fix