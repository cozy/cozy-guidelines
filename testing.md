# Test guidelines

Here are the guidelines to perform tests properly:

* Use [Mocha](https://www.npmjs.org/package/mocha) as framework (install and run it via dependencies `./node_modules/mocha/bin`).
* Use [Should](https://npmjs.org/package/should) as assertion library
* Use latest mocha scoping rules (otherwise, incompatibilities between mocha versions)
* Use [cozy-fixtures](https://npmjs.org/package/cozy-fixtures)
* Use [linter](https://npmjs.org/package/coffeelint)
* Run tests on JS build on Travis
* Always clean before & after each tests file (otherwise we cant run them separately)
* Split big modules in several files
* Split test file that runs in more than 1 minute (and that are too complex to be made faster)
* For route testing, run operation in the following order : Clean DB, Add fixtures, Start application
