# Design goals

- Each stack has it's own internal network
- Each stack consists of integrated parts -- if services need to talk, they are in the same stack

## Immich

- hardware accelerated transcodes and recognition
- I use Intel iGPU on a 12400

## servarr

- api key autoshare
- call each component by hostname, not ip:port
    * so radarr connects to jackett by specifying jackett in url etc
