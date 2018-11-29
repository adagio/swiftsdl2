# Docker Container for the Apple's Swift programming language, includes sdl2

## SDL2

(Simple DirectMedia Layer)[https://www.libsdl.org/download-2.0.php]

## Using this docker image

### Build with Swift within container

Run inside your project

    docker run --rm -v $(pwd):/data swiftsdl2:4.2

The `-v $(pwd):/data` parameter maps the current directory to the `/data` volume

### Run the executable produced

    .build/x86_64-unknown-linux/debug/<target-name>

Yes, you can run the product in host 👌

## Recommendations

Create a `.build` folder inside your project

    mkdir .build

Give useful permissions to your `.build` folder

    chmod u+s .build

## About parameters in Dockerfile

    WORKDIR /data  
    VOLUME /data  
    CMD sh -c "swift build -Xswiftc -static-stdlib"

The coomand will be executed on `/data` directory, that maps to `/data` volume.
Remember that current directory on the host was mapped to `/data` volume with a parameter on `docker run` command.
