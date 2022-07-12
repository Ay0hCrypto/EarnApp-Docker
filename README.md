# EarnApp Docker
### Docker Image for [EarnApp](https://earnapp.com)

## Clone
```BASH
git clone https://github.com/ay0hcrypto/earnapp_docker.git
```

## Available Tags
1. `latest` - Built and updated daily
2. `hourly-latest` - Built and updated every hour at UTC 10th minute.


## How to:

1. Make a directory for earnapp data
    - `mkdir $HOME/earnapp-data`
2. Run the container
    - `docker run -d --privileged -v /sys/fs/cgroup:/sys/fs/cgroup:ro -v $HOME/earnapp-data:/etc/earnapp --name earnapp fazalfarhan01/earnapp`
    `
3. Get the UUID
    - `docker exec -it earnapp showid`
4. Copy and paste the app `UUID` in the [EarnApp Dashboard](https://earnapp.com/dashboard) 

### Compose
1. Make a new directory, create a file named `docker-compose.yml` and paste the following into it.
```YML
version: '3.3'
services:
    app:
        image: fazalfarhan01/earnapp
        privileged: true
        volumes:
            - /sys/fs/cgroup:/sys/fs/cgroup:ro
            - ./etc:/etc/earnapp
```
2. Run `docker-compose up -d`

3. You can access the earnapp cli using the command
    ```BASH
    docker-compose exec app earnapp <YOUR COMMAND GOES HERE>

