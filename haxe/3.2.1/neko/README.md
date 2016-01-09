# Supported tags and respective `Dockerfile` links

- [`3.2.0`, `3.2.0-neko`, `latest`](https://github.com/cromo/dockerfiles/blob/master/haxe/3.2.0/neko/Dockerfile)
- [`3.2.0-cpp`](https://github.com/cromo/dockerfiles/blob/master/haxe/3.2.0/cpp/Dockerfile)
- [`3.2.0-cs`](https://github.com/cromo/dockerfiles/blob/master/haxe/3.2.0/cs/Dockerfile)
- [`3.2.0-java`](https://github.com/cromo/dockerfiles/blob/master/haxe/3.2.0/java/Dockerfile)
- [`3.2.0-php`](https://github.com/cromo/dockerfiles/blob/master/haxe/3.2.0/php/Dockerfile)
- [`3.2.0-python`](https://github.com/cromo/dockerfiles/blob/master/haxe/3.2.0/python/Dockerfile)

For more information about this image and its history, please see the [relevant git repository subdirectory (`haxe`)](https://github.com/cromo/dockerfiles/tree/master/haxe) in the [`cromo/dockerfiles` GitHub repo](https://github.com/cromo/dockerfiles).

# What is Haxe?

Haxe is an open source toolkit based on a modern, high level, strictly typed programming language, a cross-compiler, a complete cross-platform standard library and ways to access each platform's native capabilities.

> [wikipedia.org/wiki/Haxe](https://en.wikipedia.org/wiki/Haxe)

![logo](https://raw.githubusercontent.com/cromo/dockerfiles/master/haxe/logo.png)

# How to use this image

## Start a Haxe instance running your app

The most straightforward way to use this image is to use a haxe comtainer as both the build and runtime environment. In your `Dockerfile`, writing something along the lines of the following will compile and run your project:

    FROM cromo/haxe:3.2.0-neko
    COPY . /source
    WORKDIR /source
    RUN haxe -main Main -neko Main.n
    CMD ["neko", "Main.n"]

Then build and run the Docker image:

    docker build -t my-haxe-app .
    docker run -it --rm --name my-running-app my-haxe-app

## Compile your app inside the Docker container

There may be occasions where it is not appropriate to run your app inside a container. To compile, but not run your app inside the Docker instance, you can write something like:

    docker run --rm -v "$(pwd)":/source -w /source cromo/haxe:3.2.0-neko haxe -main Main -neko Main.n

This will add the current directory as a volume, set the working directory to the volume, and run the command `haxe -main Main -neko Main.n`. This tells haxe to compile the code in `Main.hx` and output a Neko bytecode file to `Main.n`. Alternatively, if you have a `build.hxml`, you can instead run `haxe` with the hxml file inside your container:

    docker run --rm -v "$(pwd)":/source -w /source cromo/haxe:3.2.0-neko haxe build.hxml

# License

View [license information](http://haxe.org/foundation/open-source.html) for the software contained in this image. The `Dockerfile`s themselves are under the [MIT license](https://github.com/cromo/dockerfiles/blob/master/LICENSE).

# Supported Docker versions

This image has been tested on Docker version 1.7.0.

Support for older versions (down to 1.0) is provided on a best-effort basis.

# User Feedback

## Documentation

Documentation for this image is stored in the [`haxe/3.2.0/neko` directory](https://github.com/cromo/dockerfiles/tree/master/haxe/3.2.0/neko) of the [`cromo/dockerfiles` GitHub repo](https://github.com/cromo/dockerfiles).

## Issues

If you have any problems with or questions about this image, please contact me through a [GitHub issue](https://github.com/cromo/dockerfiles/issues).

## Contributing

You are invited to contribute new features, fixes, or updates, large or small; I will do my best to process them as fast as I can.

Before you start to code, I recommend discussing your plans through a [GitHub issue](https://github.com/cromo/dockerfiles/issues), especiall for more ambitious contributions. this gives other contributors a chance to point you in the right direction, give you feedback on your design, and help you find out if someone else is working on the same thing.