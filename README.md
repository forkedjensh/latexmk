Build LaTeX documents
=====================

This docker image can be used to build latex documents with latexmk.

License
-------

This Dockerfile is licensed under the creative commons license
[CC BY-SA](https://creativecommons.org/licenses/by-sa/4.0/deed.en).

Usage
-----

The container lifecycle has to be done for every latex source directory. Change
the container name `doc_latexmk` to something other for these directories.

Hint: The `sudo` command can be dismissed if the current user belongs to the
`docker` group.

### First build

Run

    $ sudo docker run -v $(pwd):/data/ --name doc_latexmk forkedjensh/ubuntu-latexmk

with any latexmk parameters as needed. These will be appended to the latexmk
command in the container. The `$(pwd)` directory in the volume parameter is the
directory where the latex source is located.

`latexmkrc` or `.latexmkrc` files will be honored.

### Following builds

For future builds simply run

    $ sudo docker start doc_latexmk

### Destroy the container

When things are finished and the container is no longer needed the command

    $ sudo docker rm doc_latexmk

destroys the container.
