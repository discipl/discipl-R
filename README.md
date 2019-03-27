# discipl-R

R package that simplifies working with the linked data stored in platforms through discipl-core with functionality to subscribe on channels 
so that information is automaticly added. This works nicely with Shiny to create dashboards with live data.

#### Using browserify to bundle npm packages and V8 to run Javascript in R

V8 can enable R to use simple .js files directly.
For larger packages browserify can be used to bundle the files and dependencies in a single Javascript-file.

First make sure that V8 and browserify are installed, run:

- 'install.packages("V8")' and 'library(V8)' in R
- 'npm install -g browserify' in a command prompt

Example package with 'js-beautify'. Run these in the command prompt in a directory of choice:

- 'npm install js-beautify'
- 'echo "global.beautify = require('js-beautify');" > in.js'
- 'browserify in.js -o bundle.js'

Which bundles the package into a single file

Run in R:

- 'ct <- v8()'
- 'ct$source("~/Desktop/bundle.js")' *
- 'ct$get(JS('Object.keys(global)'))'

The package should now be available in R.
\* If R_HOME isn't set in Windows, use the direct path for the file as the source.
