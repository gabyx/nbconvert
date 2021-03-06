.. _changelog:

====================
Changes in nbconvert
====================

5.2.1
-----

`5.2 on GitHub <https://github.com/jupyter/nbconvert/milestones/5.2>`__

Major features
~~~~~~~~~~~~~~

In this release (along with the usual bugfixes and documentation improvements,
which are legion) we have a few new major features that have been requested for
a long time:

Global Content Filtering
++++++++++++++++++++++++

You now have the ability to remove input or output from code cells, markdown
cells and the input and output prompts. The easiest way to access all of these
is by using traitlets like TemplateExporter.exclude_input = True (or, for
example HTMLExporter.exclude_markdown = True if you wanted to make it specific
to HTML output). On the command line if you just want to not have input or
output prompts just use --no-prompt.

Execute notebooks from a function
+++++++++++++++++++++++++++++++++

You can now use the executenb function to execute notebooks as though you ran
the execute preprocessor on the notebooks. It returns the standard notebook and
resources options.

Remove cells based on regex pattern
+++++++++++++++++++++++++++++++++++

This removes cells based on their matching a regex pattern (by default, empty
cells). This is the RegexRemovePreprocessor.

Script exporter entrypoints for nonpython scripts
+++++++++++++++++++++++++++++++++++++++++++++++++

Now there is an entrypoint for having an exporter specific to the type of script
that is being exported. While designed for use with the IRkernel in particular
(with a script exporter focused on exporting R scripts) other non-python kernels
that wish to have a language specific exporter can now surface that directly.


- new: configurable ExecutePreprocessor.startup_timeout configurable #583
- new: RemoveCell preprocessor based on cell content (defaults to empty cell) #575
- new: function for executing notebooks: `executenb` #573
- new: global filtering to remove inputs, outputs, markdown cells (&c.), this works on all templates #554
- new: script exporter entrypoint #531
- new: configurable anchor link text (previously ¶) `HTMLExporter.anchor_link_text` #522

- new: configurable values for slides exporter #542 #558

- improved releases (how-to documentation, version-number generation and checking) #593
- doc improvements  #593 #580 #565 #554
- language information from cell magics (for highlighting) is now included in more formats #586
- mathjax upgrades and cdn fixes #584 #567
- better CI #571 #540
- better traceback behaviour when execution errs #521
- deprecated nose test features removed #519

- bug fixed: we now respect width and height metadata on jpeg and png mimetype outputs #588
- bug fixed: now we respect the `resolve_references` filter in `report.tplx` #577
- bug fixed: output metadata now is removed by ClearOutputPreprocessor #569
- bug fixed: display id respected in execute preproessor #563
- bug fixed: dynamic defaults for optional jupyter_client import #559
- bug fixed: don't self-close non-void HTML tags #548
- buf fixed: upgrade jupyter_client dependency to 4.2 #539
- bug fixed: LaTeX output through md→LaTeX conversion shouldn't be touched #535
- bug fixed: now we escape `<` inside math formulas when converting to html #514

Credits
~~~~~~~

This release has been larger than previous releases. In it 33 authors
contributed a total of 546 commits.

Many thanks to the following individuals who contributed to this release (in
alphabetical order):

- Adam Chainz
- Andreas Mueller
- Bartosz T
- Benjamin Ragan-Kelley
- Carol Willing
- Damián Avila
- Elliot Marsden
- Gao, Xiang
- Jaeho Shin
- Jan Schulz
- Jeremy Kun
- Jessica B. Hamrick
- John B Nelson
- juhasch
- Livia Barazzetti
- M Pacer
- Matej Urbas
- Matthias Bussonnier
- Matthias Geier
- Maximilian Albert
- Michael Scott Cuthbert
- Nicholas Bollweg
- Paul Gowder
- Paulo Villegas
- Peter Parente
- Philipp A
- Scott Sanderson
- Srinivas Reddy Thatiparthy
- Sylvain Corlay
- Thomas Kluyver
- Till Hoffmann
- Xiang Gao
- YuviPanda


5.1.1
-----

`5.1.1 on GitHub <https://github.com/jupyter/nbconvert/milestones/5.1.1>`__

- fix version numbering because of incomplete previous version number

5.1
---

`5.1 on GitHub <https://github.com/jupyter/nbconvert/milestones/5.1>`__

- improved CSS (specifically tables, in line with notebook) #498
- improve in-memory templates handling #491
- test improvements #516 #509 #505
- new configuration option: IOPub timeout #513
- doc improvements #489 #500 #493 #506
- newly customizable: output prompt #500
- more python2/3 compatibile unicode handling #502

5.0
---

`5.0 on GitHub <https://github.com/jupyter/nbconvert/milestones/5.0>`__

- Use :command:`xelatex` by default for latex export, improving unicode and font support.
- Use entrypoints internally to access Exporters, allowing for packages to declare custom exporters more easily.
- New ASCIIDoc Exporter.
- New preprocessor for sanitised html output.
- New general ``convert_pandoc`` filter to reduce the need to hard-code lists of filters in templates.
- Use pytest, nose dependency to be removed.
- Refactored Exporter code to avoid ambiguity and cyclic dependencies.
- Update to traitlets 4.2 API.
- Fixes for Unicode errors when showing execution errors on Python 2.
- Default math font matches default Palatino body text font.
- General documentation improvements. For example, testing, installation, custom exporters.
- Improved link handling for LaTeX output
- Refactored the automatic id generation.
- New kernel_manager_class configuration option for allowing systems to be set up to resolve kernels in different ways. 
- Kernel errors now will be logged for debugging purposes when executing notebooks. 

4.3
---

`4.3 on GitHub <https://github.com/jupyter/nbconvert/milestones/4.3>`_

- added live widget rendering for html output, nbviewer by extension

4.2
---

`4.2 on GitHub <https://github.com/jupyter/nbconvert/milestones/4.2>`_

- :ref:`Custom Exporters <external_exporters>` can be provided by external packages,
  and registered with nbconvert via setuptools entrypoints.
- allow nbconvert reading from stdin with ``--stdin`` option (write into
  ``notebook`` basename)
- Various ANSI-escape fixes and improvements
- Various LaTeX/PDF export fixes
- Various fixes and improvements for executing notebooks with ``--execute``.

4.1
---

`4.1 on GitHub <https://github.com/jupyter/nbconvert/milestones/4.1>`_

- setuptools fixes for entrypoints on Windows
- various fixes for exporters, including slides, latex, and PDF
- fixes for exceptions met during execution
- include markdown outputs in markdown/html exports

4.0
---

`4.0 on GitHub <https://github.com/jupyter/nbconvert/milestones/4.0>`_
