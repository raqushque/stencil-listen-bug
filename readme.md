## Stencil `@Listen` bug reproduction

Bug appears since 4.19.0

Event listeners added via `@Listen` decorator are fired twice after component was reconnected to DOM.

Only components built with output target `dist-custom-elements` are affected.

Listening to events from JSX works properly.

## Launching the demo

- `npm install` to install required dependencies
- `npm run build` to build components
- `npm run demo` to run bug demo (using `dist-custom-elements` build)

### In demo app

- Focus component (blue outline should appear)
- Press any key
  - Counter should go up by 1 and event be logged to console.
- Press the `Reconnect` button.
- Focus component once again.
- Press any key.
  - Counter increases by 2, two console messages are added.