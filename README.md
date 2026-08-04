<p align="center"><a href="https://valkyrja.io" target="_blank">
    <img src="https://raw.githubusercontent.com/valkyrjaio/art/refs/heads/master/long-banner/orange/python.png" width="100%">
</a></p>

# Valkyrja Starter (App)

Starter template for building Python applications on the [Valkyrja][Valkyrja url]
framework.

This repository gives you a working Valkyrja application as a starting point:
HTTP and CLI entry points pre-wired, example controllers and commands,
configuration scaffolding, and a ready-to-customize `app` package. The starter
passes the same linting, static analysis, and architectural rules as the
Valkyrja framework itself, so you can build your application rather than clean
up the foundation.

<p>
    <a href="https://github.com/valkyrjaio/valkyrja-starter-app-python/blob/26.x/LICENSE.md"><img src="https://img.shields.io/github/license/valkyrjaio/valkyrja-starter-app-python.svg" alt="License"></a>
    <a href="https://github.com/valkyrjaio/valkyrja-starter-app-python/actions/workflows/ci.yml?query=branch%3A26.x"><img src="https://github.com/valkyrjaio/valkyrja-starter-app-python/actions/workflows/ci.yml/badge.svg?branch=26.x" alt="CI Status"></a>
</p>

Status
------

Warning: the Python port is in progress. This repository holds the application
scaffold, the CI pipeline, and the release process. The framework it builds on
does not exist yet, so the application does not run yet.

PHP is the reference implementation, and every other port mirrors its structure,
its naming, and its tests. Read [`PORTS.md`][ports url] for the state of each
language.

What's in the Box
-----------------

The list below is what the port delivers. Each item exists in the PHP reference
implementation today.

- **Pre-wired HTTP and CLI entry points** — the application boots and answers
  both a web request and a command-line invocation
- **Example controllers and commands** — working code that shows routing,
  request handling, and command dispatch
- **Configuration scaffolding** — a config layer with example files and
  environment-driven overrides
- **Testing setup** — pytest configured with example tests, in the structure
  that Valkyrja's own components use
- **Full CI pipeline** — Ruff, mypy, Bandit, import-linter, and pytest, all
  configured and passing on a clean clone
- **ASGI worker integrations** — Uvicorn, Hypercorn, or Granian for a
  persistent-worker deployment

Installation
------------

### Use this template _(recommended)_

This repository is a GitHub template. Use the **Use this template** button at
the top of the repository page to create your own application repository from
it.

### Clone manually

```bash
git clone https://github.com/valkyrjaio/valkyrja-starter-app-python.git your-app
cd your-app
rm -rf .git && git init
```

**Python 3.14 or later is required.**

Warning: this repository publishes no package. It is a template that you copy,
rather than a dependency that you add. `uv add` does not install it.

Getting Started
---------------

### Project Structure

```
src/app/            your application code
tests/              your tests, mirroring src/
.github/ci/         each CI tool, isolated with its own lockfile
```

### Running the CI Gate

```bash
uv run poe ci
```

The gate runs the copyright header check, Ruff, mypy, import-linter, Bandit, and
pytest at 100% coverage. It runs the same checks that the pull request runs, so a
clean local run means a clean pull request.

### Writing the Header Into a New File

```bash
uv run poe copyright-header
```

Ruff reports a file whose header does not match, and it corrects nothing. This
command corrects it. Set your own package name in
`.github/ci/copyright-header/config` first.

Documentation
-------------

For framework-level questions about Valkyrja itself, see the
[Valkyrja framework repository][framework url].

For the build tool that generates the cache, see [Sindri][sindri url].

Contributing
------------

This starter is an open-source, community-driven project. Thank you for your
interest in helping develop, maintain, and release it.

See [`CONTRIBUTING.md`][contributing url] for the submission process and
[`VOCABULARY.md`][vocabulary url] for the terminology that Valkyrja uses.

Security Issues
---------------

If you discover a security vulnerability, please follow the
[disclosure procedure][security vulnerabilities url].

License
-------

This starter is open-source software licensed under the
[MIT license][MIT license url]. See [`LICENSE.md`](./LICENSE.md).

[Valkyrja url]: https://valkyrja.io
[framework url]: https://github.com/valkyrjaio/valkyrja-python
[sindri url]: https://github.com/valkyrjaio/sindri-python
[ports url]: https://github.com/valkyrjaio/architecture/blob/26.x/PORTS.md
[contributing url]: https://github.com/valkyrjaio/.github/blob/26.x/CONTRIBUTING.md
[vocabulary url]: https://github.com/valkyrjaio/.github/blob/26.x/VOCABULARY.md
[security vulnerabilities url]: https://github.com/valkyrjaio/.github/blob/26.x/SECURITY.md
[MIT license url]: https://opensource.org/licenses/MIT
