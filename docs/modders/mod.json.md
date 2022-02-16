## What is the mod.json file, and how do I use it?
The `mod.json` file is a JSON file that contains information about your mod. It is used by the mod loader to load your mod.
It contains the following information:
 - **name**: The name of your mod. Currently, this is only used for the mod loader. But it will probably be made visible to the user in the future.
 - **version**: The version of your mod. Currently, this is only used for the mod loader. But it will probably be made visible to the user in the future.
 - **author**: The author of your mod. Currently, this is only used for the mod loader. But it will probably be made visible to the user in the future.
 - **mainClass**: The main class of your mod. This is the class that will be loaded, should extend the `Mod` class.
 - **build**: The build number of your mod. Should increase every build.

Here is an example of a mod.json file:
```json
{
    "name": "Example Mod",
    "version": "1.0.0",
    "author": "Example Author",
    "mainClass": "com.example.ExampleMod",
    "build": 1
}
```