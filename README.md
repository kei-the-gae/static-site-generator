# Static Site Generator

This is a [guided project](https://www.boot.dev/courses/build-static-site-generator-python) I completed as a part of the Boot.dev back-end developer curriculum. The project is a simple static site generator that reads markdown files from a directory and generates a static HTML site from them. The project focuses on object-oriented and functional programming concepts, and as such avoids the use of external frameworks like Jekyll, Hugo, or Gatsby.

[![python](https://badgen.net/badge/python/3.13/blue?icon=https://s3.dualstack.us-east-2.amazonaws.com/pythondotorg-assets/media/files/python-logo-only.svg)](https://www.python.org)

## Features

- Reads markdown files from a directory
- Generates a static HTML site from the markdown files
- Supports custom CSS styles
- Supports custom images
- Supports custom JavaScript scripts
- Supports nested directories for organizing content

## Usage

Python 3.10 or later is required to run the static site generator.

### Local environment

Clone the repository and run the following command from the project root directory:

```bash
./main.sh
```

This will generate a static HTML site in the `docs` directory, from assets placed in the `static` directory and markdown files placed in the `content` directory. Sample content has been placed in both the `static` and `content` directories.

The script also runs a local HTTP server from Python's built-in `http.server` module, which serves the generated site at [http://localhost:8888](http://localhost:8888). Be sure to terminate the process with `Ctrl+C` when you are done to close the server and port.

### Deployment

You will need to edit the `./build.sh` script. Replace the text in quotes to the base url of your deployed site as so:

```
python3 src/main.py "BASE_URL/FOR/SITE"
```

Then, run the following command from the project root directory:

```bash
./build.sh
```

This will generate a static HTML site in the `docs` directory, from assets placed in the `static` directory and markdown files placed in the `content` directory, converting all href and src links to absolute links based on the base URL provided.

The `docs` directory can then be uploaded to your web server or hosting service of choice.

> **NOTE**: This generator does not support nested inline markdown elements for simplicity. It may throw a ValueError if it encounters nested inline markdown elements due to mismatched delimiters when parsing inline markdown.
