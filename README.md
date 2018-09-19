# redux-multiplication-middleware

[![Build Status](https://travis-ci.org/kamataryo/redux-multiplication-middleware.svg?branch=master)](https://travis-ci.org/kamataryo/redux-multiplication-middleware)
[![Build status](https://ci.appveyor.com/api/projects/status/yhpc128t9efo5b1k?svg=true)](https://ci.appveyor.com/project/kamataryo/redux-multiplication-middleware)

[![npm (scoped)](https://img.shields.io/npm/v/redux-multiplication-middleware.svg)](https://www.npmjs.com/package/redux-multiplication-middleware)
[![downloads](https://img.shields.io/npm/dt/redux-multiplication-middleware.svg)](https://www.npmjs.com/package/redux-multiplication-middleware)
[![Dependency Status](https://img.shields.io/david/kamataryo/redux-multiplication-middleware.svg?style=flat)](https://david-dm.org/kamataryo/redux-multiplication-middleware)
[![devDependency Status](https://img.shields.io/david/dev/kamataryo/redux-multiplication-middleware.svg?style=flat)](https://david-dm.org/kamataryo/redux-multiplication-middleware#info=devDependencies)

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

A Redux middleware to multiply certified state.

## install

```shell
$ npm i redux-multiplication-middleware -S
# or
$ yarn add redux-multiplication-middleware
```

## usage

```javascript
import { createStore, applyMiddleware, combineReducers } from 'redux'
import {
  createCountDispatchMiddleware,
  countDispatchReducer,
} from 'redux-multiplication-middleware'

const initialHelloState = { world: 'JavaScript' }

const helloReducer = (state = initialState, action) => {
  if (action.type === 'HELLO.SET') {
    return { ...state, world: action.payload.value }
  } else {
    return state
  }
}

const initialState = {}

const middlewares = [createCountDispatchMiddleware({ hello: { world: true } })]
const store = createStore(
  combineReducers({
    dispatchCounter: countDispatchReducer,
    hello: helloReducer,
  }),
  initialState,
  applyMiddleware(...middlewares)
)

store.dispatch({ type: 'HELLO.SET',  payload [MULTIPLE]: { index: 1 } })
store.getState().hello // 
```

## development

```shell
$ git clone https://github.com/kamataryo/redux-multiplication-middleware.git
$ cd redux-multiplication-middleware
$ npm test
```
