# DsConsumer 
No styles or assets copied from DS

## Git 
https://github.com/KBora/ds-consumer-examples/tree/feature/no-styles

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


### Run project

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The app will automatically reload if you change any of the source files.
