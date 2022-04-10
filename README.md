# Scripts for maintaining hiking OpenStreetMap data in Grenoble Alpes Métropole

## Installation

I recommend to install a Python environment with conda, virtualenv or pipenv.

### Create a Conda environment
For example with conda, 
[download and install miniconda](https://docs.conda.io/en/latest/miniconda.html)

Create a conda environment

```
conda create -n osm_gam_hiking python
```

Activate the conda environment

```
activate osm_gam_hiking
```

OR according your operating system

```
conda activate osm_gam_hiking
```

### Install requirements

Whatever your Python setup, install the requirement packages with the following command:

```
pip install -r requirements.txt
```

## Usage

Download the [Grenoble Alpes Métropole dataset](https://data.metropolegrenoble.fr/ckan/dataset/espnat_sentier_poteaux_metro) and put it in *data* directory.

It can be renamed with geojson extension like it is a geojson which can be read in https://geojson.io.

```
conflate guideposts.py -i data/POTEAUX_DIRECTIONNELS_SUR_SENTIERS_BALISES_EPSG4326_2022_02_14.geojson -o data/guidepost.osm -c data/guidepost.geojson
```

Filter the creation

```
python split_geojson.py data/guidepost.geojson
```

## License

The project has an [Apache-2.0 License](LICENSE).
