# **Do note that the README.md file (especially) and this repo is currently Under Construction**

# draughts-o-tron

[![Build Status](https://travis-ci.com/TheYoBots/draughts-o-tron.svg?branch=master)](https://travis-ci.com/TheYoBots/draughts-o-tron)
[![Dependency Status](https://david-dm.org/TheYoBots/draughts-o-tron.svg)](https://david-dm.org/TheYoBots/draughts-o-tron) 
[![devDependency Status](https://david-dm.org/TheYoBots/draughts-o-tron/dev-status.svg)](https://david-dm.org/TheYoBots/draughts-o-tron#info=devDependencies) 
[![CodeFactor](https://www.codefactor.io/repository/github/TheYoBots/draughts-o-tron/badge)](https://www.codefactor.io/repository/github/TheYoBots/draughts-o-tron) 
[![Open in Gitpod](https://img.shields.io/badge/Gitpod-Open%20in%20Gitpod-%230092CF.svg)](https://gitpod.io/#https://github.com/TheYoBots/draughts-o-tron)

Try out [lidraughts'](https://lidraughts.org) bot interface https://lidraughts.org/api#tag/Bot

### Setup

- Get an [API token](https://lidraughts.org/account/oauth/token) from lidraughts.org.

```bash
$ nvm use v10.15.3
$ yarn install

# Linux
$ export API_TOKEN=xxxxxxxxxx

# Windows
$ setx API_TOKEN xxxxxxxxxx
```

### Test

```bash
$ yarn test
```

### Run

```bash
$ yarn start
```

To implement your draughts bot you only need to create one class that implements the method:

```js
  getNextMove(moves) {
      return hubMove;
  }
```

Where moves is a list of moves so far in hub format e.g. `["e2e4", "b8c6", "f2f4"]`

See [`RandomPlayer`](src/bots/RandomPlayer.js) for minimal implementation using [draughts.js](https://github.com/shubhendusaurabh/draughts.js)

### Hosting

If you register a free heroku account you can host a BOT like this one as is - just add your `API_TOKEN` to the environment property configuration.
This code auto deploys and is live at https://test-o-a.herokuapp.com/

### Hostless

You do not need to own a server to host a BOT, this code also runs in a browser. Watch how a BOT communicates with the server https://tailuge.github.io/bot-o-tron/dist/testBot.html

### Tounaments

Compare bots locally - and the winner of the 8 x round-robin tournament is...

```bash
$ yarn tournament

Results
[ { player: 'AntiPatzerPlayer    ', score: 32.5 },
  { player: 'PatzerPlayer        ', score: 23 },
  { player: 'RandomPlayer        ', score: 22.5 },
  { player: 'SwarmKingPlayer     ', score: 18 } ]
```
