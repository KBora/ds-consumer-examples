# DsConsumer 
Rds styles imported via style component

## Git 
https://github.com/KBora/ds-consumer-examples/tree/feature/ds-import-styles

## Steps

1. Setup new Angular repository
`npx -p @angular/cli ng new ds-consumer1`
  * Select css option 'scss'

2. Add Everyday Rewards ds package
`npm install @mothershipvc/rewards-ds`

3. Configure Angular to use custom elements (see https://stenciljs.com/docs/angular)
    * In base module `app.module.ts`:
      * Import CUSTOM_ELEMENTS_SCHEME `import { CUSTOM_ELEMENTS_SCHEMA, NgModule } from '@angular/core';`
      * Add `schemas: [CUSTOM_ELEMENTS_SCHEMA],` to `@NgModule({ ... }`
    * In `main.ts`:
      * `import { defineCustomElements } from 'node_modules/@mothershipvc/rewards-ds/dist/loader';`
      * `defineCustomElements()`;

4. Insert global style component in markup:
```
<rds-style-import global></rds-style-import>
```

5. Import design system assets and fonts to Angular build
  * In `angular.json`, under `project` > `architect` > `build`:
```
"assets": [
    "src/favicon.ico",
    "src/assets",
    {
      "glob": "**/*",
      "input":  "./node_modules/@mothershipvc/rewards-ds/dist/collection/assets/",
      "output": "./assets/"
    },
    {
      "glob": "**/*",
      "input":  "./node_modules/@mothershipvc/rewards-ds/dist/assets/fonts/",
      "output": "./assets/fonts"
    }
  ],      
```

### Run project

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The app will automatically reload if you change any of the source files.
