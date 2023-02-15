# Belua

Belua is a framework built for all the discord fans who wanted to create a bot, now possible!

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. See deployment for notes on how to deploy the project on a live system.

### Prerequisites

You'll need `discord.js^14` for this package

```java
npm install discordjs@14
```

### Installing

To start, create a directory for the app and enter it


```java
mkdir myDiscordBot
cd myDiscordBot
```

Then, create a `package.json` with
```java
npm init --yes
```
Then, install the belua package
```java
npm install belua
```

## Usage

Start with a very simple boiler-plate code
```javascript
import { beluaClient } from 'belua'

const client = new beluaClient(process.env.MY_TOKEN)
```
This code Imports the `beluaClient` class from the module and creates an instance of it.

### Command Usage
Once the client is initialised, you can start adding commands to it.

```javascript
import { beluaClient, beluaCommand, beluaCommandData } from 'belua'

// Some Prerequisites
function sleep(ms) {
  return new Promise((resolve) => {
    setTimeout(resolve, ms);
  });
}

let myClient = new beluaClient(process.env.MY_TOKEN)


await sleep(2000) //Ensure client has initialised

myClient.setCommand(new beluaCommand(
  'ping', 
  new beluaCommandData('ping', 'Responds with Pong!'), ((i) => {
  i.reply('Pong!')
})))


await myClient.registerCommands() // Register Commands
```
This code does the following
- Import the neccesary classes
- Sets up a sleep function and uses it to ensure the client has initialised
- Creates a new command called ping that has a name, description and a execution function that handles the command.
- Registers the commands with `registerCommands()`


## Deployment

To Run,
```java
node .
```
This starts up the node server

## Built With

* [DiscordJS](https://discord.js.org/#/) - Built using the discord javascript framework

## Versioning

We use [SemVer](http://semver.org/) for versioning.

## Authors

* **10xyz** -  [Github](https://github.com/10xyz-coder)

## License

This project is licensed under the MIT License.
