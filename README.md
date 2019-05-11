# Examples of how to use Facets Dive to explore datasets

## Set up

The following will provide the "basic" installation (i.e. if you want to just view tabular data in Facets Dive, without images):

~~~ bash
git clone https://github.com/shaunirwin/facets_example.git
cd facets_example
conda env update -n facets_env
source activate facets_env
jupyter notebook
~~~

If you wish to view images in Facets Dive, you will also need to install Bazel to build the *atlas* of sprites:
~~~ bash
wget 
~~~

Note that it is also perfectly possible to manually create the *sprite atlas* using your own Python script or whatever. At the end of the day all you need to create is a single large .png mosaic image.

## Troubleshooting

**Images are not being displayed**
It is possible that you are trying to read in the sprite atlas from the wrong location. The browser requires that the sprite atlas image be located in the directory from where your Jupyter Notebook is being run from or a subdirectory of that. Otherwise you can add extra HTML tags to satisfy the CORS requirements. See [here](https://github.com/PAIR-code/facets/blob/master/facets_dive/README.md#providing-sprites-for-dive-to-render) for details.

