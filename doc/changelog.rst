Changelog
=========

pynote 0.4 (XXXX-XX-XX)
-----------------------

.. note::
    
    This section here is used as a roadmap for the future release!

* Fixed tests, switched to pytest and setup travis.


pynote 0.3 (XXXX-XX-XX)
-----------------------

.. note::

    I switched pynote to https://pynote.readthedocs.org/ for hosting
    documentation and I switched to github issues as well. There are
    no reasons to maintain my own setup. Every issue ID below this 
    entry is obsolte and refer to my old redmine tracker.

.. work in progress
* Big data storage refactoring!
  JSON files are not used for storing data any more. Simple plain
  text files do the job much better. Git is used via git_wrapper
  to take care of revision control.

.. implemented
* Removed translation things (for now). If anybody needs this we can 
  create a transifex account to involve other people.
* New header design, thanks to Philipp Göttlich!
* Do not include any precompiled files in git. You can create the docs
  (man and html) with ``make docs`` in the doc folder.
* Missing import statement. Now you are informed about a misspelled
  pygments theme instead of a traceback.
* Refactored ``config.py`` to use default values.
* Do not use colors in ``note compare`` by default.


pynote 0.2.2 (2014-02-05)
-------------------------

Fixed some problems which especially occured since the last release.

* Fixed a wrong method call, see #370. Thanks to Klaus Seistrup.
* Fixed a problems with ``pynote.init`` and ``pynote.config``, see #368 
  and forum posts. Thanks to tonk and null.
* Improved ``pynote.container``. If no data files exist exit and print
  an error message.
* Got rid of git flow, see #369. The errors occured because I forgot
  to bump the version number. Git flow restricted me fixing this trivial
  error with a little rebase.


pynote 0.2.1 (2014-01-31)
-------------------------

Quick and dirty bugfix release

- Do not show an empty table, fixes #366.
- Quick patches for ``pynote.config``, because ``note init`` was broken,
  see #365.

  - Thanks to Udo Wendler!
  - ``pynote.config`` will be refactored in the next release!

- Removed an obsolete link from README.rst, see #362.


pynote 0.2 (2014-01-31)
-----------------------

New features

- localisation via pybabel (GNU gettext files), see #284.
  Added German translation.

- pygments support, see #301.

  - ``note show --lang``: Read notes with synthax highlighting.
    Find a list of supported lexers on the pygments project page!
  - ``note compare --no-color``: Unified diffs are colored by default.
    Suppress colors with ``--no-color``.
  - Choose your pygments theme in noterc with 'pygments_theme', see #307.

- tag support

  - ``note show`` shows tags in header
  - ``note list --tags``: Filter all notes depending on the given tag(s).
  - add tags to a note: ``note tags 1 --add "foo"``
  - delete tags from a note: ``note tags 1 --delete "foo"``
  - show tags: ``note tags 1``
  - show all used tags in active notes: ``note tags``

- ``note revisions``: Print out existing revisions of a note, see #290.
- ``note show --all``, see #293, thanks to nsmathew.
- ``note edit --title``, see #292, thanks to nsmathew.
- ``note-init`` script has been merged to ``note init``, see #295.
- The official documentation is now in redmine,
  http://redmine.sevenbyte.org/projects/pynote/wiki
- Added noterc manpage.

Fixes

- Do not create a new revision if nothing has been changed, see #304.
- Fixed a sorting issue especially with german dateformats, see #302.


pynote 0.1 (2013-12-24)
-----------------------

Rename ``~/.note/versions.json`` to ``~/.note/revisions.json``.

- Do not create a new revision if there are no changes, see #277.
- Improved ``pynote.__main__`` code. If no command is entered just
  choose note list, see #288.
- note trash works again, see #278.
- Added a note restore command to restore deleted notes from trash,
  see #281.
- Improved JSON serialization, see #285.
- Renamed ``versions.json`` to ``revisions.json``. Please rename that
  file in ``~/.note``!
- Reverted the changes in #276.
- Added a ``--no-header`` option to note show, thanks to stewie.


pynote 0.1b3 (2013-12-18)
-------------------------

Delete your ``~/.noterc`` and run ``note-init``. That should be enough!

- Dateformat can be set in ``~/.noterc``. Please refer to docs.python.org,
  strftime and strptime behavior.
- Compare command. Compare two revisions of a note by creating a
  unified diff.
- You only have to set your data dir in ``~/.noterc``. Like data = ~/.note.
- Do not display an empty table if there is no data, see #254.
- The root section in ``~/.noterc`` must be ``[DEFAULT]``. The previous values
  will not work any more!
- Add every revision to versions.json, see #276.


pynote 0.1b2 (2013-12-10)
-------------------------

- fixed ``setup.py``, see #255.


pynote 0.1b1 (2013-12-10)
-------------------------

- Initial release.
