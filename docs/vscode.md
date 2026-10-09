# VS Code support

Install the **Search Language** extension from the SEARCH downloads page or from its VSIX package.

The extension recognises `.search`, `.SERCH` and `.serch` files and provides:

- syntax colouring and file icons;
- snippets for manifests, modules, actions and API endpoints;
- diagnostics for common manifest/module mistakes;
- completions and hover help for SEARCH constructs;
- document symbols, definitions, references and rename support;
- workspace indexing of SEARCH imports and project files.

## AI / Copilot context

AI assistants work best when the repository includes a short language specification and real examples. Keep this repository’s `docs/language-spec.md` and the `examples/` folder in the workspace alongside your project. The editor extension supplies structure and diagnostics; it does not claim that an AI model has learned the language globally.

## Recommended workspace layout

```text
MyApp/
├── .search
├── HOME.SERCH
├── APP_API.SERCH
├── services/
│   └── TEXT.SERCH
└── docs/
    └── project-notes.md
```

