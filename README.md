# React Circuit

Official React bindings for [Circuit](https://github.com/khirayama/circuit).

## Installation

```
npm install --save @khirayama/react-circuit
```

## Documentation

[Documents](documents.md)

## Examples

Ref: [Examples](https://github.com/khirayama/circuit/tree/master/examples/count-with-react-circuit)

```
createStore({total: 0}, (state, action) => {
  switch (action.type) {
    case 'COUNT_UP':
      state.total += 1;
      break;
    case 'COUNT_DOWN':
      state.total -= 1;
      break;
    default:
      break;
  }
  return state;
});

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
