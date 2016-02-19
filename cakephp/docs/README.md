# Docker Images for CakePHP docs

- [Full version](https://github.com/cake17/docker/tree/master/cakephp/docs/full) : Sphinx with latex
- [Light version](https://github.com/cake17/docker/tree/master/cakephp/docs/light) : Sphinx only

# Build the Documentation with Docker

Go to the [full documentation](https://github.com/cakephp/docs/tree/3.0) for more information.

You can run all the commands to build the docs:

    # To build the html
    cd /path/to/your/local/docs
    docker run -it --rm -v $(pwd):/data cakephpfr/docs:light make html

    # To build the epub
    cd /path/to/your/local/docs
    docker run -it --rm -v $(pwd):/data cakephpfr/docs make epub

    # To build the latex
    cd /path/to/your/local/docs
    docker run -it --rm -v $(pwd):/data cakephpfr/docs make latex

    # To build the pdf
    cd /path/to/your/local/docs
    docker run -it --rm -v $(pwd):/data cakephpfr/docs make pdf

All the commands below will create and start containers and build the docs in
the `build` folder. The `--rm` flag will delete the container after run.
