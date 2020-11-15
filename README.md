# .NET VS Code Docker Debugging Settings

## Docker development:

### Run watcher, run source code on file change:
1. Build and compose app container
    ```sh
    docker-compose -f docker-compose.yml -f docker-compose.watch.yml up -d --force-recreate --build
    ```
2. Get a bash shell in the container running container: 
    ```sh
    docker exec -it dotnet-vscode-docker-debugging-settings /bin/bash
    ```
3. Run watcher:
    ```sh
    dotnet watch run
    ```
### Debug configuration:
1. Build and compose app container
    ```sh
    docker-compose -f docker-compose.yml -f docker-compose.debug.yml up -d --force-recreate --build
    ```
2. Get a bash shell in the container running container: 
    ```sh
    docker exec -it dotnet-vscode-docker-debugging-settings /bin/bash
    ```
3. Run assembly:
    ```sh
    dotnet run
    ```

### Release configuration:
1. Build and compose app container
    ```sh
    docker-compose up -d --force-recreate --build
    ```
2. Get a bash shell in the container running container: 
    ```sh
    docker exec -it dotnet-vscode-docker-debugging-settings /bin/bash
    ```
3. Run assembly:
    ```sh
    dotnet Example.dll
    ```

### Check logs:
```sh
docker-compose logs -ft app
```

## Local development:

### Run watcher, runs source code on file change:
```sh
dotnet watch run
```

### Run source code:
```sh
dotnet run
```
