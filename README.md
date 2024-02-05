![Version](https://img.shields.io/badge/version-0.3.0-green)
![License](https://img.shields.io/badge/license-MIT-blueviolet.svg)

# EpChat

Epchat stand for : "Ephemeral Chat".

This is a side project used to explore Elixir and Websockets.

The goal is to create a basic real time chat application in Elixir allowing to create multiple ephemeral chat rooms.

One key feature is that there isn't any logs. No messages or rooms informations are saved to disk or database, this mean that there isn't any history on the server side at any point. The server side act only as a websocket events dispatcher.

For maintening the list of rooms, users and room members we will use an in memory sqlite database.

As it is an exercice to explore Elixir language, the webapp will be made with the minimum of dependencies : No Ecto, no PubSub, no Phoenix.Channels ... everything from scrach as much as possible.

Actual dependencies:

- [Bandit](https://hex.pm/packages/bandit) (http server and websocket handling)
- [WebsockAdapter](https://hex.pm/packages/websock_adapter) (upgrading http to websocket)
- [Exqlite](https://hex.pm/packages/exqlite) (to manage a in memory sqlite database)
- [Jason](https://hex.pm/packages/jason) (to encode/decode JSON format)

That's all.

# Requirements

- Elixir : 1.16.0 (or later)
- NodeJS : 20.9.0 (or later)

# Install

Clone the repository (and all submodules):

```console
git clone --recursive git@github.com:odelbos/epchat.git
```

TODO: Finish install process.

# Roadmap

- [X] User can create a room (he become the owner of the room)
- [X] Users can join a room using specific url link
- [X] Members exchange chat messages - (v0.1.0)
- [X] Handle when member leave a room. And closing a room - (v0.2.0)
- [X] Monitoring each rooms, auto close them if 10mn of inactivity - (v0.3.0)
- [X] Invit url link based on a token valid for 5mn with a one time usage - (v0.4.0)
- [X] Limit room members to 10 - (v0.5.0)
- [X] Add active_at to user (clean after 5days of inactivity) - (v0.6.0)
- [ ] Basic telemetry (nb of users, rooms, exchanged messages) - (v0.7.0)
- [ ] Explore basic end-to-end encryption (Web Crypto API), because why not? - (v0.8.0)
- [ ] Work on frontend design, look&feel - (v1.0.0)
- [ ] Move ChannelsMonitor into CleanupMonitor. - (v1.1.0)
- [ ] Ask room owner for the chat history, (see **Note 1** bellow). - (v1.2.0)

**Note 1** : Remember there isn't any way for the server to send the chat history, the only user who have the full chat history (in front side) is the room owner, because he is the first one to join the room.

# License

The project is open source and under the terms of the [MIT License](https://opensource.org/licenses/MIT).

# Author

@odelbos
