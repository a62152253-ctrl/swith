# SWITH

SWITH is a lightweight project format and language layer for building local web apps with **SEARCH Studio**.

Each project has two kinds of files:

- `.search` — project manifest: app name, local development settings, modules and start screen;
- `.SERCH` — application modules, UI, state, actions, API endpoints and services.

This repository is deliberately **documentation and examples only**. It does not contain the full runtime, installer or generated binaries.

## Start here

1. Install SEARCH Studio for Windows from [searchpoint.pl/search](https://searchpoint.pl/search/).
2. Create a project folder and add a `.search` file. Its full name is simply `.search` — no name before the dot.
3. Add one or more `.SERCH` modules.
4. Double-click `.search` after installing SEARCH Studio, or open the folder in Search Studio.

## Documentation

- [Language and project specification](docs/language-spec.md)
- [VS Code extension and language tooling](docs/vscode.md)
- [Examples](examples/)
- [Online documentation](https://searchpoint.pl/search/docs/)

## Example projects

- [Task board](examples/task-board/) — state, UI bindings and actions.
- [Contact book](examples/contact-book/) — form state and CRUD-style interactions.
- [API counter](examples/api-counter/) — module plus a scripted API endpoint.

## What SWITH is not

`.search` is a project manifest, not a module source file. Do not paste `module ...` code into `.search`; put it in a named `.SERCH` file, for example `HOME.SERCH`.

The exact runtime and editor are distributed separately so the repository stays fast to browse, clone and use as AI/VS Code context.

