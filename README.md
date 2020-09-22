# convol
Energy-based control system

This is a pedantic attempt at realizing multi-tenant, distributed interactions backed by data.

The implementation is browser-based (for ubiquity's sake) and is composed of:
- Local actor/action loop
- Local communication service
- Federated communication hub
- Federal actor/action resolver

```
function* loop() {
  while (active) {
    for (thing of things) setState(thing.update)
  }
}
```

```
webSocket.onmessage = msg=>setState(msg)
```

```
resolver.onStateChange = (update,convolution)=>{
  newState = setState(update)
  if (convolution !== newState) return {rejection: update, expectation: newState}
}
```
