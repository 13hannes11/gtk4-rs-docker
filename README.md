# gtk4-rs-docker

This repository contains the build instructions for a rust libadwaita gtk app. And an example app.

## Image Building

To build the image go to the main repository and run:

```
docker build gtk4-rs-docker -t gtk4-rs-docker
```

## Compiling the example application

To compile the example application use docker-compose (note your system needs `libadwaita` to run the example application):

```
docker-compose up
```

## Using for your own application

To use this image for your own application simply copy the docker-compose file to your application directory and modify the path of the volume mount to your project directory:
You need to modify `./adwaita-demo` to that path in in the compose file):
```
    volumes:
      - ./adwaita-demo:/mnt:z
```

## Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.
