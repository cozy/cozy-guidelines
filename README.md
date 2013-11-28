# Cozy Code Guidelines


## Coffeescript

## Javascript

## Node.js

## Express / Americano

### Errors

With Express, use next to handle errors:

    File.all (err, files) -
        if err
            next err
        else
            res.send files
