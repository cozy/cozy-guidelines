**VARS TO REPLACE IN TEMPLATE:**

** REMOVE THIS SECTION BEFORE PUBLISHING**

- `<APP_NAME>`: the application name
- `<APP_REPO>`: Github app repository name
- `<APP_SHORT_DESCRIPTION>`: a quick app description
- `<APP_PORT>`: app running port
- `<APP_MAINTAINER>`: Github main maintainer username (don't forget `@` :))
- `<SLUG_TX>`: transifex app slug
- `<SLUG_GH>`: Github repository slugname

---

![Travis build status shield](https://img.shields.io/travis/cozy/<APP_REPO>.svg)
![NPM release version shield](https://img.shields.io/npm/v/npm.svg)
![Github Release version shield](https://img.shields.io/github/release/cozy/<APP_REPO>.svg)
![NPM Licence shield](https://img.shields.io/npm/l/express.svg)


[Cozy][cozy] <APP_NAME>
=======================


What's Cozy?
------------

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 64 64" width="64" height="64"><g fill="#33a6ff"><path d="M40.446 38.433c-1.07-.702-1.122-1.99-1.125-2.048-.006-.35-.29-.626-.64-.62-.347.01-.625.296-.618.644.003.046.02.65.308 1.364-3.806 3.628-9.784 3.633-13.598.022.295-.724.314-1.34.314-1.385.006-.347-.27-.635-.615-.644-.34-.01-.63.27-.643.62 0 .05-.05 1.345-1.123 2.047-.29.194-.373.587-.182.88.12.185.32.286.528.286.117 0 .236-.034.342-.104.275-.18.506-.387.7-.605 2.117 1.92 4.793 2.88 7.47 2.88 2.68 0 5.363-.964 7.485-2.892.195.222.427.433.71.62.105.068.226.102.344.102.205 0 .407-.103.528-.29.19-.293.108-.688-.182-.88z"/><path d="M64 39.46c0-8.897-6.79-16.227-15.424-17.006-.464-3.835-2.193-7.38-4.97-10.12-3.185-3.14-7.396-4.867-11.85-4.867-4.458 0-8.667 1.727-11.852 4.868-2.79 2.75-4.524 6.316-4.976 10.172-3.827.454-7.364 2.202-10.095 5.012C1.715 30.727 0 34.97 0 39.46c0 9.414 7.6 17.073 16.946 17.073h30.106C56.395 56.533 64 48.873 64 39.46zM47.242 53.332H16.757c-7.476 0-13.558-6.16-13.558-13.736 0-7.403 5.94-13.563 13.24-13.734.963-.022 1.736-.806 1.758-1.78.167-7.397 6.25-13.415 13.556-13.415 7.305 0 13.385 6.016 13.553 13.413.022.992.822 1.778 1.798 1.778h.138c7.475 0 13.557 6.163 13.557 13.737 0 7.575-6.082 13.737-13.558 13.737z"/></g></svg>

[Cozy][cozy] is a platform that brings all your web services in the same private space.  With it, your webapps and your devices can share data easily, providing you with a new experience. You can install Cozy on your own hardware where no one's tracking you.


What's <APP_NAME>?
------------------

<APP_SHORT_DESCRIPTION>


Hack
----

### Install and run in dev mode

Hacking the <APP_NAME> app requires you [setup a dev environment][setup].

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

and point your browser to your dev VM at http://localhost:9104, your app is now available in your dashboard.


### Tests

Tests are run by [mocha] under the hood, and written using [chai] and [sinon]. You can easily run the tests suite with:

```sh
$ cd <SLUG_GH>
$ npm run test
```

:pushpin: Don't forget to update / create new tests when you contribute to code to keep the app the consistent.


### Resources

All documentation is located in the `/docs` app directory. It provides an exhaustive documentation about worflows (installation, development, pull-requests…), architecture, code consistency, data structures, dependencies, and more.

Feel free to read it and fix / update it if needed, all comments and feedback to improve it are welcome!


### Open a Pull-Request

If you want to work on <APP_NAME> and submit code modifications, feel free to open pull-requests! Our basic worflow is:

- PR point to the `development` branch
- You need to cover your code and feature by tests
- You may add documentation in the `/docs` directory to explain your choices if needed
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
