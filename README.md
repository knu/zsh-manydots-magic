manydots-magic for zsh
========================

Synopsis
--------

* manydots-magic - zle tweak for emulating "..."=="../.." etc.

Description
-----------

This tweek helps input ancestor directories beyond the parent (`..')
in a handy way.	 You can just type triple dots to input `../..',
quadruple dots to `../../..', etc..

	% .. [Hit <.>]
	% ../.. [Hit <.>]
	% ../../.. [Hit <^H>]
	% ../.. [Hit <^H>]
	% ..

How to set up
-------------

Put manydots-magic somewhere in your $fpath and add these lines to
your .zshrc:

	autoload -Uz manydots-magic
	manydots-magic

If you are enabling url-quote-magic, make sure to load url-quote-magic
first and then load manydots-magic.

License
-------

Copyright (c) 2011 Akinori MUSHA

Licensed under the 2-clause BSD license.
See LICENSE for details.
