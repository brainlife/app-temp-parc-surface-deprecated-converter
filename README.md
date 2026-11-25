<h1 align="center">Temporary converter of parcellation/surface-deprecated datatypes to surface datatypes</h1>

<p align="center">
  Converts the deprecated parcellation/surface datatype into the current surface/vertices and surface/data datatypes by copying and renaming files; a temporary format conversion utility.
</p>

<p align="center">
  <a href="https://github.com/brainlife/abcd-spec"><img src="https://img.shields.io/badge/ABCD_Spec-v1.1-green.svg" alt="ABCD Spec v1.1"></a>
  <a href="https://doi.org/10.25663/brainlife.app.582"><img src="https://img.shields.io/badge/Brainlife-brainlife.app.582-blue.svg" alt="Run on brainlife.io"></a>
  <a href="LICENSE"><img src="https://img.shields.io/badge/License-MIT-lightgrey.svg" alt="MIT license"></a>
</p>

> **This branch, `v1.0`, is the brainlife.io App Temporary converter of parcellation/surface-deprecated datatypes to surface datatypes** ([doi:10.25663/brainlife.app.582](https://doi.org/10.25663/brainlife.app.582)).

## At a glance

<!-- brainlife-app:begin (generated from the App manifest; edit the manifest, not this block) -->

> **Converts the deprecated parcellation/surface datatype into the current surface/vertices and surface/data datatypes by copying and renaming files; a temporary format conversion utility.**

Copies the left/right annotation files and label.json (and key.txt if present) into a surface/data output, and the inflated, pial and white surfaces into per-hemisphere folders of a surface/vertices output. No data are modified; use it only to migrate data created with the old datatype. Runs without a container.

| | |
|---|---|
| **Inputs** | `neuro/parcellation/surface-deprecated` |
| **Outputs** | `neuro/surface/vertices` · `neuro/surface/data` |
| **Run it** | [doi.org/10.25663/brainlife.app.582](https://doi.org/10.25663/brainlife.app.582) |

#### Inputs

| Input | Datatype | Required | Description |
|---|---|---|---|
| `parc_deprecated` | `neuro/parcellation/surface-deprecated` | yes | Deprecated surface parcellation: lh/rh annotation, inflated, pial and white surfaces, key and label files. |

#### Outputs

| Output | Datatype | Description |
|---|---|---|
| `surface_verts` | `neuro/surface/vertices` | left/ and right/ folders with the inflated, pial and white surfaces (<hemi>.<surface>.gii). |
| `surface_data` | `neuro/surface/data` | left.gii and right.gii parcellation data with label.json and key.txt. |

<!-- brainlife-app:end -->

## Running the App

### On brainlife.io

Open the App at [doi.org/10.25663/brainlife.app.582](https://doi.org/10.25663/brainlife.app.582), choose `neuro/parcellation/surface-deprecated` from your project and press **Execute**. The results are saved to your project as `neuro/surface/vertices`, `neuro/surface/data`.

### Locally

You need [`jq`](https://jqlang.github.io/jq/).

1. Clone this repository.
2. Create `config.json` with the paths to your inputs and the parameters:

   ```json
   {
       "lh_annot": "/path/to/parc_deprecated/lh_annot",
       "rh_annot": "/path/to/parc_deprecated/rh_annot",
       "lh_inflated": "/path/to/parc_deprecated/lh_inflated",
       "rh_inflated": "/path/to/parc_deprecated/rh_inflated",
       "lh_pial": "/path/to/parc_deprecated/lh_pial",
       "rh_pial": "/path/to/parc_deprecated/rh_pial",
       "lh_white": "/path/to/parc_deprecated/lh_white",
       "rh_white": "/path/to/parc_deprecated/rh_white",
       "key": "/path/to/parc_deprecated/key",
       "label": "/path/to/parc_deprecated/label"
   }
   ```

3. Run `./main`.

## Citing

If you use this App, please cite it, the software it builds on and brainlife.io:

- Temporary converter of parcellation/surface-deprecated datatypes to surface datatypes. brainlife.io App. [doi:10.25663/brainlife.app.582](https://doi.org/10.25663/brainlife.app.582)
- Hayashi S, Caron BA, Heinsfeld AS, et al. brainlife.io: a decentralized and open-source cloud platform to support neuroscience research. *Nature Methods* 21:809–813 (2024). [doi:10.1038/s41592-024-02237-2](https://doi.org/10.1038/s41592-024-02237-2)
- Avesani P, McPherson B, Hayashi S, et al. The open diffusion data derivatives, brain data upcycling via integrated publishing of derivatives and reproducible open cloud services. *Scientific Data* 6:69 (2019). [doi:10.1038/s41597-019-0073-y](https://doi.org/10.1038/s41597-019-0073-y)

## Authors

- Brad Caron

**Contributors**

- Soichi Hayashi

## Funding

[![Wellcome-226486/Z/22/Z](https://img.shields.io/badge/Wellcome-226486%2FZ%2F22%2FZ-purple.svg)](https://wellcome.org/)
[![NIH-NINDS-U24NS140384](https://img.shields.io/badge/NIH_NINDS-U24NS140384-green.svg)](https://reporter.nih.gov/project-details/11261037)
[![NIH-NINDS-UM1NS132207](https://img.shields.io/badge/NIH_NINDS-UM1NS132207-green.svg)](https://reporter.nih.gov/project-details/11411328)
[![NIH-NIBIB-R01EB029272](https://img.shields.io/badge/NIH_NIBIB-R01EB029272-green.svg)](https://reporter.nih.gov/project-details/10262925)
[![NIH-NIBIB-R01EB030896](https://img.shields.io/badge/NIH_NIBIB-R01EB030896-green.svg)](https://reporter.nih.gov/project-details/10428625)
[![NIH-NIMH-R01MH126699](https://img.shields.io/badge/NIH_NIMH-R01MH126699-green.svg)](https://reporter.nih.gov/project-details/10460628)
[![NIH-NIDCD-R01DC020088](https://img.shields.io/badge/NIH_NIDCD-R01DC020088-green.svg)](https://reporter.nih.gov/project-details/11140284)
[![NSF-BCS-1734853](https://img.shields.io/badge/NSF_BCS-1734853-blue.svg)](https://www.nsf.gov/awardsearch/showAward?AWD_ID=1734853)
[![NSF-BCS-2203524](https://img.shields.io/badge/NSF_BCS-2203524-blue.svg)](https://www.nsf.gov/awardsearch/showAward?AWD_ID=2203524)
[![NSF-IIS-1636893](https://img.shields.io/badge/NSF_IIS-1636893-blue.svg)](https://www.nsf.gov/awardsearch/showAward?AWD_ID=1636893)
[![NSF-OAC-2148729](https://img.shields.io/badge/NSF_OAC-2148729-blue.svg)](https://www.nsf.gov/awardsearch/showAward?AWD_ID=2148729)
[![NSF-IIS-1912270](https://img.shields.io/badge/NSF_IIS-1912270-blue.svg)](https://www.nsf.gov/awardsearch/showAward?AWD_ID=1912270)
[![NSF-IIS-2148700](https://img.shields.io/badge/NSF_IIS-2148700-blue.svg)](https://www.nsf.gov/awardsearch/showAward?AWD_ID=2148700)
[![NSF-OAC-1916518](https://img.shields.io/badge/NSF_OAC-1916518-blue.svg)](https://www.nsf.gov/awardsearch/showAward?AWD_ID=1916518)

<sub>brainlife.io is publicly funded, and acknowledging that support helps keep it running. This App was developed with support from Wellcome, the U.S. National Institutes of Health (including the BRAIN Initiative BRAIN CONNECTS program: The Axonal Projectome EXchange, U24NS140384, and the Center for Mesoscale Connectomics, UM1NS132207) and the U.S. National Science Foundation.</sub>

## License

See [LICENSE](LICENSE).
