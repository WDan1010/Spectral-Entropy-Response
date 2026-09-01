# Data

This directory contains the source datasets and processed network data used in the study **“Spectral Entropy Response Reveals Multiscale Sensitivity of Network Diffusion to Early Node Damage.”**

## Directory overview

| Directory                   | Description                                                    |
| --------------------------- | -------------------------------------------------------------- |
| `communication_networks/`   | Original SNAP `email-Eu-core` communication network            |
| `empirical_brain_network/`  | Original publicly released MEG connectivity dataset            |
| `processed_brain_networks/` | Fifty subject-specific brain networks used in the SER analysis |

## Empirical brain network

The `empirical_brain_network` directory contains the publicly released MEG connectivity data associated with Guillon et al. (2017).

The dataset includes:

* 25 patients with Alzheimer's disease
* 25 age-matched healthy controls
* 7 frequency bands
* 148 cortical regions of interest based on the Destrieux atlas

The data consist of processed functional connectivity matrices derived from source-reconstructed resting-state MEG signals. Raw MEG recordings are not included.

The original data file was obtained from the Brain Network Toolbox:

[Brain Network Toolbox: Guillon2017.mat](https://github.com/brain-network/bnt/blob/develop/bntdata/Guillon2017.mat)

The source publication is:

> Guillon, J., Attal, Y., Colliot, O., La Corte, V., Dubois, B., Schwartz, D., Chavez, M., and De Vico Fallani, F. (2017). Loss of brain inter-frequency hubs in Alzheimer's disease. *Scientific Reports*, 7, 10879. https://doi.org/10.1038/s41598-017-07846-w

## Processed brain networks

The `processed_brain_networks` directory contains the 50 subject-specific brain networks used as inputs to the SER analysis. These networks were derived from the publicly released MEG connectivity matrices:

* 25 networks correspond to participants with Alzheimer's disease.
* 25 networks correspond to healthy control participants.

For the analyses reported in the study, each frequency layer was thresholded and binarized at equal density, corresponding to a mean intralayer degree of \(k=12\). The processed files are provided to preserve the exact network inputs used in the reported calculations.

These files are derived data prepared for the present study and should not be interpreted as raw MEG recordings.

## Communication network

The `communication_networks` directory contains the original `email-Eu-core` edge list downloaded from the Stanford Large Network Dataset Collection.

In the original dataset:

* nodes represent anonymized members of a European research institution;
* a directed edge from node \(u\) to node \(v\) indicates that member \(u\) sent at least one email to member \(v\);
* the network contains 1,005 nodes and 25,571 directed edges.

Original dataset page:

[SNAP: email-Eu-core network](https://snap.stanford.edu/data/email-Eu-core.html)

Original data download:

[email-Eu-core.txt.gz](https://snap.stanford.edu/data/email-Eu-core.txt.gz)

For the SER analysis, the directed network was converted into a simple undirected and unweighted graph. Self-loops were removed, reciprocal and duplicate edges were merged, and the largest connected component was retained. The resulting network contains 986 nodes and 16,064 undirected edges.

The communication dataset should be cited as:

> Yin, H., Benson, A. R., Leskovec, J., and Gleich, D. F. (2017). Local higher-order graph clustering. *Proceedings of the 23rd ACM SIGKDD International Conference on Knowledge Discovery and Data Mining*, 555–564. https://doi.org/10.1145/3097983.3098069

## Data attribution

The original datasets remain attributable to their respective authors and repositories. The processed brain networks were derived from the publicly released MEG connectivity matrices for the analyses reported in the associated study. All files are provided to support transparency and reproducibility.
