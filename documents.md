# React Circuit

Official React bindings for [Circuit](https://github.com/khirayama/circuit).

## Table of Contents

- React Circuit
  - class: Container
    - container.dispatch

## API

### Class: Container

`Container` is component extended `React.Component`.  
It has circuit's `store.state` as `this.state` and subscribe updating `store.state`.  
When update `store.state`, `Container` map `store.state` to `this.state` and call `render` via `this.setState`.  
Use this with `extends`.

#### container.dispatch(action)

- `action` `<Object>` The action object

Dispatch action object.
Alias for circuit's `store.dispatch`. If call this before `createStore`, throw error.

```javascript

export default class CountContainer extends Container {
  render() {
    return (
      <section>
        <h1>Count: {this.state.total}</h1>
        <CountButton onCountButtonClick={countUp(this.dispatch)}>Count up +1</CountButton>
        <CountButton onCountButtonClick={countDown(this.dispatch)}>Count down -1</CountButton>
      </section>
    );
  }
}

```
