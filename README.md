manydots-magic for zsh
======================

Synopsis
--------

* manydots-magic - zle tweak for emulating `...`==`../..` etc.

Description
-----------

This tweek helps input ancestor directories beyond the parent (`..`)
in a handy way.	 You can just type triple dots to input `../..`,
quadruple dots to `../../..`, etc..

	% .. [Hit <.>]
	% ../.. [Hit <.>]
	% ../../.. [Hit <^H>]
	% ../.. [Hit <^H>]
	% ..

As you see above, each of the `/..` parts complemented by this tweak
can be deleted by a single invocation of the `backward-delete-char`
command, only if invoked right after the magic happens.

	% .. [Hit </><.><.>]
	% ../.. [Hit <^H>]
	% ../.

Triple-dot is not a rarely used character sequence, and this tweak
kind of "knows" when it should be expanded.

	% ruby -e '(1.. [Hit <.>]
	% ruby -e '(1...

	% git log branch.. [Hit <.>]
	% git log branch...

	% git diff .. [Hit <.>]
	% git diff ../.. [Hit <b>]      <- This may be a path...
	% git diff ...b [Hit <ranch>]   <- Or not.
	% git diff ...branch

How to set up
-------------

Put the file `manydots-magic` somewhere in your `$fpath` (typically in
`$ZDOTDIR` which is set to something like `~/.zsh` or `~/.zsh.d`) and
add these lines to your `.zshrc`:

	autoload -Uz manydots-magic
	manydots-magic

If you are enabling `url-quote-magic`, make sure to load
`url-quote-magic` first and then load `manydots-magic`.

License
-------

Copyright (c) 2011, 2012 Akinori MUSHA

Licensed under the 2-clause BSD license.
See `LICENSE` for details.
