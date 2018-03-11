# Jekyll Tachyons

Jekyll Tachyons is a base Jekyll theme that:

- Imports Tachyons modules as SASS files
- Inlines styles
- Minimises HTML

You can choose which Tachyons modules to include in your styles by adding them to or removing them from the `_includes\style.scss` file. Or, simply keep the full list and comment out any you don't want.

The Tachyons modules live in the `_sass` directory, along with 2 additional SASS files:

- `_c.scss`, which includes any additional user styles (I normally precede these with a '-c' to distinguish them from Tachyons selectors)
- `_variables.scss`, which includes any variables you want to refer to in `_c.scss`

## Media queries

Tachyons is mobile first, i.e. media query breakpoints are only applied as the screen width increases. Default styles are applied to all screen widths.

It uses three breakpoints, which can be applied to almost all tachyons selectors through the `selector-[breakpoint-shorthand]` syntax. For example, the `db` selector (`display: block`) can be employed in these ways:

- `db` (default, applies to all screen widths)
- `db-ns` (applies to medium and large screen widths)
- `db-m` (applies to medium screen widths only)
- `db-l` (applies to large screen widths and up only)

You can define the ranges of `ns`, `m` and `l` in the `media-queries.scss` file by overriding the defaults after they've been declared.

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
