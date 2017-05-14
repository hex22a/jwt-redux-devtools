# JWT Redux Devtools
[![Build Status](https://travis-ci.org/hex22a/jwt-redux-devtools.svg?branch=master)](https://travis-ci.org/hex22a/jwt-redux-devtools)
[![Coverage Status](https://coveralls.io/repos/github/hex22a/jwt-redux-devtools/badge.svg?branch=master)](https://coveralls.io/github/hex22a/jwt-redux-devtools?branch=master)

Redux middleware to develop JWT-based apps

## Installation

`yarn add -D jwt-redux-devtools`

or `npm i --save-dev jwt-redux-devtools` if you are still using npm

## Usage

Import and add reducer

rootReducer.js
```javascript
import { combineReducers } from 'redux';
import { jwtReducer } from 'jwt-redux-devtools';

// something

export default combineReducers({
  ...jwtReducer,
});
```

Import middleware

configureStore.dev.js
```javascript
import { applyMiddleware, compose, createStore } from 'redux';
import jwtMiddleware from 'jwt-redux-devtools';

import rootReducer from '../rootReducer';
import actionTypes from '../actions/actionTypes';

// Action that contains token in payload
const { SIGN_IN_SUCCESS } = actionTypes;

// some of your code here

const enhancer = compose(
    applyMiddleware(jwtMiddleware([SIGN_IN_SUCCESS])),
);

// and maybe here

export default createStore(rootReducer, {}, enhancer);
```

## Contributing
PR's are welcome 👍

## Credits
Maintained by [hex22a](http://github.com/hex22a)

Twitter: [@hex22a](https://twitter.com/hex22a)
