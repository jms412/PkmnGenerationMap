Pokemon generation custom map to use with PoracleJS

**New Method (August 2021):**<br />
The version built into PoracleJS now supports regional forms correctly. Thank you Jabes.

Monster & Raid DTS<br />
{{generation}} - Gen Number (1, 2, 3, 4, 5, 6, 7, 8)<br />
{{generationName}} - Gen Name (Kanto, Johto, Hoenn, Sinnoh, Unova, Kalos, Alola, Galar)<br />
{{generationRoman}} - Gen Number Roman Numeral (I, II, III, IV, V, VI, VII, VIII)<br />

Example:<br />
Gen {{generation}} {{generationName}} Region

Result:<br />
Gen 6 Kalos Region

Web:<br />
![Screen Shot 2021-08-27 at 11 03 15 am 2](https://user-images.githubusercontent.com/80012316/131057023-eab144d7-61f7-4e2f-b085-5860d08e1fd8.png)

iOS:<br />
![image0](https://user-images.githubusercontent.com/80012316/131057040-80ec2f7b-fb8b-499a-ad21-f9667d45c0df.jpeg)


**Old Method (For Reference Only):**<br />
Current files to put in your config/customMaps folder: generation.json

Monster & Raid DTS<br />
```{{#if (map 'generation' pokemonId)}}{{#map 'generation' pokemonId}}\nGen {{genNumber}} {{genName}} Region{{/map}}{{/if}}{{#if (map 'generation' (concat pokemonId '_' formId))}}{{#map 'generation' (concat pokemonId '_' formId)}}\nGen {{genNumber}} {{genName}} Region{{/map}}{{/if}}```

Only one custom map will be applicable for each Pokemon. If the Pokemon doesn't have any forms or all forms are from the same generation the customMap will pick up the first part of the DTS: `{{#map 'generation' pokemonId}}\nGen {{genNumber}} {{genName}} Region{{/map}}{{/if}}` and the second part will be blank. And if the Pokemon has multiple forms and some of them are from different generations the first part of the DTS will be blank and it will pick up the second part: `{{#map 'generation' (concat pokemonId '_' formId)}}\nGen {{genNumber}} {{genName}} Region{{/map}}`
