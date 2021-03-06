# fuse-torrent

[![npm version](https://badge.fury.io/js/fuse-torrent.svg)](https://badge.fury.io/js/fuse-torrent)

It is a working progress project, use it with precaution.

**fuse-torrent** is based on [torrent-mount](https://github.com/mafintosh/torrent-mount)
but it allows mounting several torrents at the same time.

To mount several torrents at the same time without hit the performance of the network it relies upon **SQLite** to
cache the metadata of the torrents, so then, torrent-playing only connect to the torrent swarm when the filesystem tries to read a file. After some time of inactivity torrent-playing disconnect of the swarm.

## NOTES
- fuse-bindings does not work with latest node, use node v10 for now

## Install
```
$ npm install -g fuse-torrent
```

You also need to install fuse. See [this link](https://github.com/mafintosh/fuse-bindings#requirements) for more info.

## Usage

```
$ fuse-torrent db-prepare
$ fuse-torrent mount $HOME/torrentfs
$ fuse-torrent add "magneturl"
$ fuse-torrent addtorrent x.torrent
```

Check help for more info:

```
$ fuse-torrent --help
```

Watch the [demo](https://youtu.be/XyFWidfHkYY).

After doing that open mount directory using a file browser. The torrents should be mounted there now and you should be able to double-click them to start streaming as regular files!

BTW: It works pretty well with Plex.

![MIND BLOWN](https://media.giphy.com/media/1AePOBF3JaxKtI96pY/giphy.gif)

## TODO

- [ ] Update to fuse-native to support latest node
- ---
- [ ] Better documentation.
- [ ] Pool for connected torrents.
- [ ] Clean cached data for `torrent-stream`.
- [ ] Avoid duplicates by infohash.
- [ ] Allow more parameters on cli.
- [ ] Configuration by file.
- [ ] Add version to cli.
