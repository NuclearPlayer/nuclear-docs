---
description: How to create and update translations
---

# Translating

When adding translations, a few things need to be done:

* add the json file with the correct name in `packages/app/app/locales` and keep it empty
* update the i18n script in `packages/app/package.json` by adding your locale 

  ```text
  {
  ...
  "scripts": {
   ...
    "i18n": "sync-i18n --files 'app/locales/*.json' --primary en --languages fr [your locale] --space 2"
  } 
  ...
  }
  ```

* run the command

  ```text
  npm run i18n
  ```

* edit the file `packages/app/common/settings.js` to add your local in user's choice

  ```javascript
  {
   name: 'language',
   category: 'program-settings',
   type: settingType.LIST,
   prettyName: 'language',
   placeholder: 'language-placeholder',
   options: ['en', 'fr', <your locale>],
   default: undefined
  }
  ```

* edit the `packages/app/app/i18n.js` file

  ```javascript
  ...
  import en from './locales/en.json';
  import <your locale> from './locales/<your locale>.json';
  ...
   resources: {
     en,
     ...
     <your locale>
   },
  ...
  ```

You can now translate your locale file from English to your language.

After you're done, you can add your translation to the readme, under "Community translations".

