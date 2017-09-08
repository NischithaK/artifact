[![Introducing Artifact Video](docs/data/artifact-thumb.png)][4]

- **[Installation Guide](docs/Installation.md)**
- **[Quick Start Guide](docs/QuickStart.md)**
- **[Cheat Sheet](docs/CheatSheet.md)**
- **[FAQ](docs/FAQ.md)**
- **[Simple Quality][1]**: short free book which is the full user guide
  for artifact and teaches quality best practices.
- **[Design Documents][2]**: also see how [you can do this][3]

[1]: https://vitiral.gitbooks.io/simple-quality/content/
[2]: http://vitiral.github.io/artifact/#artifacts/REQ-1
[3]: https://github.com/vitiral/artifact/wiki/Exporting-Html
[4]: https://www.youtube.com/watch?v=kMzxKVkKLlE

## Artifact: design documentation for everybody

<img width="300" alt="portfolio_view" src="https://github.com/vitiral/artifact/blob/master/docs/logo/logo.png?raw=true">

Artifact is the simple, linkable and trackable design documentation tool for
everybody. It allows anyone to write and link their design docs both to each
other and to source code, making it easy to track how complete their project
is. Documents are revision controllable, can be rendered as a static web page
and have a full suite of command line tools for searching, displaying, checking
and formatting them.

Writing detailed design documents is one of the core pillars of quality software
development. Design documents are how you capture the requirements (purpose) of
your project and link them to your specifications (how you will build it). They
let you get your ideas on paper before writing code, and help you have fewer
painful refactors. They create a reference for developers and curious users of
how and why your project was developed a certain way, and make it easier to
refactor your project when that becomes necessary.

Even though design documents are critical to the quality of software, there
are very few tools for writing them and integrating them into the larger context
of a project. Artifact aims to fill the major gap in quality best practices by
making writing good design documents *useful* to the average developer.

First of all, artifact makes it easy to write design documents in *text files*
and link them by just specifying their `partof` attribute. This allows
developers to put their design documents under revision control, review them
using regular code review tools and use all the normal text processing tools
(vim, grep, sed, etc) to view, edit and refactor them. Artifact also provides
some command line tools of its own.

Secondly, design documents can be linked to their implementation in source-code
through a language agnostic syntax, simultaniously tracking the project
completion. Once linked, anyone reading the documentation can see what
specification a method is supposed to implement. They can then easily search
for that specification to get an idea of the larger context, making the source
code comments more self documenting.

Finally, artifact exports a beautiful rendered view of the design documents
for hosting on sites like github and viewing in a web browswer ([example][2]).
This completes the self documenting nature and allows anyone, even
non-developers, to view the design documents of their project. Rendered
artifacts contain *links to the source code*. Seeing a `#SPC-foo` comment in
source tells a developer which specification the code implements, and it is
easy to navigate the code repository by just browsing the design documents.

Furthermore, if the name of an artifact changes, `art check` will tell you
where your dangling references are. Never again will you have to be scared
of refactoring your design documents, it is as easy as refactoring your
code.

In this way, artifact aims to unify all of the other quality best practices
while also making development easier and more fun.  Check out the brief
[commercial video][4] and the [Quick Start Guide](docs/QuickStart.md) for an
introduction.

[![Build Status](https://travis-ci.org/vitiral/artifact.svg?branch=master)](https://travis-ci.org/vitiral/artifact)

### Pre-release notice
Artifact is now (finally) feature complete for 1.0. The 0.8 release has been
released and 1.0 is probably coming within a few weeks.

## Contributors
To set up a build environment and run tests, simply run:

```bash
git clone git@github.com:vitiral/artifact.git && cd artifact
source env  # installs environment to `target/env`
just test-all
```

Note: `source env` will take a while as it (locally) installs
build/test/lint/fmt toolchains for rust, node.js and python from scratch. It
does not touch ANYTHING in your global environment.

A quick source code overview:
- `justfile` contains build/test/etc scripts
- design documents are in `design/`
- rust source code is in `src/`
- elm source code (html frontend) is in `web-ui/src/`
- selenium (end-to-end web) tests are in `web-ui/sel_tests/`

## Licensing

### Goals
The intent of the artifact licensing is that:
- The artifact application remains open source under a copy-left license
  but can be linked and built upon in any way (LGPLv3+)
- Anything generated by artifact can be licensed any way the user wishes
  to, including the built static html pages.
- Any documents, tutorials or specifications for artifact (except the code
  and logo) remain public domain and can be used for any purpose at all.

### Specifics
All documentation and tutorials for the artifact application are released under
the CC0 Creative Commons Public Domain License with the intent that you should
feel free to copy, paste and modify any of the designs, guides examples or
exported data for any purpose (including commercial) without the need of
attribution. You can read more about CC0 here:
https://creativecommons.org/publicdomain/

The CC0 license applies to:
- All project [docs](docs)
- The [Artifact Design Documents](http://vitiral.github.io/artifact/#artifacts/REQ-1)
    (also located in `design/`)
- The Artifact Documentation (located in `docs/`) except the logo in `docs/logo`
- The [Artifact Wiki](https://github.com/vitiral/artifact/wiki)
- Any file or data created by any artifact command, including:
    - documents created by `art init`
    - documents created by `art tutorial`
    - compiled html/css/json files created by `art export`

The artifact logo (named Tula) is licensed under Creative Commons
Attribution-ShareAlike (`CC BY-SA`) and can be used by the artifact project for
any purpose without needing additional attribution. The artifact logo is located
in `docs/logo` and was originally created by
[packapotatoes](https://github.com/packapotatoes).

The artifact source code (located in `src/` and `web-ui/src`) are licensed under
the LGPLv3+, except for files which say otherwise in their header or folders
containing a different `LICENSE` file. See [LICENSE.txt](LICENSE.txt) for more
information.
