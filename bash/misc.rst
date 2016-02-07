
vi mode
-------

In bash::

    $ set -o vi

vi mode in applications that use readline, (psql for example)::

    $ echo 'set editing-mode vi' >> ~/.inputrc

tr
--

tr can be used to replace one set of characters with another set, or to delete a set of
characters. Input can be taken from stdin or a file. Use -d to delete characters in the
given set. Use -c to translate or delete the *complement* of the given set. Use -s to
replace multiple occurrences of a character with a single character.

Convert uppercase to lowercase::

    $ tr '[:upper:]' '[:lower:]' < myfile.txt

Remove anything that isn't uppercase or whitespace::

    $ tr -dc '[:upper:][:white:]' < myfile.txt

random string generator
-----------------------

Read from /dev/urandom and use 'tr' to remove anything that isn't an alphanumeric
character or one of the given puntuation characters. Use 'fold' to format the stream as
a sequence of 48 character lines. Use 'head' to take the first of these lines.

::

    $ tr -dc 'a-zA-Z0-9!?$%^&*()-+=' < /dev/urandom | fold -w 48 | head -n 1

Avoid ':' as this will need to be escaped in a postgres PGPASSFILE where the format is::

    <host>:<port>:<database>:<user>:<password>

