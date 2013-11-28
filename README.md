# Cozy Code Guidelines

## Generic code style
* lines must not be longer than 80 characters
* indentation must be done with 4 spaces
* variables name must not be abbreviated
* file naming?

## Coffeescript
* no parenthesis in function declaration when it has no parameter
* `or` and `and` must be used instead of `||` and `&&`
* the `return` keyword should be explicit when needed

## Javascript

## Node.js

## Express / Americano

### Errors

With Express, use next to handle errors:

    File.all (err, files) -
        if err?
            next err
        else
            res.send files
