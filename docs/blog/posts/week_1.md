---
date: 2024-05-31 
categories: [Internship]
authors: [nangosha]
draft: false
---

# Week 1: API Mocking

Imagine you were working on a frontend team and you needed a given API service so bad. To your disappointment, the service is still being built by the backend team and it will not be ready anytime soon. Actually, it could so happen that the service is down. So you think to yourself: How do I get around this? Enter API mocking!!

<!-- more -->
API mocking is a development approach that involves mimicking the behavior of an API, to allow you to test and develop applications without relying on real data. It enables you to create realistic examples to simulate the expected response of an API. It also allows one to decouple the frontend development from the API development.

### What are the benefits of API mocking?

1. **Faster development times** - Let’s say you’re building against an API service that has yet to be created. Without mocking, you would need to wait until the real data has been provided. This slows down the development of your application. By providing developers with a mocked environment to test their code and test data, they can quickly find bugs, fix them, and optimize your systems.

2. **Cost-effectiveness** - Third party API providers normally charge for their services at different price plans. Creating a mock API can be an economically feasible option if the team does not want to incur additional expenses, especially during the development stages.

3. **Privacy & security** - API mocking happens in the local environment, which provides an added level of security and privacy especially when working with sensitive data(such as user credentials and records). With API mocking, developers are working with fake data, reducing the risk of accessing sensitive information or leaking private data.

### What are some API mocking tools?
Common mocking tools include **Postman**, **Mock Service Worker**, **WireMock**, **json-server** etc.

### Enough with the literature, let us look at a simple example!

For this example, we shall be using **Mock Service Worker** since I think it is very simple to understand. Most of their docs can be found [here.](https://mswjs.io/)

We have an endpoint `GET https://api.nangosha.com/user` that we would like to mock and it returns the data below. Of course this endpoint does not exist but with mocking, we shall show that this will work.

```js
{
   "name": "Trevor James Nangosha",
   "message": "To be or not to be!",
   "status": "success"
}
```

- Install the dependency

```bash title="install"
# using npm....
npm install msw@latest --save-dev

#....or using yarn
yarn add -D msw
```

- Define a request handler that will be in charge of mocking our endpoint

```js title="handlers.js"
import { http, HttpResponse } from 'msw'
 
export const handlers = [
  http.get('https://api.nangosha.com/user', () => {
    return HttpResponse.json({
      "name": "Trevor James Nangosha",
      "message": "To be or not to be!",
      "status": "success"
    })
  }),
]
```

- We can then make calls to our mocked API. The server will listen to all calls to our endpoint and return our custom response.

```js title="server.js"
import { setupServer } from 'msw/node'
import { handlers } from './handlers'

const server = setupServer(...handlers)
server.listen()

async function app() {
  const response = await fetch('https://api.nangosha.com/user')
  const user = await response.json()
  console.log(user)
}
 
app()
```

- Run the application. This will return and print the mocked response without actually making a network request.

```bash title="run"
node server.js
```

Voilà, as simple as that! We are done making our first API mock.
