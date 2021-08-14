# [Redux](https://redux.js.org/)
<img src="./images/banner.png" alt="banner"/> 

## Reducer
```js
const reducer = (state = 0, action) => {
  switch (action.type) {
    case 'INC':
      return state + 1;
    default:
      return state;
  }
};

let state = reducer(undefined, { });

state = reducer(state, { type: 'INC' });
console.log(state); // 1

state = reducer(state, { type: 'INC' });
console.log(state); // 2
```
## Redux
```bash
> npm install redux
```
```js
import { createStore } from 'redux';

const reducer = (state = 0, action) => {
  switch (action.type) {
    case 'INC':
      return state + 1;
    default:
      return state;
  }
};

const store = createStore(reducer);

store.subscribe(() => {
  console.log(store.getState());
});

store.dispatch({ type: 'INC' });
store.dispatch({ type: 'INC' });
store.dispatch({ type: 'INC' });
```
### Example
```html
<!--index.html-->
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <title>Redux App</title>
  </head>
  <body>
    <div id="root">
      <h1 id="counter">0</h1>
      <button id="dec">DEC</button>
      <button id="inc">INC</button>
      <button id="rnd">RND</button>
    </div>
    <script src="index.js"></script>
  </body>
</html>
```
```js
// index.js
import { createStore } from 'redux';

const reducer = (state = 0, action) => {
  switch (action.type) {
    case 'INC':
      return state + 1;
    default:
      return state;
  }
};

const store = createStore(reducer);

store.subscribe(() => {
  console.log(store.getState());
});

store.dispatch({ type: 'INC' });
store.dispatch({ type: 'INC' });
store.dispatch({ type: 'INC' });
```