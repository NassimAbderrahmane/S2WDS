# SENTINEL2-FOREST-FIRES-DATASET

## Dataset for on-board detection of forest fires using sentinel-2 multi-spectral satellite imagery

<div id="top"></div>


<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of contents</summary>
  <ol>
    <li>
      <a href="#about-this-repository-">About this repository</a>
      <ul>
        <li><a href="#built-with-">Built with</a></li>
      </ul>
    </li>
    <li>
      <a href="#getting-started">Installation</a>
      <ul>
        <li><a href="#prerequisites">Prerequisites</a></li>
      </ul>
    </li>
    <li>
        <a href="#usage-">Usage</a>
        <ul>
            <li><a href="#demo-running">Running the demonstration</a></li>
            <li><a href="#data_structure">Data structure</a></li>
        </ul>
    </li>
    <li><a href="#license-">License</a></li>
    <li><a href="#contact-">Contact</a></li>
    <li><a href="#references-">References</a></li>
  </ol>
</details>



<!-- ABOUT THE PROJECT -->

## About this repository 💼

This git repository contains a demonstration of an active forest fire detection using a deep learning neural network model. The demonstration
consists of showing how to load the model and to make an inference on some sample images.

<p align="right">(<a href="#top">back to top</a>)</p>

### Built with 🧰

* [Anaconda](https://www.anaconda.com/products/distribution)
* [Python](https://www.python.org/)
* [Tensorflow](https://www.tensorflow.org/)
* [Skimage](https://scikit-image.org/)
* [Matplotlib](https://matplotlib.org/)
* [NumPy](https://numpy.org/)

<p align="right">(<a href="#top">back to top</a>)</p>


<!-- GETTING STARTED -->

## Installation

Follow these instructions to locally setup up your project:

1. Clone the repository : 
  ```sh
  git clone "https://github.com/hxfdanger/S2WDS.git"
  ```
 2. cd S2WDS/
 3. Create conda env using S2WDS_env.yml file : 
   ```sh
   conda env create -f S2WDS_env.yml
   ```
 4. Activate the conda environment : 
   ```sh
   conda activate S2WDS
   ```
 5. Download the model **wildfire_Unet_MobileNetv3_model_40m.h5** from [__here__](https://ciar.irt-saintexupery.com/index.php/s/NDXrX4eRKzkIPWD/download?path=%2F&files=wildfire_Unet_MobileNetv3_model_40m.h5).
 6. Create a folder "model" in the project's directory S2WDS/.
 7. Mouve the **wildfire_Unet_MobileNetv3_model_40m.h5** file to S2WDS/model.

🚨 To run conda commands, you have to install the [Anaconda distribution.](https://www.anaconda.com/products/distribution))

<p align="right">(<a href="#top">back to top</a>)</p>



<!-- USAGE EXAMPLES -->

## Usage 📒

### 1. Running the demonstration

The jupyter nootebook is not installed in the S2WDS env created by <a href="#prerequisites">S2WDS_env.yml </a> file.

🚨 To run the notebook **demo.ipynb** you have to install **jupyter** package in your active environment
```conda install -c anaconda jupyter```

🏁 Run the notebook [**demo.ipynb**](https://github.com/hxfdanger/S2WDS/blob/prepare_demo/demo.ipynb)

```bash
jupyter notebook demo.ipynb
```

**✍ NOTES:**

- [**demo.ipynb**](https://github.com/hxfdanger/S2WDS/blob/prepare_demo/demo.ipynb) will use some function declared in
  utils.py
- All images used for this demonstration are located in "data" folder. The structure of the data is described
  (<a href="#data_structure">bellow</a>).

### <div id="data_structure"> 2. Data structure</div>

```
./data/
├── false_color
│      ├── _Sentinel-2 L1C from 2017-12-08_SantaBarbara_BANDS-S2-L1C_0_5.tif
│      ├── _Sentinel-2 L1C from 2018-08-16_Mendocino_BANDS-S2-L1C_0_5.tif
│      └── _Sentinel-2 L1C from 2019-11-12_PortMacquarie2_BANDS-S2-L1C_0_77.tif
├── image_distribution
│      ├── test.txt
│      ├── train.txt
│      └── val.txt
├── masks
│      ├── _Sentinel-2 L1C from 2017-12-08_SantaBarbara_BANDS-S2-L1C_0_5.tif
│      ├── _Sentinel-2 L1C from 2018-08-16_Mendocino_BANDS-S2-L1C_0_5.tif
│      └── _Sentinel-2 L1C from 2019-11-12_PortMacquarie2_BANDS-S2-L1C_0_77.tif
└── RGB
       ├── _Sentinel-2 L1C from 2017-12-08_SantaBarbara_BANDS-S2-L1C_0_5.tif
       ├── _Sentinel-2 L1C from 2018-08-16_Mendocino_BANDS-S2-L1C_0_5.tif
       └── _Sentinel-2 L1C from 2019-11-12_PortMacquarie2_BANDS-S2-L1C_0_77.tif
```
**✍ NOTES:**

- The data folder only contains some examples used to run the demonstration.
- **false_color** folder contains 3 images composed of [B12,B11,B04] (sentinel2 bands), which are used as the input of the model for performing inference. 
- **RGB** contains 3 images corrsponding to false_color images composed of [B04,B03,B02] (sentinel2 bands), which are used only for visualization.
- **masks** folder contains 3 binary masks (**value : 0=no-fire; value : 1=fire**) corresponding to the images that are located in the false_color folder.
- Image_distribution folder contains 3 files :
  - train.txt : (empty), 
  - val.txt : (empty),
  - test.txt : contains the name of 3 images that are used for the inference.
- To download all the data, use this ([link](https://ciar.irt-saintexupery.com/index.php/s/NDXrX4eRKzkIPWD))
- For more information about the data, see ([link]()).

<p align="right">(<a href="#top">back to top</a>)</p>


<!-- LICENCE -->

## Licence 📑


Distributed under the Attribution 4.0 International (CC BY 4.0) Licence. 

Contains modified Copernicus Sentinel data [2016-2020] processed by Sentinel Hub.

<p align="right">(<a href="#top">back to top</a>)</p>



<!-- CONTACT -->

## Contact 📭

* [Houssem FARHAT 📧](mailto:houssem.farhat@irt-saintexupery.com)
* [Lionel DANIEL 📧](mailto:lionel.daniel@irt-saintexupery.com)
* [Michael BENGUIGUI 📧](mailto:michael.benguigui@irt-saintexupery.com)
* [Adrien GIRARD 📧](mailto:adrien.girard@irt-saintexupery.com)


Project link: [https://github.com/hxfdanger/S2WDS/](https://github.com/hxfdanger/S2WDS/)

<p align="right">(<a href="#top">back to top</a>)</p>



<!-- REFERENCES -->

## References 🔗 

<ol>
<li>
<div id="ref-FARHAT:2022" class="csl-entry" role="doc-biblioentry">
Houssem Farhat, Michael Benguigui, Lionel Daniel. 2022. <span>“Mod<span>è</span>le Et Jeu de Donn<span>é</span>es Pour La d<span>é</span>tection Multi-Spectrale de Feux de Forêt <span class="nocase">à</span> Bord de Satellites.”</span> In <em>PFIA 2022 - CNIA</em>, 1–8. Angers, France. <a href="">paper link</a>.
</div>
</li>
</ol>


<p align="right">(<a href="#top">back to top</a>)</p>
