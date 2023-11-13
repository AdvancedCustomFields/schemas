# ACF Schemas

This respository contains the schema used in ACF which extend the native WordPress schemas to add ACF's specific options.

It is based on https://github.com/WordPress/gutenberg/tree/trunk/schemas.

JSON schemas are used by code editors to offer tooltips, autocomplete, and validation.

## JSON schema usage

Many editors recognize the `$schema` property in JSON files.

Update your `block.json` to include:

```json
{
	"$schema": "https://advancedcustomfields.com/schemas/block.json"
}
```

Visual Studio Code and PhpStorm are two popular editors that work out of the box. However, some editors require a plugin installed, and not all editors recognize the `$schema` property. Check your editor's documentation for details. Additionally, [SchemaStore.org](https://www.schemastore.org/) and [JSON Schema](https://json-schema.org/implementations.html#editors) have lists of editors known to have support if your current editor is unsupported.

## Local Development

You may wish to update one of the schemas to conform to a new change in the structure. In order to do this you'll want to be able to see how your changes impact how your IDE displays schema information.

To allow this you will need to:

-   update your block's `block.json` to include:

```json
{
	"$schema": "file://{{FULL_FILE_PATH}}/schemas/json/block.json"
}
```

Be sure to replace `{{FULL_FILE_PATH}}` with the full local path to your Gutenberg repo.

With this in place you should now be able to edit either `schemas/json/block.json` in order to see changes reflected in `block.json` in your IDE.