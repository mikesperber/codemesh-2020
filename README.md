## CodeMesh 2020
# Functional Software Architecture

You don't need to download and run code on your own computer, but it
may be helpful to do so.  In that case, you should make some
preparations.

If there are problems with the setup, e-mail Mike Sperber.

# Preparation

If you have a working Haskell/Cabal setup for ghc 8.8, things might
just work.  (ghc 8.10 will not work.)

Otherwise:

- install [Docker](https://www.docker.com/)
- give Docker at least 6GB RAM where relevant
- install [Visual Studio Code](https://code.visualstudio.com/download)
- install VS Code Extension "Remote - Containers" 
- select  "View" -> "Command Palette" (some modifiers + P), type
  "containers",  select"Remote - Containers: Open Folder in Container"
- open the `hearts` directory

VS Code will then construct a container to do its business.  That
might also take while.

# Starting the Game

## Console

The `Sync` module has two functions `gameAlong` and
`gameInteractive`. (Very rudimentary.)

## UI version

- in the `hearts` directory, run `./docker-shell.sh` to start a
  suitable shell in a Docker container

- inside the Docker container, do `cabal build` to build the server

- inside the Docker container, do `./run-server-inside-docker.sh` to
  start the server
  
- *outside* the Docker container:

- install [Elm](https://elm-lang.org/)

- cd to `hearts-frontend`, do:

```
elm reactor
```

- go to the URL there, typically
  [`http://localhost:8000`](http://localhost:8000)
  
- click on `examples`, then `HeartsFrontend.elm`
