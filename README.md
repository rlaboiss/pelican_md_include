Use Markdown-Include extension: A Plugin for Pelican
====================================================

> **Note**<br>
> The code in this repository has been moved into the [markdown-include][] repository, which is maintained under the auspices of the [Pelican-plugins]() organization. The present repository is archived and preserved here for historical purposes.

[markdown-include]: https://github.com/pelican-plugins/markdown-include
[Pelican-plugins]:https://github.com/pelican-plugins

[![Build Status](https://img.shields.io/github/workflow/status/pelican-plugins/md-include/build)](https://github.com/pelican-plugins/md-include/actions)
[![PyPI Version](https://img.shields.io/pypi/v/pelican-md-include)](https://pypi.org/project/pelican-md-include/)
![License](https://img.shields.io/pypi/l/pelican-md-include?color=blue)

This plugin allows the use of the [Markdown-Include extension][] in Pelican articles.

[Markdown-Include extension]: https://github.com/cmacmackin/markdown-include

Installation
------------

This plugin can be installed via:

    python -m pip install pelican-md-include

Usage
-----

The syntax for use within Pelican articles is `{!filename!}`. According to the documentation of the Markdown-Include extension, this statement will be replaced by the contents of `filename` and will work recursively. The replacement is done prior to any other Markdown processing, so any Markdown syntax that is wanted can be used within the included files. For more details, see the [documentation][] of the markdown-include module of Python.

[documentation]: https://github.com/cmacmackin/markdown-include/#readme


Configuration
-------------

The following variables control the behavior of the plugin and can be set in the Pelican settings file:

- `MD_INCLUDE_BASE_PATH`: By default, the file name is given relative to the directory from where Pelican is run.  This can be changed with this variable.

- `MD_INCLUDE_ENCODING`: The encoding of the included files (defaults to `'utf-8'`).

- `MD_INCLUDE_INHERIT_HEADING_DEPTH`: If True, increases headings on include file by amount of previous heading. Combines with `MD_HEADING_OFFSET` option, below (defaults to False.)

- `MD_HEADING_OFFSET`: Increases heading depth by a specific ammount, in addition to the `MD_INCLUDE_INHERIT_HEADING_DEPTH` option (defaults to 0).


Alternative to this plugin
--------------------------

Pelican allows the use of extra Markdown extensions by declaring them in the `MD_EXTENSIONS` configuration variable.  However, as [explained][] in the Pelican documentation, adding new extensions via MD_EXTENSIONS is awkward, because all the extensions loaded by default must also be listed.  Besides avoiding this problem, this plugin provides a "pelicanish" way of setting the configuration values of the Markdown-Include extension (`base_path`, `encoding`, `inherit_heading_depth`, and `heading_offset`).  Furthermore, Markdown-Include extension must be installed in a place where Pelican can find it, what may be tricky.

[explained]: http://docs.getpelican.com/en/latest/settings.html

Contributing
------------

Contributions are welcome and much appreciated. Every little bit helps. You can contribute by improving the documentation, adding missing features, and fixing bugs. You can also help out by reviewing and commenting on [existing issues][].

To start contributing to this plugin, review the [Contributing to Pelican][] documentation, beginning with the **Contributing Code** section.

[existing issues]: https://github.com/pelican-plugins/md-include/issues
[Contributing to Pelican]: https://docs.getpelican.com/en/latest/contribute.html

Author
------

Copyright © 2015, 2021, 2022 Rafael Laboissière (<rafael@laboissiere.net>)

License
-------

This project is licensed under the AGPL-3.0 license.
