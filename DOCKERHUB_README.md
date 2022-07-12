# EarnApp Docker
### Docker Image for [EarnApp](https://earnapp.com)

Note: This is an unofficial build and comes with no warranty of any kind what so ever.
By using this image you also agree to BrightData's terms and conditions.

 works on ARM64 processors and Docker on Windows/WSL 

## Available Tags
1. `latest` - Built and updated daily
2. `hourly-latest` - Built and updated every hour at UTC 10th minute.
3. `lite` - A non-systemd image. (An already existing UUID is needed for this image.)

## How to:
1. Make a directory for earnapp data
    - `mkdir $HOME/earnapp-data`
2. Run the container
    - `docker run -d --privileged -v /sys/fs/cgroup:/sys/fs/cgroup:ro -v $HOME/earnapp-data:/etc/earnapp --name earnapp Ay0hCrypto/earnapp`
3. Get the UUID
    - `docker exec -it earnapp earnapp showid`
4. Copy and paste the app `UUID` in the [EarnApp Dashboard](https://earnapp.com/dashboard) 

### Compose
    1. Make a new directory, create a file named `docker-compose.yml` and paste the following into it.
```YML
version: "3.3"
services:
    app:
        image: fazalfarhan01/earnapp
        privileged: true
        volumes:
            - /sys/fs/cgroup:/sys/fs/cgroup:ro
            - ./etc:/etc/earnapp
```

#### Lite Version
Use the `lite` version if you don't want to run the container priviledged or having any of the issues [here](https://github.com/fazalfarhan01/EarnApp-Docker/issues/2).

```YML
version: "3.3"
services:
    app:
        image: fazalfarhan01/earnapp:lite
        volumes:
            - ./etc:/etc/earnapp
        environment:
            EARNAPP_UUID: YOUR_NODE_ID_HERE
```

2. Run `docker-compose up -d`

