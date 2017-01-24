# Mapzen documentation

Mapzen writes documentation in Markdown, stores the source files in GitHub, and uses a [MkDocs](http://www.mkdocs.org/)-based automated workflow to convert them into static-site documentation pages hosted at https://mapzen.com/documentation/. You can read more about this process in the [blog post](https://mapzen.com/blog/doc-site/).

## Build locally

Clone the repository locally and open a terminal window to the mapzen-docs-generator folder.

On a Mac, assuming you have [Homebrew](http://brew.sh) and 
[Python 3](https://docs.python.org/3/using/mac.html) installed, and a local
checkout of this repository:

```shell
# Prepare virtualenv and install local dependencies
brew install jq
virtualenv -p python3 venv
source venv/bin/activate
pip install -Ur requirements.txt

# Get all the sources and build all the documentation
make

# Use make clean for a fresh build

# Local preview
python -m http.server 8000
open http://localhost:8000/dist/
```

Run `make clean` to build a clean copy of the documentation. This command deletes the previous build and makes new files.

You may be able to build one section of the documentation using `make clean dist-projectname`, such as `make clean dist-tangram`.
