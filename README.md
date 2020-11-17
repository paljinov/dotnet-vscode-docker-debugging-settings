# .NET VS Code Docker Debugging Settings

## Requirements

- docker-compose >= 1.27.4 (<https://docs.docker.com/compose/>)
- Docker (<https://docs.docker.com/engine/install/>)
- VSCode is optional, though the main point so...

An opinionated approach to developing applications with VSCode and
docker-compose. Designed for quick startup via

```sh
git clone https://github.com/paljinov/dotnet-vscode-docker-debugging-settings.git example
cd example
code .
```

Then simply select Run->Start Debugging or press F5

## Docker development

### Run watcher, run source code on file change

1. Build and compose app container

    ```sh
    docker-compose -f docker-compose.yml -f docker-compose.watch.yml up -d --force-recreate --build
    ```

2. Get a bash shell in the container running container:

    ```sh
    docker-compose exec app /bin/bash
    ```

3. Run watcher:

    ```sh
    dotnet watch run
    ```

### Debug configuration

1. Build and compose app container

    ```sh
    docker-compose -f docker-compose.yml -f docker-compose.debug.yml up -d --force-recreate --build
    ```

2. Get a bash shell in the container running container:

    ```sh
    docker-compose exec app /bin/bash
    ```

3. Run assembly:

    ```sh
    dotnet run
    ```

### Release configuration

1. Build and compose app container

    ```sh
    docker-compose up -d --force-recreate --build
    ```

2. Get a bash shell in the container running container:

    ```sh
    docker-compose exec app /bin/bash
    ```

3. Run assembly:

    ```sh
    dotnet Example.dll
    ```

### Check logs

```sh
docker-compose logs -ft app
```

## Local development

### Run watcher, runs source code on file change

```sh
dotnet watch run
```

### Run source code

```sh
dotnet run
```
