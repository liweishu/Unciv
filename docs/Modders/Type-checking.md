# Type checking

Mistakes happen. Misnamed fields, things we forgot to add, or even stuff we didn't know existed.

Computers can handle a lot of that themselves, so we can let them do the work to ensure that our json files are correct, by using *json schemas*.

As of now, only Buildings.json has a proper schema

## Using Android Studio

- Double-click space, search "json schema mappings", enter
- Click the small '+' (top, under 'language & frameworks' text)
- Put the URL as `https://raw.githubusercontent.com/yairm210/Unciv/master/docs/Modders/schemas/buildings.json`
- Click the '+' under the 'Schema version' text, add 'File pattern', put pattern as `*/Buildings.json`

Tada! Now Android Studio will recognize all Buildings.json files as belonging to that schema, and will warn you of inconsistencies!

## Using VSCode

- ctrl-shift-p, search "open user settings (json)", enter
- Copy this into the settings:
```json
    "json.schemas": [
        {
            "fileMatch": [
                "*/Buildings.json"
            ],
            "url": "https://raw.githubusercontent.com/yairm210/Unciv/master/docs/Modders/schemas/buildings.json"
        }
    ]
```

## Using an online tool

If you don't use any of these tools, you can check your file online using [this tool](https://www.jsonschemavalidator.net/)

However, it can't handle the missing commas that vscode and Android Studio handle, so you may need to get your json up to spec to use it.

The schema you want to validate against is:
```json
{
	"$ref": "https://raw.githubusercontent.com/yairm210/Unciv/master/docs/Modders/schemas/buildings.json"
}
```