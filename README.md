# A simple responsive Octopress theme

There isn't a very wide choice of Octopress themes out there, so I decided
to make my own. It's inspired heavily by Simon Foster's blog
(http://simonfosterdesign.com/blog/), relying mostly on typography (all
typographical elements are stored as variables for simple customization).

The theme makes use of bourbon for SASS mixins, lettering.js for typography,
and prettify.js and zclip.js for displaying code blocks.

## Demo

See http://fivetonine.eu

## Install

	# cd octopress/.themes
	# git clone https://github.com/elisehein/Pageturner.git
	# rake install\[Pageturner\]
	# rake generate

## About

`sass/_variables.scss` allows for a lot of customization.

### Fonts

I experimented with a lot of fonts and didn't bother removing the ones I
didn't like so there's a lot to choose from. See `sass/_typography.scss`
for a full list of fonts that come with this theme.

### Code blocks and syntax highlighting

The theme comes with Prettify.js for syntax highlighting. My color scheme of
choice for Prettify was Hemisu from
http://jmblog.github.com/color-themes-for-google-code-prettify/. To use a
different color scheme, add the css file to `sass/.` change the stylesheet name in the
`<head>` section of `source/_layouts/default.html` (this is the base layout
that all other pages use). You will need to save the css file as .scss,
otherwise `rake generate` won't pick it up.

Using Prettify does not require any special markdown syntax. You simply
begin a code block with the usual indentation or grave characters. 

Of course, the the standard of using Pygments and `{% codeblock %}` should
work as well, but this theme does not include styling for any `{% codeblock
%}` elements.


## Issues

- zclip.js error `PPB_Graphics2D.PaintImageData: Rectangle is outside
	bounds.`
- `_responsive.scss` mixins are causing syntax errors. This is probably
	caused by the way rake compiles sass files. Using regular `@media`
	queries instead until fixed.
- No styling for Octopress codeblock and gist plugins yet
- If you've enabled like buttons or disqus comments in your _config.yml, you will need to add relevant tags and styling
