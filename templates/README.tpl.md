**VARS TO REPLACE IN TEMPLATE:**

** REMOVE THIS SECTION BEFORE PUBLISHING**

- `<APP_NAME>`: the application name
- `<APP_REPO>`: Github app repository name
- `<APP_SHORT_DESCRIPTION>`: a quick app description
- `<APP_PORT>`: app running port
- `<APP_MAINTAINER>`: Github main maintainer username (don't forget `@` :))
- `<SLUG_TX>`: transifex app slug
- `<SLUG_GH>`: Github repository slugname
- `<SLUG_NPM>`: NPM slugname

---

![Travis build status shield](https://img.shields.io/travis/cozy/<APP_REPO>.svg)
![NPM release version shield](https://img.shields.io/npm/v/<SLUG_NPM>.svg)
![Github Release version shield](https://img.shields.io/github/release/cozy/<APP_REPO>.svg)
![NPM Licence shield](https://img.shields.io/npm/l/<SLUG_NPM>.svg)


[Cozy][cozy] <APP_NAME>
=======================


What's Cozy?
------------

![Cozy Logo](https://raw.githubusercontent.com/cozy/cozy-guidelines/master/templates/cozy_logo_small.svg)

[Cozy][cozy] is a platform that brings all your web services in the same private space.  With it, your webapps and your devices can share data easily, providing you with a new experience. You can install Cozy on your own hardware where no one's tracking you.


What's <APP_NAME>?
------------------

<APP_SHORT_DESCRIPTION>


Hack
----

### Install and run in dev mode

Hacking the <APP_NAME> app requires you to [setup a dev environment][setup].

You can then clone the app repository and install dependencies:

```sh
$ git clone https://github.com/cozy/<SLUG_GH>.git
$ cd <SLUG_GH>
$ npm install
```

:pushpin: If you use a node environment wrapper like [nvm] or [ndenv], don't forget to set your local node version before doing a `npm install`.

Cozy's apps use a standard set of _npm scripts_ to run common tasks. You can so start you development workflow with:

```sh
$ cd <SLUG_GH>
$ npm run watch
```

and point your browser to http://localhost:<APP_PORT>.


### Run it inside the VM

You can easily view your current running app in your VM, use [cozy-dev]:

```sh
# in a terminal, run your app in watch mode
$ cd <SLUG_GH>
$ npm run watch
```

```sh
# in another terminal, install cozy-dev (first time) and run the deploy
$ cd <SLUG_GH>
$ npm install -g cozy-dev
$ cozy-dev deploy <APP_PORT>
```

your app is available in your vm dashboard at http://localhost:9104.


### Tests

Tests are run by [mocha] under the hood, and written using [chai] and [sinon]. You can easily run the tests suite with:

```sh
$ cd <SLUG_GH>
$ npm run test
```

:pushpin: Don't forget to update / create new tests when you contribute to code to keep the app the consistent.


### Resources

All documentation is located in the `/docs` app directory. It provides an exhaustive documentation about workflows (installation, development, pull-requests…), architecture, code consistency, data structures, dependencies, and more.

Feel free to read it and fix / update it if needed, all comments and feedback to improve it are welcome!


### Open a Pull-Request

If you want to work on <APP_NAME> and submit code modifications, feel free to open pull-requests! Our basic workflow is:

- PR point to the `development` branch
- You need to cover your code and feature by tests
- You may add documentation in the `/docs` directory to explain your choices if needed
- We recommend to use [task lists][checkbox] to explain steps / features in your PR
- you do _not_ need to build app to submit a PR
- you should update the Transifex source locale file if you modify it for your feature needs (see Localization section below)


Community
---------

### Localization

Localization and translations are handled by [Transifex][tx], which is used by all Cozy's apps.

As a _translator_, you can login to [Transifex][tx-signin] (using your Github account) and claim an access to the [app repository][tx-app]. Locales are pulled when app is build before publishing.

As a _developer_, you must [configure the transifex client][tx-client], and claim an access as _maintainer_ is the [app repository][tx-app]. Then please **only update** the source locale file (usually `en.json` in client and/or server parts), and push it to Transifex repository using the `tx push` command.


### Maintainer

The lead maintainer for Cozy <APP_NAME> is <APP_MAINTAINER>, send him/her a :beers: to say hello!


### Get in touch

You can reach the Cozy Community by:

- Chatting with us on IRC [#cozycloud on Freenode][freenode]
- Posting on our [Forum][forum]
- Posting issues on the [Github repos][github]
- Say Hi! on [Twitter][twitter]


Licence
-------

Cozy <APP_NAME> is developed by Cozy Cloud and distributed under the [AGPL v3 license][agpl-3.0].



[cozy]: https://cozy.io "Cozy Cloud"
[setup]: https://dev.cozy.io/#set-up-the-development-environment "Cozy dev docs: Set up the Development Environment"
[agpl-3.0]: https://www.gnu.org/licenses/agpl-3.0.html
[tx]: https://www.transifex.com/cozy/
[tx-signin]: https://www.transifex.com/signin/
[tx-app]: https://www.transifex.com/cozy/<SLUG_TX>/dashboard/
[tx-client]: http://docs.transifex.com/client/
[freenode]: http://webchat.freenode.net/?randomnick=1&channels=%23cozycloud&uio=d4
[forum]: https://forum.cozy.io/
[github]: https://github.com/cozy/
[twitter]: https://twitter.com/mycozycloud
[nvm]: https://github.com/creationix/nvm
[ndenv]: https://github.com/riywo/ndenv
[cozy-dev]: https://github.com/cozy/cozy-dev/
[mocha]: https://mochajs.org/
[chai]: http://chaijs.com/
[sinon]: http://sinonjs.org/
[checkbox]: https://help.github.com/articles/basic-writing-and-formatting-syntax/#task-lists