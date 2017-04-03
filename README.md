# api documentation for  [step (v1.0.0)](https://github.com/creationix/step#readme)  [![npm package](https://img.shields.io/npm/v/npmdoc-step.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-step) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-step.svg)](https://travis-ci.org/npmdoc/node-npmdoc-step)
#### A simple control-flow library for node.JS that makes parallel execution, serial execution, and error handling painless.

[![NPM](https://nodei.co/npm/step.png?downloads=true)](https://www.npmjs.com/package/step)

[![apidoc](https://npmdoc.github.io/node-npmdoc-step/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-step_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-step/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-step/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-step/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Tim Caswell",
        "email": "tim@creationix.com"
    },
    "bugs": {
        "url": "https://github.com/creationix/step/issues"
    },
    "dependencies": {},
    "description": "A simple control-flow library for node.JS that makes parallel execution, serial execution, and error handling painless.",
    "devDependencies": {},
    "directories": {},
    "dist": {
        "shasum": "b300e9d2ae9057d4d78633aae2303813a94bdff2",
        "tarball": "https://registry.npmjs.org/step/-/step-1.0.0.tgz"
    },
    "engine": [
        "node >=0.2.0"
    ],
    "gitHead": "9bd3479d0cdca1417b7aef5fd1d8e9340c404eeb",
    "homepage": "https://github.com/creationix/step#readme",
    "license": "MIT",
    "main": "lib/step",
    "maintainers": [
        {
            "name": "creationix",
            "email": "tim@creationix.com"
        }
    ],
    "name": "step",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git+ssh://git@github.com/creationix/step.git"
    },
    "scripts": {},
    "version": "1.0.0"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module step](#apidoc.module.step)
1.  [function <span class="apidocSignatureSpan">step.</span>fn ()](#apidoc.element.step.fn)



# <a name="apidoc.module.step"></a>[module step](#apidoc.module.step)

#### <a name="apidoc.element.step.fn"></a>[function <span class="apidocSignatureSpan">step.</span>fn ()](#apidoc.element.step.fn)
- description and source-code
```javascript
function StepFn() {
  var steps = Array.prototype.slice.call(arguments);
  return function () {
    var args = Array.prototype.slice.call(arguments);

    // Insert a first step that primes the data stream
    var toRun = [function () {
      this.apply(null, args);
    }].concat(steps);

    // If the last arg is a function add it as a last step
    if (typeof args[args.length-1] === 'function') {
      toRun.push(args.pop());
    }


    Step.apply(null, toRun);
  }
}
```
- example usage
```shell
n/a
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
