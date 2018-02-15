
Windows and Buffers
-------------------

Open a file::

    $ emacs -nw intro.rst

Now 'intro.rst' is the current buffer.

Within emacs open up another file::

    C-xf

then enter a new file name or tab-complete the name of an existing file.

This file is then the current buffer but 'intro.rst' is still open in its buffer.

To cycle through buffers::

    C-x LEFT
    C-x RIGHT

To save a buffer::

    C-x s

To save a buffer without confirmation prompt::

    C-xs

To kill the current buffer::

    C-x k RET

To kill a buffer by name::

    C-x k bufname RET


Exit emacs::

    C-xc

Minibuffer
::::::::::

Exit the minibuffer::

    C-g or C-]


