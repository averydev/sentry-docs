---
title: Ember
sidebar_order: 50
---
<!-- WIZARD -->
To use Sentry with your Ember application, you will need to use `@sentry/browser` (Sentry’s browser JavaScript SDK).  
On its own, `@sentry/browser` will report any uncaught exceptions triggered from your application.

If you use [ember-auto-import](https://github.com/ef4/ember-auto-import/) to install simply run:

```javascript
  yarn add @sentry/browser
  ```

or

```javascript
  npm i @sentry/browser
  ```

Then add this to your `app.js`:

```javascript
import * as Sentry from '@sentry/browser'

Sentry.init({
  dsn: '___PUBLIC_DSN___',
  integrations: [new Sentry.Integrations.Ember()]
});
```

If you don't use Ember Auto import, you will will also need to install `ember-cli-cjs-transform` with `ember install ember-cli-cjs-transform`.

Once that's complete, add this to your `ember-cli-build.js` file:

```javascript
app.import('node_modules/@sentry/browser/dist/index.js', {
  using: [
    { transformation: 'cjs', as: '@sentry/browser' }
  ]
});
```
<!-- ENDWIZARD -->
