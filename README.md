# jbase

jbase is a base Jekyll theme that:

- Imports Tachyons modules as SASS files
- Inlines styles
- Minimises HTML

You can choose which Tachyons modules to include in your styles by adding them to or removing them from the `_includes\style.scss` file.  Or, simply keep the full list and comment out any you don't want to import by preceding them with `\\`.

The Tachyons modules live in the `_sass` directory, along with 2 additional SASS files:

- `_c.scss`, which includes any additional user styles (I normally precede these with a '-c' to distinguish them from Tachyons selectors)
- `_variables.scss`, which includes any variables you want to refer to in `_c.scss`

## Import Order

Because the SASS files refer to each other and `_c.scss` may refer to `_variables.scss`, the first files you import should be:

1. "variables"
2. "normalize"
3. "media-queries"
4. "colors"

## Import everything

Avoid all choice and simply import:

1. "tachyons-4.8.1"
2. "variables"
3. "c"

## Moi

<ul>
  <li><a href="https://www.leonpaternoster.com">Leon Paternoster</a></li>
  <li><a href="https://www.twitter.com/leonpaternoster">@leonpaternoster</a></li>
</ul>
