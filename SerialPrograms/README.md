# Guideline of Resources Folder

## Slug

A slug is a string that uniquely identify an object for a program to manage it. Each Pokémon and in-game item needs a slug for SerialPrograms to identify it internally.
For example, slugs for all the Pokémon species can be found in [Pokedex-National.json](Resources/Pokemon/Pokedex/Pokedex-National.json).

We set a slug to consist only of lowercase letters, digits and hyphens. To sanitize Pokémon names into slugs, we convert white spaces and special characters to hyphens if they are in the middle of a name:

"Mime Jr." -> `mime-jr`

"Farfetch'd" -> `farfetch-d`

### Pokémon Forms

To create slugs for Pokémon forms, we have following rules:

- Shiny forms add "-shiny" to the end of the slug.

- Gender differences add "-(fe)male" to the end of the slug, e.g. `gyarados-male`. The only exception is Nidoran which get `nidoran-m` and `nidoran-f` since the two genders are two separate Pokédex entries.

- Mega forms add "-mega" to the end of the slug, e.g. `lucario-mega`, `charizard-mega-x`.

- Regional forms add "-\<region_name\>" to the end of the slug, e.g. `rattata-alola`. If a Pokémon species has a new regional form in an upcoming generation, we don't retroactively add a regional name to the base form's slug to ensure backward comaptibility. For example, Kantonian rattata is still `rattata`. We don't use `rattata-kanto`.

- Gigantamax forms add "-gmax" to the end of the slug, e.g. `venusaur-gmax`.

- General form differences. Use best judgement, e.g. `shellos-east-sea`, `shellos-west-sea`.

If a form has two or more suffixes, use this order:

speciesname-regional-generalform-gender-mega-gmax-shiny


