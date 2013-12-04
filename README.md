# Cozy Code Guidelines

## Generic code style

* lines must not be longer than 80 characters
* indentation must be done with 4 spaces
* file names should be in snake_case
* variables name must not be abbreviated
* class names should be CamelCase, starting with uppercase
* no blank line at the end of files.

## CSS / Stylus

* all class names must be written in lowercase
* layout attributes (margin, width...) must be placed before others.

## Coffeescript
* no parenthesis in function declaration when it has no parameter
* `or` and `and` must be used instead of `||` and `&&`
* the `return` keyword should be explicit when needed
* variables names should be camelCase, starting with lowercase

## Javascript

* variables names should be camelCase, starting with lowercase

## Pyhon

* variables names should be snake_case, starting with lowercase
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
- have the same snake_case_file_name than their templates

## Node.js

Catching process level exception may corrupt/leak memory, apps sould exit when
it happens and let the cozy-controller restart them.
```coffee
process.on 'uncaughtException', (err) =>
   console.log err.stack
   process.exit 1
```

## Express / Americano

### Errors

With Express, use next to handle errors:

    module.exports.doStuff = (req, res, next) =>
        File.all (err, files) -
            if err?
                next err
            else
                res.send files
