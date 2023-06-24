## Machine Learning for Earth Observation
A repository with some examples of machine learning applications in the domain of Earth Observation/remote sensing.
Specifically, the repository is meant for fine-tuning image classification on the EuroSAT dataset [1,2]. The goal is to leverage different packages, in order to check:

1. how easy they are to use
2. the quality of the results, vs. [3]

### Installation
```bash
conda create -n earthObs
conda activate earthObs
conda install -c fastchan fastai
pip install requirements.txt
```

(Note that the installation is specific for using miniconda, cfr. https://anaconda.org/fastai/fastai)

### Contents
Fine-tuning for the EuroSAT dataset with:
- Fast.ai: train_fast_vit.ipynb
- Timm: train_timm_vit.ipynb
- Hugging Face (+torch): train_hf_vit.ipynb
- TensorFlow: TODO

### Conclusion (preliminary)
The best results are through using Hugging Face's transformers package. This package is also relatively easy to use, well-documented and has a wide database of datasets and models.

For multi-specral and multi-temporal data, one should revert to base (Py)Torch/TensorFlow, as standard image processing NN/libraries focus on RGB data. Still, there are some recent interesting works that can be leveraged. One is from Li et al. {4] (though only multi-temporal), the other from Cong et al. [5]. The latter work is specifically for satellite imagery and provides code which can be reused [6].

### References
[1] P. Helber, B. Bischke, A. Dengel and D. Borth, "EuroSAT: A Novel Dataset and Deep Learning Benchmark for Land Use and Land Cover Classification," in IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing, vol. 12, no. 7, pp. 2217-2226, July 2019, doi: 10.1109/JSTARS.2019.2918242.

[2] P. Helber, B. Bischke, A. Dengel and D. Borth, "Introducing Eurosat: A Novel Dataset and Deep Learning Benchmark for Land Use and Land Cover Classification," IGARSS 2018 - 2018 IEEE International Geoscience and Remote Sensing Symposium, Valencia, Spain, 2018, pp. 204-207, doi: 10.1109/IGARSS.2018.8519248.

[3] Ivica Dimitrovski, Ivan Kitanovski, Dragi Kocev, Nikola Simidjievski, Current trends in deep learning for Earth Observation: An open-source benchmark arena for image classification, ISPRS Journal of Photogrammetry and Remote Sensing, Volume 197, 2023, Pages 18-35, ISSN 0924-2716, https://doi.org/10.1016/j.isprsjprs.2023.01.014. (https://www.sciencedirect.com/science/article/pii/S0924271623000205)

<div class="csl-entry">[4] Li, Z., Li, S., &#38; Yan, X. (2023). <i>Time Series as Images: Vision Transformer for Irregularly Sampled Time Series</i>. https://doi.org/https://doi.org/10.48550/arXiv.2303.12799</div>
<div class="csl-entry">[5] Cong, Y., Khanna, S., Meng, C., Liu, P., Rozi, E., He, Y., Burke, M., Lobell, D. B., &#38; Ermon, S. (2022). <i>SatMAE: Pre-training Transformers for Temporal and Multi-Spectral Satellite Imagery</i>. http://arxiv.org/abs/2207.08051</div>
<div class="csl-entry">[6] <i>GitHub - sustainlab-group/SatMAE: Official code repository for NeurIPS 2022 paper “SatMAE: Pretraining Transformers for Temporal and Multi-Spectral Satellite Imagery.”</i> (n.d.). Retrieved June 24, 2023, from https://github.com/sustainlab-group/SatMAE</div>