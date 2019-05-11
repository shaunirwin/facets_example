# Examples of how to use Facets Dive to explore datasets

## Setting up

The following will provide the "basic" installation (i.e. if you want to just view tabular data in Facets Dive, without images):

Install [Miniconda](https://docs.conda.io/en/latest/miniconda.html).
Use Google Chrome browser only!

~~~ bash
git clone https://github.com/shaunirwin/facets_example.git
cd facets_example
conda env update -n facets_env
~~~

If you wish to view images in Facets Dive, there are two options:
1. Use Facets AtlasMaker to generate a sprite atlas from a folder of images
2. Manually generate the sprite atlas

### Option 1

Install [Bazel](https://docs.bazel.build/versions/master/install-ubuntu.html) for your platform.
Once done, install [Facets AtlasMaker](https://github.com/PAIR-code/facets/tree/master/facets_atlasmaker) as follows:

~~~ bash
git clone https://github.com/PAIR-code/facets/
source activate facets_env
cd facets/facets_atlasmaker
pip install -r requirements.txt
~~~

Build the sprite atlas (substitute in the correct path to your image list file, image dimensions and output folder):

~~~ bash
./bazel-bin/facets_atlasmaker/atlasmaker --sourcelist=image_paths.csv \
--output_dir=. --image_width=28 --image_height=28 \
--default_image_path=https://upload.wikimedia.org/wikipedia/en/d/d1/Image_not_available.png
~~~

### Option 2

It is also perfectly possible to manually create the *sprite atlas* using your own Python script or whatever. At the end of the day all you need to create is a single large .png mosaic image. This is what is demonstrated in the Jupyter Notebook.

## Running the Notebook

~~~ bash
source activate facets_env
jupyter notebook
~~~

## Troubleshooting

**Images are not being displayed**

It is possible that you are trying to read in the sprite atlas from the wrong location. The browser requires that the sprite atlas image be located in the directory from where your Jupyter Notebook is being run from or a subdirectory of that. Otherwise you can add extra HTML tags to satisfy the CORS requirements. See [here](https://github.com/PAIR-code/facets/blob/master/facets_dive/README.md#providing-sprites-for-dive-to-render) for details.

**Nothing is being displayed in the Jupyter Notebook when the cell is run**

Ensure that you are using Google Chrome. Firefox and other browsers do not work!

