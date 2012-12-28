# EventManager

  Higher level event management designed to facilitate fluent
  domain-specific event subscriptions.

  For example [component/events](https://github.com/component/events)
  uses `EventManager` to provide fluent dom node event subsciptions,
  while [component/delegates](https://github.com/component/delegates)
  does the same, however for delegated events.

  You can think of this as the "Event Emitter" of the abstract event mechanism.

## Installation

    $ component install component/event-manager

## API

  - [EventManager()](#eventmanager)
  - [EventManager.onbind()](#eventmanageronbindfnfunction)
  - [EventManager.onunbind()](#eventmanageronunbindfnfunction)
  - [EventManager.bind()](#eventmanagerbindeventstringmethodstring)
  - [EventManager.unbind()](#eventmanagerunbindeventstringmethodstring)

## EventManager()

  Initialize an `EventManager` with the given
  `target` object which events will be bound to,
  and the `obj` which will receive method calls.

## EventManager.onbind(fn:Function)

  Register bind function.

## EventManager.onunbind(fn:Function)

  Register unbind function.

## EventManager.bind(event:String, [method]:String)

  Bind to `event` with optional `method` name.
  When `method` is undefined it becomes `event`
  with the "on" prefix.

```js
 events.bind('login') // implies "onlogin"
 events.bind('login', 'onLogin')
```

## EventManager.unbind([event]:String, [method]:String)

  Unbind a single binding, all bindings for `event`,
  or all bindings within the manager.

```js
  events.unbind('login', 'onLogin')
  events.unbind('login')
  events.unbind()
```


## License

  MIT
