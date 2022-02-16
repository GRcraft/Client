## Getting set up
To set up a new modding environment, and code your mod, follow the steps below. If you'd like to compile G_Rcraft from source, see [the developer guide](/docs/developer/SETUP.md).

### Dependencies
To compile G_Rcraft from source, you'll need to install the following dependencies:
 - [Gradle](https://gradle.org)
 - [Java 17](https://adoptium.net/)
 - A working G_Rcraft installation

This guide assumes you have already installed the above dependencies.

It should all work out of the box on any operating system that supports these dependencies.
### Setting up a new modding environment
To set up a new modding environment, clone the [G_Rcraft modding template repository](https://github.com/GRcraft/modding-template). You can do this by running the following command in your terminal: `git clone https://github.com/GRcraft/modding-template.git`, or by downloading the repository and extracting it into your project directory.

Once you are completed, open up the project in a file manager and navigate to the `libs` directory. This is where you'll be puting the G_Rcraft installation so you can use it as an API.

If you have compiled G_Rcraft from source, you can find the `libs` directory in the `build` directory of the G_Rcraft source code.
If you have installed G_Rcraft from the [G_Rcraft website](https://grcraft.grplayer.ga/), you can follow the instructions below to find the jar file.

1. Locate your `.minecraft` directory. If you are unsure how to find this, you can follow [this guide](https://minecraft.fandom.com/wiki/.minecraft) on how to find it.
2. Navigate to the `.minecraft` directory. This is where you'll find the `versions` directory.
3. Navigate to the `versions` directory. And open a directory called `G_Rcraft-1.18.1`.
4. Copy the `G_Rcraft-1.18.1.jar` file to your `libs` directory.

**🎉 Congratulations! You've set up your modding environment! Now you can interact with the native Minecraft source code, and load your mod into the game.**

### Setting up a new mod
Now you have your modding environment set up, you can start coding your mod. You can use the regular Minecraft API to interact with the game. If you'd like to get the game instance, we recommend using the following code in your `onEnable` method:
```
Minecraft minecraft = (Minecraft)this.game;
```
Furthermore, we recommend just looking around in the Minecraft source code to see what you can all modify. The options are almost endless.

### Understanding the API
A mod consists of a set of resources, which are files that are interpreted by the mod loader. The mod loader will load these files into memory, and then use them to modify the game.
There are 3 types of resources:

- **Java class files** These are files that are loaded into the JVM. These are the files that you'll be writing code in.
- **mod.json** This is a file that contains metadata about your mod. Read more about it [here](/docs/modders/mod.json).
- **pack.zip** This is a resource pack that contains all of the resources that your mod uses. It is just a regular resource pack, but the user can't disable or remove it without removing the mod.

It is important to set up your mod correctly, and to make sure that your mod is compatible with the latest version of G_Rcraft.
To do this, stay up to date with the latest version of G_Rcraft. We recommend joining the [G_Rcraft Discord](https://discord.gg/5Gcxq3JsgC). All new breaking changes will be announced there. You can also ask questions in there.

### Compiling
To compile your mod, you'll simply need to run the `jar` gradle task. This will create a `libs/G_Rcraft.jar` file in the `build` directory. You can then place this file in your `mods` game directory.

**🎉 Congratulations! You've just compiled your mod! Now you can place it in your mod directory!**

### Bonus tip
If you are using Linux, you can create a symbolic link to your `mods` directory in your `.minecraft` directory. This will allow you to load the mod without having to copy it to your `mods` directory.
Just used the following command in your terminal:
```
ln -s /path/to/your/mods/build/directory/themodjar.jar /path/to/your/.minecraft/mods/themodjar.jar
```