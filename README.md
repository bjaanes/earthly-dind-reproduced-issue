# Earthly dind issue

Look at the testcontainers.test.js file, as it is the one starting a container.

It works fine both locally and inside devcontainer and Github Codespaces, but not inside Earthly.

It works just fine with the "hello-world" `WITH CONTAINER` setup, but not when the container gets triggered from within the test.

So the two things that work:
```shell
$ npm test
$ earthly +this-works
```

But this does not work:
```shell
$ earthly +this-does-not
```
