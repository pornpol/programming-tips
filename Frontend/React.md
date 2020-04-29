# REACT

## Redux

1. action

```javascript
import {
  HTTP_REGISTER_FETCHING,
  HTTP_REGISTER_SUCCESS,
  HTTP_REGISTER_FAILED,
} from '../constants';

export const setRegisterStateToFetching = () => ({
  type: HTTP_REGISTER_FETCHING,
});

export const setRegisterStateToSuccess = (payload) => ({
  type: HTTP_REGISTER_SUCCESS,
  payload,
});

export const setRegisterStateToFailed = () => ({
  type: HTTP_REGISTER_FAILED,
});

// For Register sequence fetch -> success/fail
export const register = (history, credential) => {
  return async (dispatch) => {
    dispatch(setRegisterStateToFetching());
    let result = await Axios.post(
      'http://localhost:8000/api/v1/auth/register',
      credential
    );
    if (result.data.message === 'ok') {
      dispatch(setRegisterStateToSuccess(result.data.data));
      history.push('/login');
    } else {
      dispatch(setRegisterStateToFailed());
    }
  };
};
```

1. reducer

```javascript
import {
  HTTP_REGISTER_FETCHING,
  HTTP_REGISTER_SUCCESS,
  HTTP_REGISTER_FAILED,
} from '../constants';

const initialState = {
  result: null,
  isFetching: false,
  isError: false,
};

export default (state = initialState, { type, payload }) => {
  switch (type) {
    case HTTP_REGISTER_FETCHING:
      return { ...state, result: null, isFetching: true, isError: false };

    case HTTP_REGISTER_SUCCESS:
      return { ...state, result: payload, isFetching: false, isError: false };

    case HTTP_REGISTER_FAILED:
      return { ...state, result: null, isFetching: false, isError: true };

    default:
      return state;
  }
};
```

1. combine reducer

```javascript
import registerReducer from './register.reducer';
import { combineReducers } from 'redux';

export default combineReducers({ registerReducer });
```

1. store & Provide

```javascript
import { createStore, applyMiddleware } from 'redux';
import thunk from 'redux-thunk';
import logger from 'redux-logger';
import reducers from './reducers';

const store = createStore(reducers, applyMiddleware(thunk, logger));
```

1. Provider

```javascript
import { Provider } from 'react-redux';

const ReduxApp = () => (
  <Provider store={store}>
    <App />
  </Provider>
);

ReactDOM.render(
  <React.StrictMode>
    <ReduxApp />
  </React.StrictMode>,
  document.getElementById('root')
);
```

1. Connect

```javascript
import { register } from '../../actions/register.action';
import { connect } from 'react-redux';

const Register = ({ history, register, registerReducer }) => {
  //Code
};

const mapStateToProps = ({ registerReducer }) => ({
  registerReducer,
});

const mapDispatchToProps = {
  register,
};

export default connect(mapStateToProps, mapDispatchToProps)(Register);
```

## Disqus

---

## Custom Hooks

- [React-hook-form](https://react-hook-form.com)
- [11 Useful Custom React Hooks for Your Next Web App](https://blog.bitsrc.io/11-useful-custom-react-hooks-for-your-next-app-c66307cf0f0c)

---
