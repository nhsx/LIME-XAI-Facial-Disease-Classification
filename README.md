# LIME-XAI-Facial-Disease-Classification
## NHSX Analytics Unit - PhD Internship Project

### About the Project

[![status: hibernate](https://github.com/GIScience/badges/raw/master/status/hibernate.svg)](https://github.com/GIScience/badges#hibernate)

This repository holds code for the NHSX Analytics Unit PhD internship project led by Anwesha Mohanty from April to July 2022

[Project Description - Explaining facial skin disease classification using LIME](https://nhsx.github.io/nhsx-internship-projects/explaining-classification-using-lime/)


### Data Sources
- Rosacea-Full-Face-300 (rff-300): The “rff-300” is a collection of images from various sources such as [Irish Dataset (confidential)](https://www.ucd.ie/charles/research/researchgroups/thepowelllab/) , SD-260, teledermatology websites and google image search results. 
- [Flicker Faces High Quality (FFHQ): FFHQ](https://arxiv.org/abs/1912.04958) is a collection full-face images of people with normal skin. 


_**Note:** No data, public or private are shared in this repository.  A suitable test image can be taken from [Here](http://www.elan-medical-clinic.co.uk/blog/rosacea-update-new-treatments-available/rosacea-advanced/) and saved in the data folder.

### Project Stucture

- The main code is found in the investigation folder
  - ffhqrffInceptionv3.ipynb uses the pre-trained [Inception v3](https://ieeexplore.ieee.org/document/7780677) as a base model and then fine tunes it using the rff-300 and FFHQ datasets in order to perform a classification for the prescence of Rosecea.
  - ffhqrffIncepv3_con.ipynb does the same as ffhqrffInceptionv3.ipynb but used pre-processed high contrast images.
  - Explain_working_con.ipynb conducts the LIME analysis by: 
      - creating superpixels for an image, 
      - creating randomly perturbed superpixel images from the original,
      - uses an ML classifer and the fine tuned inceptionv3 predictor,
      - calulates a distance between each perturbed image and the original,
      - computes weights for the importance of each superpixel,
      - shows the LIME explanation in terms of the most important superpixels.   
- The accompanying [report](./reports/report.pdf) is also available in the `reports` folder

### Built With

[![Python v3.8](https://img.shields.io/badge/python-v3.8-blue.svg)](https://www.python.org/downloads/release/python-380/)
- [keras v2.9.0](https://keras.io/)
- [tensorflow v2.9.1](https://www.tensorflow.org/)
- [scikit-image v0.19.3](https://scikit-image.org/)
- [scikit-learn v1.1.2](https://scikit-learn.org/stable/)

### Getting Started

#### Installation

To get a local copy up and running follow these simple steps.

To clone the repo:

`git clone https://github.com/nhsx/LIME-XAI-Facial-Disease-Classification.git`

To create a suitable environment:
- `virtualenv -p /usr/local/bin/python3.8 .venv`
- `source .venv/bin/activate`
- `pip install -r requirements.txt`

### Usage

This repo contains an investigation and therefore can't be used as an active tool.  

To run and tune the inceptionv3 classifiers you'll need to bring in a suitable dataset and have access to a GPU.  These notebooks have been left in their google colab form.  

However, if you just want to use the LIME implmentation then save a test.jpeg test image in the data folder and run Explain_working_con.ipynb to see how the superpixels are identified and weighted.

### Roadmap

See the [open issues](https://https://github.com/nhsx/LIME-XAI-Facial-Disease-Classification/issues) for a list of proposed features (and known issues).

### Contributing

Contributions are what make the open source community such an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

_See [CONTRIBUTING.md](./CONTRIBUTING.md) for detailed guidance._

### License

Distributed under the MIT License. _See [LICENSE](./LICENSE) for more information._

### Contact

To find out more about the [Analytics Unit](https://www.nhsx.nhs.uk/key-tools-and-info/nhsx-analytics-unit/) visit our [project website](https://nhsx.github.io/AnalyticsUnit/projects.html) or get in touch at [england.tdau@nhs.net](mailto:england.tdau@nhs.net).

<!-- ### Acknowledgements -->
