## Getting started
To compile the project from source, please follow the instructions below.
If you'd like to code mods, please follow the instructions in [the modder guide](MODDERS.md).

### Dependencies
To compile the project, you'll need the following dependencies:
 - [git](https://git-scm.org/), the version control system. Used to generate & apply patches.
 - [gradle](https://gradle.org/), the build system. Used to compile the project.
 - [java](https://openjdk.java.net/), the Java programming language. Used to compile the project.

**Currently there is no official Windows & macOS support, it will be added soon.**

This guide assumes you have these dependencies installed and are using the latest versions. The documentation is written with IntelliJ in mind, but you can use any IDE.

### Getting the source code
To get the source code, you'll need to clone the repository. You can do this from the command line:
```git clone https://github.com/GRcraft/Client.git```
you can also clone the repository from [the GitHub website as a zip file](https://github.com/GRcraft/Client/archive/refs/heads/main.zip).

### Setting up the build environment
Open the project in your IDE or terminal and run the `setup` task. This will set up anything MCP related.
When the task is complete, you'll have a normal MCP environment. Now execute some shell commands to set up the patching system.

```
cd src
git init
git add main
git commit -m "init"
```
Once that is completed, run the `applyPatchesGR` task. This will apply the patches to the source code.

**🎉  Congratulations! You're now ready to compile the project!**

### Compiling
To compile the project, run the `jar` task. This will compile the project to a jar file, which can be used to launch the game from the launcher.

**🎉 Congratulations! You're now ready to run the client!**

### Running (whilst in development)
You can run the client by running the `runClient` task. This is a task provided by MCP, and will run the client. But this is slow, and it does not support hot reloading.
If you are using IntelliJ, you can run the client by following the following steps:
1. Set up a new run configuration for the `mcp.client.Start` class. If you are unsure what this is, you can check the [IntelliJ documentation](https://www.jetbrains.com/help/idea/run-configurations.html).
2. Set the working directory to the `run` folder.
3. Set the classpath to `grcraft.main`

When you make change, make sure to press `Ctrl+F9` to build the project. This will compile the project and hot swap the new classes. This is much faster than restarting the client every time you make a change.

**🎉  Congratulations! You've just ran G_Rcraft!**

### Running (launcher)
Before you can run the client, you'll need to launch the vanilla client. To do this, open the launcher and click on the `Launch` button (G_Rcraft is currently on 1.18.1).

Once you have done that, you need to modify your compiled jar file. Follow the steps below to do so.
 1. Close any open launcher & game instances.
 2. Open your `.minecraft` folder. If you are not sure where this is, follow [this guide](https://minecraft.fandom.com/wiki/.minecraft) to find out.
 3. Go into the `versions` folder, and find the `1.18.1` folder.
 4. Copy the `1.18.1` folder, and rename it to `G_Rcraft-1.18.1`.
 5. Go into the `G_Rcraft-1.18.1` folder and open the ``1.18.1.jar`` file in an archive manager.
 6. Copy the `assets` & `data` folders to the `G_Rcraft-1.18.1` folder. These are the assets & data folders for the vanilla client.
 7. Copy the `pack.png` file to the `G_Rcraft-1.18.1` folder. This is the default pack icon.
 8. Remove the `1.18.1.jar` file from the `G_Rcraft-1.18.1` folder.
 9. Copy the compiled jar file to the `G_Rcraft-1.18.1` folder.
 10. Open the built jar file in an archive manager.
 11. Copy the directories `assets` & `data` into the built jar file.
 12. Copy the `pack.png` file into the built jar file.
 13. Rename the built jar file to `G_Rcraft-1.18.1.jar`.
 14. Open `1.18.1.json` in a text editor, and find the first instance of `"downloads":` This tells Minecraft where to obtain the game JAR file. If you leave this in, Minecraft will automatically download the vanilla JAR. But we want to run your new modded JAR. So delete everything from that `"downloads":` through the client, server, and server_mappings headers, which finally end in `/server.txt"}},`. Once you remove that, this section should hold `"assets": "1.18", "complianceLevel": 1, "id": "1.18.1".` The last thing we need to do in this JSON file is to change that ID field to match the name of the folder and the JSON file. So change it to `"id": "G_Rcraft-1.18.1"`.
 15. Save the file, and rename it to `G_Rcraft-1.18.1.json`.
 16. Open the Launcher again, and launch the new installation.

**🎉  Congratulations! You've just compiled a production build & ran G_Rcraft!**

### Optimizing development (IntelliJ)
To optimize your experience, you can switch to IntelliJ instead of Gradle. This will make building and running a lot faster. You can do this by following these steps:
1. Open the project in IntelliJ, make sure everything is set up correctly.
2. Open the Gradle settings window. If you are not sure what this is, you can check the [IntelliJ documentation](https://www.jetbrains.com/help/idea/gradle-settings.html).
3. Select the `Client` project.
4. Set all of the `Build and run` options to `IntelliJ IDEA`.

This should improve your build times, if you have any suggestions for how to improve your build times, please let us know!

### Are you having issues?
If you are having issues with G_Rcraft, you can check out the [G_Rcraft Discord](https://discord.gg/5Gcxq3JsgC) or [G_Rcraft GitHub Issues](https://github.com/GRcraft/Client/issues).