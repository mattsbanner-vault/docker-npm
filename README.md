# NPM
**NPM in a lightweight Debian based container.**

I like to run everything I can within Docker, that way when I'm switching between Mac & Linux, I have exactly the same environment. That's why I've built this repository and the subsequent images on [DockerHub](https://hub.docker.com/r/mattbanner/npm/tags).

## Executing NPM
To execute NPM within Docker, you first need to decide on a Docker image [tag](https://hub.docker.com/r/mattbanner/npm/tags) to use. They're all named appropriately depending on which versions of Node and NPM they contain.

There's no need for the `npm` prefix as that's where the container starts. 

## Executing

```shell script
$ docker run --rm -it -v $PWD:/app -v ~/.npm/:/root/.npm mattbanner/npm:10.x-latest install
```

## Alias It!
That's a pretty lengthy command to have to type every time you need to update some packages. Therefore I have this aliased to the command `npm` on my machine. I've actually uninstalled NPM locally; yet I can still run `npm install` just like anyone else.

```
alias npm='docker run --rm -it -v $PWD:/app -v ~/.npm/:/root/.npm mattbanner/npm:10.x-latest install'
```
