# create-redux-store
Util for create [redux](https://github.com/reactjs/redux) store
***
## installation:
```
npm install create-redux-store
```
***
## quick start:<br/>

### import:

`es5:`
```js
var createReduxStore = require('create-redux-store');
```
`es6:`
```js
import createReduxStore from 'create-redux-store';
```

### examples:

***creating***
```js
const store = createReduxStore(reduser,middleware);
```
```
reduser - Function or Object 
middleware - Function or the array of functions
```
***
***how it works***
```js
store.dispatch('test:action');
// set { type : 'test:action'}

store.dispatch(new Promise());
// promise.then(result => store.dispatch(result)
// promise.catch(error => store.dispatch({ type: '@@ERROR', error: error})

store.dispatch(new Error());
//set { type : '@@ERROR', error : Error }

store.dispatch([
  {
    type : 'test:action:1',
    payload : 'test:payload'
  },
  {
    type : 'test:action:2'
  },
    'test:action:3'
  ]);
```
>When the array is passed, subscribers will be called once after the last action is processed.

>Processing of actions for q and m remains the same.

>If NODE_ENV=development, [redux-devtools-extension](https://github.com/zalmoxisus/redux-devtools-extension) is automatically connected

***

### more tests

https://github.com/kkarifan/create-redux-store/tree/master/tests


***OR:***


> npm run test:redusers

> npm run test:string

> npm run test:error

> npm run test:promise

> npm run test:array

> npm run test:mixedarray

> npm run test:perf

> npm run test:mdw

> npm run test:objectmdw


***
