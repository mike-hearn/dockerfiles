# Dockerfiles

This repo contains Dockerfiles for services and utilities that I
frequently use via Docker. Most of these are just small services that can
easily be containerized and don't need deep system access, and it's easier to
run them in a container than installing them (and their dependencies) on my
system directly. Combined with the Docker Hub, via `docker pull`, this saves me
time installing these utilities on fresh systems.

A good example of this is `tldr`, a program that shortens manpages down to
concise examples. Here is an example of it in action:

```
$ tldr zip

  zip
  Package and compress (archive) files into zip file.

  - Package and compress multiple directories and files:
    zip -r compressed.zip /path/to/dir1 /path/to/dir2 /path/to/file

  - Add files to an existing zip file:
    zip compressed.zip path/to/file

  - Remove unwanted files from an existing zip file:
    zip -d compressed.zip "foo/*.tmp"

  - Exclude unwanted files from being added to the compressed archive:
    zip -r compressed.zip path/to/dir -x \*.git\* \*node_modules\* ...
```


It is a Node program, which means to run it on a fresh
system, you need to install Node, and then install it via `npm`.

However, turning this into a Docker container means that the following command
will work on any system with Docker installed:

```
docker run --rm mikehearn/tldr
```

From there, simply aliasing `tldr` to this command means you never have to
worry about installing it again. It works on all machines with Docker
installed.

```
alias tldr="docker run --rm mikehearn/tldr"
```


