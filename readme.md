# csv-validator

Tiny project that accepts a CSV, validates columns based on a set of rules and spits out an import example.

## run it

just open the [index.html](index.html) and you should be good to go.

## usage

### rules

Before running the validation of a CSV you can manually specify the rules to check or choose one of the preselected options. This far, only one things is checked which is the existance of a column or not by looking at the CSVs first line headers. The next step of this would be to validate the contents of each column such as if it contains links or numbers.

![validation-rules](set-validation-rules.gif)

### validation

Once a ruleset is chosen, simply pick your CSV. The errors will be displayed as a bullet list of missing columns or the file will be sampled to show a number of example lines.

![Usage](usage.gif)

## dependencies

This small proof-of-concept relies on
* [https://www.papaparse.com/](https://www.papaparse.com/) which does the heavy lifting of parsing the CSV
* [http://getskeleton.com/](http://getskeleton.com/) for styling
* [https://releases.jquery.com/](jquery) for interaction handling and easy lookup
* [https://lodash.com/](lodash) to simplify some actions such as sampling or truncating

## live reload

To debug the html contents, it's easiest to use the `livereload` plugin. The snippet is automatically added to the layout header unless running in `production` environment.

```
npm install -g livereload
livereload
```

## next steps

It would be really cool to accept google sheet links straight off as well. I could parse these and convert them to the CSV download format:

```
https://docs.google.com/spreadsheets/d/{key}/gviz/tq?tqx=out:csv&gid={sheet_id}
```

The file will need to be publically open to allow this though.