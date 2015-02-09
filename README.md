# Cozy Code Guidelines

## Generic code style

* lines must not be longer than 80 characters
* indentation must be done with 4 spaces
* file names should be in snake\_case
* variables name must not be abbreviated
* class names should be CamelCase, starting with uppercase
* two blank lines between functions
* one blank line at the end of files.

## CSS / Stylus

* all class names must be written in lowercase
* layout attributes (margin, width...) must be placed before others

## Coffeescript

* no parenthesis in function declaration when it has no parameter
* `or` and `and` must be used instead of `||` and `&&`
* the `return` keyword should be explicit when needed
* variables names should be camelCase, starting with lowercase
* describe all options field in the comments

## Javascript

* variables names should be camelCase, starting with lowercase
* describe all options field in the comments

## Python

* variables names should be snake\_case, starting with lowercase
* global variables should be written with uppercase
* Files should be [pep8](http://www.python.org/dev/peps/pep-0008/) compliant

## Backbone

### Views

Views should :
- have the default Backbone constructor MyView(options)
- not model.fetch() themselves
- not render() themselves
- not fail when rendered with a non-fetched Model
- not fail when rendered multiple time
- have the same snake\_case\_file\_name than their templates


## Node.js

### Catching exception

Catching process level exception may corrupt/leak memory, apps sould exit when
it happens and let the cozy-controller restart them.

```coffee
process.on 'uncaughtException', (err) =>
   console.log err.stack
   process.exit 1
```
### Return Shortcuts

Return shortcuts should not be used by default. They can be used to avoid branchings that have very few meaning. The most known case where it occurs is:

```coffeescript
myfunc (err) ->
    return callback err if err
```

## Localisation

Localisation is based on keys. In the code, there is no string that is directly displayed. Every string should refer to a translation key. Translations keys are stored in localisation files named with the locale (`en` for English, `fr` for French, etc.).

[Exemple of a localisation folder](https://github.com/cozy/cozy-home/tree/master/client/app/locales)

Here are the rules to follow when using locale keys:

* Separators are spaces, other separators must be discarded
* The first word describes the context
* key names must be lowercased
* key names must be no longer than 40 chars or 6 words
* key names must be self-explicit
* key names must be in english
* key names are sorted by alphabetical order


## Express / Americano

### Instance routes

When you write an API that works on a given instance of an object you should
use the param function of Americano/Express. This function acts as a
preprocessor to fetch given instance:

In sever/controllers/routes.coffee:

```coffee
alarms = require './alarms'

module.exports =
    'alarmid':
        param: alarms.fetch
```

In sever/controllers/alarms.coffee:

```coffee
module.exports.fetch = (req, res, next, id) ->
    Alarm.find id, (err, alarm) =>
        if err or not alarm
            res.send error: true, msg: "Alarm not found", 404
        else
            req.alarm = alarm
            next()
```


### Response

### Success response

* Always set the proper status (`200` for success, `201` for creation, `204` for deletion).
* Put objects as a response of a success.

```coffeescript
res.status(201).send(newContact)
```

### Error response

Always returned error with the proper status too by using the `next` function from Express:

```coffeescript
err = new Error "Something wrong occured"
err.status = 404
return err
```

If the error status is 500, no need to specify it again:

```coffee
module.exports.doStuff = (req, res, next) =>
    File.all (err, files) -
        if err?
            next err
        else
            res.send files
```

## What is Cozy?

![Cozy Logo](https://raw.github.com/mycozycloud/cozy-setup/gh-pages/assets/images/happycloud.png)

[Cozy](http://cozy.io) is a platform that brings all your web services in the
same private space.  With it, your web apps and your devices can share data
easily, providing you with a new experience. You can install Cozy on your own
hardware where no one profiles you. 

## Community 

You can reach the Cozy Community by:

* Chatting with us on IRC #cozycloud on irc.freenode.net
* Posting on our [Forum](https://groups.google.com/forum/?fromgroups#!forum/cozy-cloud)
* Posting issues on the [Github repos](https://github.com/mycozycloud/)
* Mentioning us on [Twitter](http://twitter.com/mycozycloud)
