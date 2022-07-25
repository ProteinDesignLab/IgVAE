# Ig-VAE
## Author: Raphael R. Eguchi

The Ig-VAE is a variational autoencoder that directly generates the 3D coordinates of immunoglobulin backbones using a torsion- and distance-based loss function that is rotationally and translationally invariant. The model is trained on structures from [AbDb/AbYBank](http://www.abybank.org/abdb/). IgVAE is intended for use with existing protein design suites such as [Rosetta](https://www.rosettacommons.org/software). 

![figure_1_schematic scale=0.1](https://user-images.githubusercontent.com/10354479/171936661-8b2eb74b-b41b-450b-bc67-78536285c3f9.png)

### Requirements
Python 3.7  
See environment.yml

### Usage
```
python generate.py -n 100 -device cpu -seed 14 -outdir outputs/ 
```

### Interpolation Example
<p align="center">
<img src="https://user-images.githubusercontent.com/10354479/171932946-1ad954b3-8f4b-4dd0-8166-c07e4645ccb7.gif" width="300" height="300" />
</p>

### Notes
The environment uses CPU Pytorch, but the script is GPU-compatible via:
```
python generate.py -device cuda
```

### Citing and Licensing
This software is distributed under the BSD-3 license. The license file is available at license.txt.
This work was published in PLoS Computational Biology in 2022. Please reference it using the following citation:
```
@article{10.1371/journal.pcbi.1010271,
    doi = {10.1371/journal.pcbi.1010271},
    author = {Eguchi, Raphael R. AND Choe, Christian A. AND Huang, Po-Ssu},
    journal = {PLOS Computational Biology},
    publisher = {Public Library of Science},
    title = {Ig-VAE: Generative modeling of protein structure by direct 3D coordinate generation},
    year = {2022},
    month = {06},
    volume = {18},
    url = {https://doi.org/10.1371/journal.pcbi.1010271},
    pages = {1-18},
    abstract = {While deep learning models have seen increasing applications in protein science, few have been implemented for protein backbone generation—an important task in structure-based problems such as active site and interface design. We present a new approach to building class-specific backbones, using a variational auto-encoder to directly generate the 3D coordinates of immunoglobulins. Our model is torsion- and distance-aware, learns a high-resolution embedding of the dataset, and generates novel, high-quality structures compatible with existing design tools. We show that the Ig-VAE can be used with Rosetta to create a computational model of a SARS-CoV2-RBD binder via latent space sampling. We further demonstrate that the model’s generative prior is a powerful tool for guiding computational protein design, motivating a new paradigm under which backbone design is solved as constrained optimization problem in the latent space of a generative model.},
    number = {6},
}
```
