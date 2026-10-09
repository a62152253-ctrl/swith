# SWITH language and project specification

## File roles

| File | Role |
| --- | --- |
| `.search` | Project manifest. It declares the app and its modules. |
| `*.SERCH` | Source unit for a page/module, API or reusable service. |

Filenames may contain spaces and Polish characters. Keep the extension exactly `.search` for the manifest and `.SERCH` for source units.

## Minimal project

```text
MyApp/
├── .search
└── HOME.SERCH
```

`.search`:

```search
app "My App"
domain "localhost"

dev {
  host "localhost"
  port 3442
  open auto
  hotReload true
}

modules { Home }
start { Home }
```

`HOME.SERCH`:

```serch
module Home
route "/"
access public

state { message = "Hello from SWITH" }

view {
  <main><h1 search-text="message"></h1></main>
}
```

## Modules, state and actions

A module is a browser page. `state` stores reactive values; a button can call an `action`.

```serch
module Counter
route "/counter"
access public

state { count = 0 }

view {
  <main>
    <h1>Counter</h1>
    <strong search-text="count"></strong>
    <button action="increment">Add one</button>
  </main>
}

action increment {
  script { state.count = state.count + 1 }
}
```

## API and services

Use an API unit for server-side endpoints:

```serch
api App
base "/api"

endpoint POST "/echo" {
  access public
  script {
    return { message: body.message }
  }
}
```

Use a service for reusable functions:

```serch
service TextTools {
  function wordCount(text) {
    return array.count(string.words(string.trim(text)))
  }
}
```

## Built-ins and runtime namespaces

SERCH scripts include the stable standard library (for example `string.trim`, `string.words`, `array.count`, `math.round`) and runtime namespaces including `db`, `api`, `auth`, `file`, `http`, `crypto`, `cache`, `event`, `env`, `system`, `log`, `sleep` and `services`.

The language is interpreted by SEARCH Runtime; it is not JavaScript hidden in a renamed file.

## Diagnostics

When Studio cannot open a project, first check that `.search` contains a manifest rather than `module` code. The editor reports the filename, line and column of a syntax error.

