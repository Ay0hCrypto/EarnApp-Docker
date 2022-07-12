# EarnApp Docker
### Docker Image for [EarnApp](https://earnapp.com)

## Clone
```BASH
git clone https://github.com/ay0hcrypto/earnapp_docker.git
```
## Available Tags
1. `latest` - Built and updated daily

## How to:

1. Make a directory for earnapp data
    - `mkdir $HOME/earnapp-data`
2. Run the container
    - `docker run -d --privileged -v /sys/fs/cgroup:/sys/fs/cgroup:ro -v $HOME/earnapp-data:/etc/earnapp --name earnapp fazalfarhan01/earnapp` `
3. Get the UUID
    $ cd /root/earnapp-data
    $ cat UUID
    https://earnapp.com/r/SDK-NODE-ADDRESS-HERE

4. Provide the above web address to user to Link Device.
