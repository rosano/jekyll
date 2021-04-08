[![remoteStorage](https://remotestorage.io/img/icon.svg)](https://remotestorage.io/)

-   [Get Storage](https://wiki.remotestorage.io/Servers)  
     - [Apps](https://wiki.remotestorage.io/Apps)  
     - [Develop](https://wiki.remotestorage.io/Developer_Portal)  
     - [Spec](https://wiki.remotestorage.io/Protocol)
    
-   [Wiki](https://wiki.remotestorage.io/)  
     - [Forums](https://community.remotestorage.io/)  
     - [GitHub](https://github.com/remotestorage)  
     - [Chat](https://kiwiirc.com/client/irc.freenode.net/#remotestorage)  
     - [Twitter](https://twitter.com/remotestorage_)  
     - [Fediverse](https://kosmos.social/@remotestorage)
    

![remoteStorage](https://remotestorage.io/img/icon.svg)

## remoteStorage

An open protocol for per-user storage on the Web

### Own your data

Everything in one place – your place. Use a storage account with a provider you trust, or set up your own storage server. Move house whenever you want. It's your data.

### Stay in sync

remoteStorage-enabled apps automatically sync your data across all of your devices, from desktop to tablet to smartphone, and maybe even your TV.

### Compatibility & choice

Use the same data across different apps. Create a to-do list in one app, and track the time on your tasks in another one. Say goodbye to app-specific data silos.

### Go offline

Most remoteStorage-enabled apps come with first-class offline support. Use your apps offline on the go, and automatically sync when you're back online.

### Unhosted Architecture

remoteStorage is the first open protocol to enable truly [unhosted](https://unhosted.org/) web apps. That means users are in full control of their precious data and where it is stored, while app developers are freed of the burden of hosting, maintaining and protecting a central database.

#### Traditional Web Apps

![Traditional web app](https://remotestorage.io/img/explainer-1-traditional-webapp-scoured.svg)

Traditional hosted web stack, for example LAMP/.Net/RoR/Django/etc.

Developer hosts app and data,  
user controls device.

#### [No-Backend](https://nobackend.org/) Web Apps

![Traditional web app](https://remotestorage.io/img/explainer-2-no-backend-scoured.svg)

100% client-side app plus CouchDB, Hoodie, Firebase, Parse, Kinto, etc.

Developer provides app and data,  
user controls device.

#### [Unhosted](https://unhosted.org/) Web Apps

![Traditional web app](https://remotestorage.io/img/explainer-3-unhosted-scoured.svg)

100% client-side app plus remoteStorage, Google Drive, Dropbox, etc.

Developer provides app only,  
user controls device and data.

### remoteStorage Protocol

remoteStorage is a creative combination of existing protocols and standards. It aims to re-use existing technologies as much as possible, adding just a small layer of standardization on top to facilitate its usage for per-user storage with simple permissions and offline-capable data sync.

![](https://remotestorage.io/img/webfinger-connect.png)

#### Discovery: [WebFinger](https://webfinger.net/)

In order for apps to know where to ask permission and later actually sync user data, users give them a user address, basically like with E-Mail or Jabber/XMPP. With that address, apps retrieve storage information for the username on that domain/host.

[Check out a live example for a 5apps user](https://client.webfinger.net/lookup?resource=tony%405apps.com).

![](https://remotestorage.io/img/oauth-dialog.png)

#### Authorization: [OAuth 2.0](https://oauth.net/)

User data is scoped by so-called categories, which are essentially base directories, for which you can give apps read-only or read/write permission. Apps will use OAuth scopes to ask for access to one or more categories.

In the example screenshot, [Litewrite](https://litewrite.net/) is asking for read/write access to the "documents" category, using the OAuth scope `documents:rw`. If you allow access, the app will retrieve a bearer token, with which it can read and write to your storage, until you revoke that access on your server.

![](https://remotestorage.io/img/screenshot-folder-description.png)

#### Data Storage & Sync: [HTTP REST](https://en.wikipedia.org/wiki/Representational_state_transfer)

remoteStorage defines a simple key/value store for apps to save and retrieve data. The basic operations are GET/PUT/DELETE requests for specific files/documents.

In addition to that – and the only special feature aside from plain HTTP – there are directory listings, formatted as JSON-LD. They contain both the content type and size, as well as ETags, which can be used to implement sync mechanisms. The files and listings themselves also carry ETag headers for sync/caching and conditional requests.

### Community

remoteStorage is a grass-roots standard, developed completely in the open, by the community for the community. Countless individuals have contributed in one way or another over time, and we'd love to welcome you as one of them!

#### [GitHub](https://github.com/remotestorage)

GitHub is where we collaborate on the protocol specification as well as all common source code.

#### [Forums](https://community.remotestorage.io/)

Our community exchange and support site for everybody from users to developers to providers.

#### [IRC](https://kiwiirc.com/client/irc.freenode.net/#remotestorage)

Many community members are hanging out in #remotestorage on Freenode. Say hi!

#### [Twitter](https://twitter.com/remotestorage_) / [Fediverse](https://kosmos.social/@remotestorage)

Follow the project on Twitter or on the Fediverse, to receive updates on releases, events, apps, and related news.

#### [Events](https://community.remotestorage.io/c/events)

Meet people in person at conferences, hackathons, camps, and other gatherings.

#### [Get involved!](https://wiki.remotestorage.io/What_can_I_do_for_remoteStorage%3F)

Want to make the world better by supporting RS in some way? Check out [What can I do for remoteStorage?](https://wiki.remotestorage.io/What_can_I_do_for_remoteStorage%3F) on our wiki.

### Sponsors

[![NLnet Foundation](https://remotestorage.io/img/sponsors/nlnet.svg)](https://nlnet.nl/ "NLnet Foundation")

[![Wau Holland Stiftung](https://remotestorage.io/img/sponsors/whs.svg)](https://www.wauland.de/ "Wau Holland Stiftung")

[![5apps](https://remotestorage.io/img/sponsors/5apps.svg)](https://5apps.com/ "5apps")

[![DuckDuckGo](https://remotestorage.io/img/sponsors/duckduckgo2.svg)](https://duckduckgo.com/ "DuckDuckGo")

© remoteStorage [contributors](https://github.com/remotestorage?tab=members) · Remix/redistribute under [CC-BY](https://creativecommons.org/licenses/by/4.0/) · [Fork this website](https://github.com/remotestorage/website) and help improve it!
