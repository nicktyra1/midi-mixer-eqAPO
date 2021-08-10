# MIDI Mixer Template Plugin (Vite)

Use this template to quickly create a plugin for MIDI Mixer. It uses [TypeScript](https://www.typescriptlang.org/), [Vite](https://vitejs.dev/), and [midi-mixer-plugin](https://github.com/midi-mixer/midi-mixer-plugin) to provide an easy API and development environment with hot-loading built in!

## Usage

- Create a repository using this as a template
- Clone your repository in to `%appdata%/midi-mixer-app/plugins`
- Install Node (I'd recommend [Volta](https://volta.sh/))

``` bash
# install dependencies
npm install
```

``` bash
# start dev environment
npm run dev

# production build
npm run build
```

To ensure that the created plugin is easy to use for other users, make sure to commit your `dist` folder with any changes so that it can be downloaded and placed directly in to the `plugins` folder with no build step for the user.

The template also leverages MIDI Mixer's ability to have differing targets for dev and production. `package.json` defines two targets: `main` and `dev`. When the production version of the plugin is run, it'll use `main`, but will defer to `dev` if the plugin is loaded in development mode. Because Vite creates a local development server at `localhost:3000`, the `dev` key points to that, meaning we can develop with sourcemaps and hotreloading! Nice!

## API

See [midi-mixer-plugin](https://github.com/midi-mixer/midi-mixer-plugin) for API documentation.

## Manifest

A few key items are configurable in your plugin's `package.json`.

- `prettyName`: The name of your plugin in the MM UI
- `description`: The description in the MM UI
- `version`: The version of the plugin in the MM UI
- `author`: Your name in the MM UI
- `main`: Must point to the built entry file for your plugin
- `settings`: An object of settings that will appear in the MM UI's Settings page for the plugin - see the [definition](https://github.com/midi-mixer/plugin-template-vite/blob/main/package.json#L13-L33) and [fetching](https://github.com/midi-mixer/plugin-template-vite/blob/main/src/main.ts#L4-L9)
