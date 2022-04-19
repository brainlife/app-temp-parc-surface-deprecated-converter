[![Abcdspec-compliant](https://img.shields.io/badge/ABCD_Spec-v1.1-green.svg)](https://github.com/brain-life/abcd-spec)
[![Run on Brainlife.io](https://img.shields.io/badge/Brainlife-brainlife.app.582-blue.svg)](https://doi.org/10.25663/brainlife.app.582)

# Temporary converter of parcellation/surface-deprecated datatypes to surface datatypes

This app will convert the brainlife parcellation/surface-deprecated datatype into a surface/vertices and surface/data datatype. This is needed as the datatype for surface data was updated internally.

### Authors

- Brad Caron (bacaron@utexas.edu)

### Contributors

- Soichi Hayashi (shayashi@iu.edu)

### Funding Acknowledgement

brainlife.io is publicly funded and for the sustainability of the project it is helpful to Acknowledge the use of the platform. We kindly ask that you acknowledge the funding below in your publications and code reusing this code.

[![NSF-BCS-1734853](https://img.shields.io/badge/NSF_BCS-1734853-blue.svg)](https://nsf.gov/awardsearch/showAward?AWD_ID=1734853)
[![NSF-BCS-1636893](https://img.shields.io/badge/NSF_BCS-1636893-blue.svg)](https://nsf.gov/awardsearch/showAward?AWD_ID=1636893)
[![NSF-ACI-1916518](https://img.shields.io/badge/NSF_ACI-1916518-blue.svg)](https://nsf.gov/awardsearch/showAward?AWD_ID=1916518)
[![NSF-IIS-1912270](https://img.shields.io/badge/NSF_IIS-1912270-blue.svg)](https://nsf.gov/awardsearch/showAward?AWD_ID=1912270)
[![NIH-NIBIB-R01EB029272](https://img.shields.io/badge/NIH_NIBIB-R01EB029272-green.svg)](https://grantome.com/grant/NIH/R01-EB029272-01)

### Citations

We kindly ask that you cite the following articles when publishing papers and code using this code.

1. Avesani, P., McPherson, B., Hayashi, S. et al. The open diffusion data derivatives, brain data upcycling via integrated publishing of derivatives and reproducible open cloud services. Sci Data 6, 69 (2019). https://doi.org/10.1038/s41597-019-0073-y

#### MIT Copyright (c) 2020 brainlife.io The University of Texas at Austin and Indiana University

## Running the App

### On Brainlife.io

You can submit this App online at [https://doi.org/10.25663/brainlife.app.582](https://doi.org/10.25663/brainlife.app.582) via the 'Execute' tab.

### Running Locally (on your machine)

1. git clone this repo

2. Inside the cloned directory, create `config.json` with something like the following content with paths to your input files.

```json
{
    "lh_annot": "/input/parc_deprecated/lh_annot.gii",
    "rh_annot": "/input/parc_deprecated/rh_annot.gii",
    "lh_inflated": "/input/parc_deprecated/lh_inflated_surf.gii",
    "rh_inflated": "/input/parc_deprecated/rh_inflated_surf.gii",
    "lh_pial": "/input/parc_deprecated/lh_pial_surf.gii",
    "rh_pial": "/input/parc_deprecated/rh_pial_surf.gii",
    "lh_white": "/input/parc_deprecated/lh_white_surf.gii",
    "rh_white": "/input/parc_deprecated/rh_white_surf.gii",
    "key": "/input/parc_deprecated/key.txt",
    "label": "/input/parc_deprecated/label.json"
}
```

### Sample Datasets

You can download sample datasets from Brainlife using [Brainlife CLI](https://github.com/brain-life/cli).

```
npm install -g brainlife
bl login
mkdir input
bl dataset download
```

3. Launch the App by executing 'main'

```bash
./main
```

## Output

The main output of this App is a surface/vertices datatype containing the data containing to surfaces (i.e. pial, white, inflated) and a surface/data datatype which contains the surface-mapped data.

#### Product.json

The secondary output of this app is `product.json`. This file allows web interfaces, DB and API calls on the results of the processing.

### Dependencies

This App only requires [singularity](https://www.sylabs.io/singularity/) to run. If you don't have singularity, you just need access to a terminal with the 'cp' command.

#### MIT Copyright (c) 2020 brainlife.io The University of Texas at Austin and Indiana University
