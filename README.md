# Hello Test Plugin

A minimal test plugin for the [Izum Music](https://github.com/izum-music) plugin store. It demonstrates the smallest possible plugin: a manifest, a single HTML view, and a click counter.

![Preview](for_readme.gif)

## What it does

- Displays a greeting message.
- Shows the plugin `id` and `version` retrieved from `MusicPluginAPI`.
- Counts button clicks (in-memory, resets on reload).

## Structure

plug_test/
├── manifest.json    ← plugin metadata
├── index.html       ← plugin UI (entry point)
├── icon.jpg         ← icon shown in the plugin list
└── README.md

No dependencies. No bundler. No permissions requested.

## Install (from source)

1. Zip the contents of this folder (files must be at the archive root, not nested):
   ```bash
   cd plug_test
   zip -r ../hello-test.zip . -x '.git/*' '*.DS_Store' 'for_readme.gif'
   ```
2. In Izum Music: **Settings → Plugins → Install → From file** → pick `hello-test.zip`.
3. Confirm and open the plugin from the list.

## Install (via plugin store)

Once published as a GitHub Release:

1. Push this folder to a public GitHub repo.
2. Create a release (`v1.0.0`) with `hello-test.zip` attached.
3. Add an entry to the store `registry.json`:
   ```json
   {
     "id": "com.izum.test.hello",
     "name": "Hello Test Plugin",
     "author": "izum-music",
     "description": "A minimal test plugin",
     "repo": "<owner>/<repo>"
   }
   ```
4. In the app open **Plugins → Store**, refresh, install.

## Manifest reference

| Field | Value |
|---|---|
| `id` | `com.izum.test.hello` |
| `version` | `1.0.0` |
| `view.entry` | `index.html` |
| `permissions` | none |

See the full manifest spec in the [Izum Music Plugins docs](https://github.com/izum-music).

## License

MIT