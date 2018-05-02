<p align="center"><img src="https://cldup.com/7umchwdUBh.png" /></p>

<h3 align="center">The official Strapi SDK for JavaScript, available for browsers or Node.js backends.</h3>

---

<p align="center">
    <a href="https://travis-ci.org/strapi/strapi-sdk-javascript"><img src="https://img.shields.io/travis/strapi/strapi-sdk-javascript.svg?style=for-the-badge" /></a>
    <a href="https://github.com/strapi/strapi-sdk-javascript/releases"><img src="https://img.shields.io/github/release/strapi/strapi-sdk-javascript.svg?style=for-the-badge" /></a>
    <a href="https://codecov.io/gh/strapi/strapi-sdk-javascript"><img src="https://img.shields.io/codecov/c/github/strapi/strapi-sdk-javascript.svg?style=for-the-badge" /></a>
</p>

<br>

## Install

```sh
npm install strapi-sdk-javascript
```

## Start now

```js
import Strapi from 'strapi-sdk-javascript';

const strapi = new Strapi('http://localhost:1337');

(async () => {
  // Local authentication
  await strapi.login('username_or_email', 's3cr3t');

  // Or within provider
  window.location = strapi.getProviderAuthenticationUrl('facebook')
  // ...
  // Once authorized, Facebook redirects the user to your app with an access token in the URL.
  // Complete the authentication: (The SDK will handle the access token for you)
  await strapi.authenticateProvider('facebook')

  // You can now fetch private APIs
  const posts = await strapi.getEntries('post');
  console.log(`Posts count: ${posts.length}`);
})();
```

## API

### `Strapi(baseURL, storeConfig, requestConfig)`
### `request(method, url, requestConfig)`
### `register(username, email, password)`
### `login(identifier, password)`
### `forgotPassword(email, url)`
### `resetPassword(code, password, passwordConfirmation)`
### `getProviderAuthenticationUrl(provider)`
### `authenticateProvider(provider, params)`
### `setToken(token, comesFromStorage)`
### `clearToken(token)`
### `getEntries(contentType, params)`
### `getEntry(contentType, id)`
### `createEntry(contentType, data)`
### `updateEntry(contentType, id, data)`
### `deleteEntry(contentType, id)`
### `searchFiles(query)`
### `getFiles(params)`
### `getFile(id)`
### `upload(data)`

#### requestConfig

Custom axios request configuration. [See documentation](https://github.com/axios/axios#request-config)

## Resources

* [Documentation](https://strapi.github.io/strapi-sdk-javascript)
* [Changelog](https://github.com/strapi/strapi-sdk-javascript/blob/master/CHANGELOG.md)
* [Medium story](https://medium.com/strapi/announcing-the-strapi-javascript-sdk-ac89f140a9d1)

## Roadmap

* GraphQL
* Attach/Detach entry relationship
* Real time with Socket.io

## Credits

* [axios](https://github.com/axios/axios)
* [typescript-starter](https://github.com/bitjson/typescript-starter)

## License

MIT
