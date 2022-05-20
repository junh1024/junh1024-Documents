# Bittorrent Clients

## Introduction

BitTorrent supports partial segmented downloading and integrity-checking. It can be used to reliably transfer files between two computers with support for resuming broken transfers anytime. Some people will recommend nothing but kBT or qBT and use nothing but private sites. That is fine for them, but this document will focus on torrent clients for the rest of us.

## Clients
- **uTorrent** has a decent selection of features. It has a Web Ul. It has a unique feature of being able to easily save directly to a directory you specify instead of a subfolder. This is hugely beneficial for organization. Most other clients do not do this as easily or at all. 2.2 is the best version, since newer  versions have ads & more bugs. The RC exploit for 2.2 that was discovered some years ago is not a make a problem since it can only open dialogue box.
- **Picotorrent** supports sequential downloading. But as it has few features I would not recommend it as a primary client.
- **Azureus/Vuze** is a torrent for power users and has features like swarm visualisation, GUI peer blocking, and being a torrent tracker itself but is not allowed on many private sites.
- Http download managers and sites like IDM, zbigz, pikpak, terafile I'm not recommending since they do not support protocols like DHT, PEX, to get more peers.
- **kBT and qBT** may be fine for some people but not for public sites since they create categories for every tracker and your client will be cluttered with many sites
- **BiglyBT** is a next-gen torrent client and has a unique feature of combining 2 incomplete torrents to form a whole but this is a very niche feature
- **Aria 2** is a HTTP download manager which also supports BitTorrent. It's main advantage as a BitTorrent client is that is CLI, which is an advantage in some situations
- **Deluge torrent** is another GUI client which has a web Ul
- **Transmission** is another client which has a simplified mac-like interface. It can also act like a Damon+client architecture so you can have a uTorrent-like GUI
