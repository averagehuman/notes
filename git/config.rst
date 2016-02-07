

Multiple Identities
-------------------

The default identity with which commits are made is defined in `~/.gitconfig`::

    [user]
        name = work
        email = me@work.com

To override this for a particular repository add a similar stanza to that
repository's `.git/config`::

    [core]
        ...

    [branch "master"]
        ...

    [user]
        name = notwork
        email = me@notwork.com

For non-public repositories, you also need to update `.ssh/config` with a stanza for
the non-default account, eg.::

    Host github.com-notwork
        HostName github.com
        User notwork
        IdentitiesOnly yes
        IdentityFile ~/.ssh/notwork.pem

and when you are adding a remote for the non-default account, the host has to match up
with this stanza, ie.::

    $ git remote add origin git@github.com-notwork:notwork/myrepo.git

rather than the usual::

    $ git remote add origin git@github.com:notwork/myrepo.git

