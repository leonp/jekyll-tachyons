# Jekyll Tachyons

Jekyll Tachyons is a base Jekyll theme that:

- imports Tachyons individual modules (borders, spacing, flexbox etc. etc. etc.) as individual SASS files
- provides an option to inline styles
- creates basic `default` and `post` layout files
- adds a `c-sans-serif` variable to `_variables.scss`
- adds a `.c-sans-serif` rule to `_c.scss`

Useful if you're using Tachyons and want to get a Jekyll site up and running quickly, while controlling what [Tachyons modules](http://tachyons.io/docs/table-of-styles/) you load. Tachyons is a small CSS framework, but you still want to avoid loading CSS you don't need.

## Installation

Clone or fork this repo, or download the files. Then:

1. if you haven't done so already, install [Bundler](http://bundler.io/)
2. navigate to the theme folder
3. run `bundle update`
4. run `bundle install`
5. run `bundle exec jekyll s` to serve and build the site

## Inlining styles in the head or linking to a separate CSS file

You can get the theme to include styles within `<style></style>` tags in the document `head`. This saves a call to a separate CSS file, maybe speeding your site up a bit.

To inline your styles make sure you include this line in `_config.yml`:

`css: inline`

If you don't include the line, or change it to something like `css: linked`, the theme will link to a separate CSS file (`/css/style.css`).

Note that the theme is set to inline styles by default.

## Selecting Tachyons modules

The theme loads each Tachyons module individually as a SASS file using Jekyll's build pipeline.

Simply comment out any modules you don't want by preceding its SASS file name with `//`. For example, if you don't need negative margins:

`// "negative-margins"`

The file you need to edit depends on whether you've chosen to inline your styles:

- If you're inlining styles, edit the list in `/_includes/style.scss`
- If you're referring to an external stylesheet, edit the list in `/css/style.scss`

There are 2 additional SASS files:

- `_c.scss`, which includes any additional user styles (I normally precede these with a 'c-' to distinguish them from Tachyons selectors).
- `_variables.scss`, which includes any variables you want to refer to in `_c.scss`

Alternatively, import just the following files. You can comment out or even delete the rest.

1. `_tachyons-4.8.1.scss`
2. `_variables.scss`
3. `_c.scss`

(Note: If you haven't created any variables and/or custom rules, you'll only need to import `_tachyons-4.8.1.scss`.)

## Media queries

Tachyons is mobile first, i.e. media query breakpoints are only applied as the screen width increases. Default styles are applied to all screen widths.

It uses three breakpoints, which can be applied to almost all tachyons selectors through the `selector-[breakpoint-shorthand]` syntax. For example, the `db` selector (`display: block`) can be employed in these ways:

- `db` (default, applies to all screen widths)
- `db-ns` (applies to medium and large screen widths)
- `db-m` (applies to medium screen widths only)
- `db-l` (applies to large screen widths and up only)

You can define the ranges of `ns`, `m` and `l` by overriding the defaults after they've been declared.

To do this, edit the `_media-queries.scss` file in the `_sass` folder.

By default, it contains these lines, which define your responsive breakpoints:

`$breakpoint-not-small: 'screen and (min-width: 30em)' !default;
$breakpoint-medium: 'screen and (min-width: 30em) and (max-width: 60em)' !default;
$breakpoint-large: 'screen and (min-width: 60em)' !default;`

Comment out or delete these lines and replace them with your new screen width ranges. For example:

`$breakpoint-not-small: 'screen and (min-width: 40em)' !default;
$breakpoint-medium: 'screen and (min-width: 40em) and (max-width: 64em)' !default;
$breakpoint-large: 'screen and (min-width: 64em)' !default;`

Now, your responsive suffixes will work like so:

- `db` (default, applies to all screen widths)
- `db-ns` (applies to 40em screen widths and up)
- `db-m` (applies to medium screen widths only, i.e. between 40em and 64em)
- `db-l` (applies to large screen widths and up only, i.e. 64em and up)

## Import Order

Because the SASS files refer to each other and `_c.scss` may refer to `_variables.scss`, the first files you import should be:

1. `_normalize.scss`
2. `_media-queries.scss`
3. `_variables.scss`
4. `_colors.scss`
5. `_spacing.scss`

## Moi

- [leonpaternoster.com](https://www.leonpaternoster.com)
- [Micro.blog](https://micro.blog/leonp)
- [Twitter](https://www.mobile.twitter.com/leonpaternoster)
