Pokemon generation custom map to use with PoracleJS

Current files to put in your config/customMaps folder: generation.json

Monster & Raid DTS

```{{#if (map 'generation' pokemonId)}}{{#map 'generation' pokemonId}}\nGen {{genNumber}} {{genName}} Region{{/map}}{{/if}}{{#if (map 'generation' (concat pokemonId '_' formId))}}{{#map 'generation' (concat pokemonId '_' formId)}}\nGen {{genNumber}} {{genName}} Region{{/map}}{{/if}}```

Only one custom map will be applicable for each Pokemon. If the Pokemon doesn't have any forms or all forms are from the same generation the customMap will pick up the first part of the DTS: `{{#map 'generation' pokemonId}}\nGen {{genNumber}} {{genName}} Region{{/map}}{{/if}}` and the second part will be blank. And if the Pokemon has multiple forms and some of them are from different generations the first part of the DTS will be blank and it will pick up the second part: `{{#map 'generation' (concat pokemonId '_' formId)}}\nGen {{genNumber}} {{genName}} Region{{/map}}`
