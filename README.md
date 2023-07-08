# Terraria-Server
Basic server setup using tshock for Terraria designed for a Raspberry Pi

## Requirements

Must use a 64 bit operating system on the Raspberry Pi

## Usage

Start by giving execution permissions to the setup, create-world, and launch scripts
```
chmod +x ./setup ./create-world ./launch
```

Run the setup script to install dependencies and make your system able to run TShock
```
./setup
```
- This should only be done once on a system as it will reinstall and add some clutter

TShock offers a lot of configuration. To create a simple world for use, run the create-world script. A world called "world" will be created and placed in the Worlds folder.
```
./create-world
```

You can change the name of the world to be created by modifying the script
```
nano create-world
```
- Look for WORLD_NAME="world"
- Use ctrl+s to save and ctrl+x to exit
- There are other basic configurations you can modify in the create world script for quick setup.
- Or look at the [tshock docs](https://ikebukuro.tshock.co/#/command-line-parameters) for more command line parameters

After setup is complete, just launch the server. NOTE: It looks for a world named "world" so when trying to launch a named world, make sure to edit the script first just like above with create-world.
```
./launch
```

## Other useful tools

### Screen
If you have the server running and you would like to ssh into the machine to see the logs or run commands, I recommend using screen. It allows you to run a task and put it in the background by detaching from it. You can later re-attach to interact again.

To install
```
sudo apt install screen
```

To use
```
screen
```

Once the server is running; detach with ctrl+a, d.

When you want to re-attach, use
```
screen -r
```
- If you have multiple instances of screen you will need to specify the id to re-attach

## References

[TShock Github](https://github.com/Pryaxis/TShock)

[Auto-restart with tmux](https://www.reddit.com/r/Terraria/comments/3gl5kk/installing_and_running_a_terraria_server_with/)

[The docs](https://ikebukuro.tshock.co/)