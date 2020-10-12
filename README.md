# DsConsumer1

## Steps

### Setup new Angular repository
`npx -p @angular/cli ng new ds-consumer1`

Select css option 'scss'

### Add Everyday Rewards ds package
`npm install @mothershipvc/rewards-ds`

### Configure Angular to use custom elements
See https://stenciljs.com/docs/angular

#### Copy DS assets into Angular project
In angular.json, under architect > build > options > assets, add these settings:

```json
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
```


### Run project

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The app will automatically reload if you change any of the source files.
