# karma-phantomjs-launcher

> Launcher for [PhantomJS].

This is a fork of karma-runner/karma-phantomjs-launcher to point to my fork of Medium/phantomjs. This is only to trick phantomjs to pulling down the v2.0.0 binaries from the cdn.

## Installation

The easiest way is to keep `karma-phantomjs-launcher` as a devDependency in your `package.json`.
```json
{
  "devDependencies": {
    "karma": "~0.10",
    "karma-phantomjs-launcher": "~0.1"
  }
}
```

You can simple do it by:
```bash
npm install karma-phantomjs-launcher --save-dev
```

## Configuration
```js
// karma.conf.js
module.exports = function(config) {
  config.set({
    browsers: ['PhantomJS', 'PhantomJS_custom'],

    // you can define custom flags
    customLaunchers: {
      'PhantomJS_custom': {
        base: 'PhantomJS',
        options: {
          windowName: 'my-window',
          settings: {
            webSecurityEnabled: false
          }
        },
        flags: ['--remote-debugger-port=9000']
      }
    }
  });
};
```

You can pass list of browsers as a CLI argument too:
```bash
karma start --browsers PhantomJS_custom
```

----

For more information on Karma see the [homepage].


[homepage]: http://karma-runner.github.com
[PhantomJS]: http://phantomjs.org/
