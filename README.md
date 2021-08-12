<link rel="stylesheet" href="https://olsk.rosano.ca/OLSKDecor/master/ui-style.css" />
<div class="OLSKCommonCard">
	<img src="https://remotestorage.io/img/icon.svg" role="presentation" />
	<div>
		<h1 style="margin: 0;">remoteStorage</h1>
		<span>An open protocol for per-user storage on the Web</span>
	</div>
</div>

---

# Features

## Own your data

Everything in one place – your place. Use a storage account with a provider you trust, or set up your own storage server. Move house whenever you want. It's your data.

## Stay in sync

remoteStorage-enabled apps automatically sync your data across all of your devices, from desktop to tablet to smartphone, and maybe even your TV.

## Compatibility & choice

Use the same data across different apps. Create a to-do list in one app, and track the time on your tasks in another one. Say goodbye to app-specific data silos.

## Go offline

Most remoteStorage-enabled apps come with first-class offline support. Use your apps offline on the go, and automatically sync when you're back online.

[Browse apps](/apps){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 } [Protocol details](/protocol){: .btn .fs-5 .mb-4 .mb-md-0 }

---

# Developer library

The [remoteStorage.js](https://github.com/remotestorage/remotestorage.js) library does most of the heavy lifting to add offline storage and cross-device synchronization to your apps. No more worrying about accounts, databases, passwords…

## Setup

```javascript
const api = new RemoteStorage({ modules: [{
	name: 'todoList',
	builder (privateClient, publicClient) {
	  return {
	    exports: {
	    	storeTodo (object) {
	    		return privateClient.storeObject('/' + object.id, object);
	    	},
	    },
	  };
	},
}] });

api.access.claim('todos', 'rw');

api.on('ready', function () {
   // ready
});
```

## Write an object

```javascript
// write `{"id":"alfa","done":false}` to /todos/alfa.json
await api.todoList.storeTodo({
	id: 'alfa',
	done: false,
});
```

## Connect to the Connect Widget UI component

Use our [drop-in UI widget](https://github.com/remotestorage/remotestorage-widget) for connecting storage accounts.

```javascript
const widget = new Widget(api);

widget.attach();
```

[Read the documentation](https://remotestoragejs.readthedocs.io){: .btn .fs-5 .mb-4 .mb-md-0 }

---

# Community

remoteStorage is a grass-roots standard, developed completely in the open, by the community for the community. Countless individuals have contributed in one way or another over time, and we'd love to welcome you as one of them!

|  |  |
| - | - |
| [GitHub](https://github.com/remotestorage) | Where we collaborate on the protocol specification as well as all common source code. |
| [Forums](https://community.remotestorage.io) | Our community exchange and support site for everybody from users to developers to providers. |
| [IRC](https://web.libera.chat/#remotestorage) | Some community members are hanging out in #remotestorage on Libera.Chat — say hi! |
| [Twitter](https://twitter.com/remotestorage_) / [Fediverse](https://kosmos.social/@remotestorage) | Follow the project on Twitter or on the Fediverse, to receive updates on releases, events, apps, and related news. |
| [Mailing List](https://buttondown.email/remotestorage)| A monthly digest about remoteStorage apps, tools, and decentralized news. |
| [Events](https://community.remotestorage.io/c/events) | Meet people in person at conferences, hackathons, camps, and other gatherings. |

We would love for you to get involved — check out [What can I do for remoteStorage?](https://wiki.remotestorage.io/What_can_I_do_for_remoteStorage%3F) for some ideas.

---

# Sponsors

<div class="sponsors">
<a href="https://nlnet.nl/" title="NLnet Foundation"><img src="https://remotestorage.io/img/sponsors/nlnet.svg" alt="NLnet Foundation" /></a> <a href="https://www.wauland.de/" title="Wau Holland Stiftung"><img src="https://remotestorage.io/img/sponsors/whs.svg" alt="Wau Holland Stiftung" /></a> <a href="https://5apps.com/" title="5apps"><img src="https://remotestorage.io/img/sponsors/5apps.svg" alt="5apps" /></a> <a href="https://duckduckgo.com/" title="DuckDuckGo"><img src="https://remotestorage.io/img/sponsors/duckduckgo2.svg" alt="DuckDuckGo" /></a>
</div>

<style>
.sponsors img {
 max-width: 128px !important;
}
</style>
