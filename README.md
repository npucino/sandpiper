<!-- PROJECT SHIELDS -->
<!--
*** I'm using markdown "reference style" links for readability.
*** Reference links are enclosed in brackets [ ] instead of parentheses ( ).
*** See the bottom of this document for the declaration of the reference variables
*** for contributors-url, forks-url, etc. This is an optional, concise syntax you may use.
*** https://www.markdownguide.org/basic-syntax/#reference-style-links
-->
[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
[![MIT License][license-shield]][license-url]
[![LinkedIn][linkedin-shield]][linkedin-url]



<!-- PROJECT LOGO -->
<br />
<p align="center">
  <a href="https://github.com/npucino/sandpiper">
    <img src="images/logo.png" alt="Logo" width="80" height="80">
  </a>

  <h3 align="center">Sandpiper - automatic UAV-SfM beach volumetric analysis</h3>

  <p align="justify">
    Sandpiper performs an organised and automatic extraction of elevation profiles from as many DSM and orthophotos as you like!
    It has some specialised functions to deal with the common limitations found in beach environments:
  <ol>
    <li>Swash zone: the water motion as waves wash in and out of the swash zone prevent Structure from Motion algorithm to find matches, thus, model elevation.</li>
    <li>Vegetation: both dune vegetation and beach wracks (macroalgae, woody debris) should be removed or filetered as can compromise sediment volumetric computation.</li>
    <li>File size: a few km long beach surveyed with a Phantom 4-Advanced at 100m altitude create roughly 10 Gb (uncompressed) of data, which can be cumbersome for some GIS to handle.</li>
  </ol>
  
  From user-defined cross-shore transects, you can clean profiles from unwanted non-sand points, detect significant hotspots/coldspots (cluster) of beach change, compute     volumetric dynamics at the site and transect levels, plot alongshore change and model beachface behaviour using the Beachface Cluster Dynamics indices.
  
  >**This code has supported the analysis and publication of the article ["Citizen science for monitoring seasonal-scale beach erosion and behaviour with aerial drones"](https://rdcu.be/cfgvu  "link to paper"), in the open access Nature Scientific Report journal.**


  <br />
  <a href="https://github.com/npucino/sandpiper"><strong>Explore the docs »</strong></a>
  <br />
  <a href="https://github.com/npucino/sandpiper">View Demo</a>
  ·
  <a href="https://github.com/npucino/sandpiper/issues">Report Bug</a>
  ·
  <a href="https://github.com/npucino/sandpiper/issues">Request Feature</a>
  </p>
</p>



<!-- TABLE OF CONTENTS -->
<details open="open">
  <summary><h2 style="display: inline-block">Table of Contents</h2></summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
      <ul>
        <li><a href="#Background">Background</a></li>
        <li><a href="#Modules">Modules</a></li>
      </ul>
    </li>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#Installation (temporary - will be a package in PyPI)">Installation (temporary - will be a package in PyPI)</a></li>
      </ul>
    </li>
    <li><a href="#usage">Usage</a></li>
    <li><a href="#roadmap">Roadmap</a></li>
    <li><a href="#contributing">Contributing</a></li>
    <li><a href="#license">License</a></li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="#publications">Publications</a></li>
    <li><a href="#acknowledgements">Acknowledgements</a></li>
   
  </ol>
</details>



<!-- ABOUT THE PROJECT -->
## About The Project

[![Product Name Screen Shot][product-screenshot]](https://example.com)

<!-- Background -->
### Background
This code has been developed to ease the analysis of big data coming from more than 300 Unnmanned Aerial Vehicles (UAV) surveys, performed by Citizen Scientist in Victoria, Australia. This is the [Eureka Award Winning](https://www.deakin.edu.au/about-deakin/media-releases/articles/eureka-prize-win-for-world-first-citizen-science-program) World-first [beach monitoring program powered by volunteers](https://www.marinemapping.org/vcmp-citizen-science "info on the Citizen Science project"), who autonomously fly UAVs on 15 sensitive sites (erosional hotspots) across the Victorian coast, every 6 weeks for 3 years, since 2018. This project is part of a broader marine mapping program called The [Victorian Coastal Monitoring Program (VCMP)](https://www.marineandcoasts.vic.gov.au/coastal-programs/victorian-coastal-monitoring-program "VCMP website"), funded by the [Victorian Department of Environment, Land, Water and Planning](https://www.delwp.vic.gov.au/ "DELWP website"), co-funded by [Deakin University](https://www.deakin.edu.au/ "Deakin Uni website") and [The University of Melbourne](https://www.unimelb.edu.au/ "UniMelb website").
***
Each survey creates Digital Surface Models and orthophotos of considerable size (5-10 Gb uncompressed), which can be troublesome for some GIS to render, let alone perform rster-based computations.

<!-- modules -->
### Modules

* **.outils**: main storage of useful functions.
* **.profile**: extract elevation and colour information across profiles from a folder of rasters.
* **.labels**: use KMean and Silhouette analysis to help clean the extracted elevation data from unwanted non-sand points.
* **.hotspots**: use Local Moran's I to disscard spatial outliers and obtain significant hot/cold spots of beach change at site and transect levels.
* **.dynamics**: compute Beachface CLuster Dynamics indices at the site and transect levels.
* **.volumetrics**: compute volumetric timeseries of sand-only points and create plots.
* **.space** (under development): simple satellite and UAV instantaneous waterlines tidal-correction and shoreline shifts/error metrics.



<!-- GETTING STARTED -->
## Getting Started

To get a local copy up and running follow these simple steps.

### Prerequisites
[Install Conda] in your local machine and use the [sandpiper_env.yml file ](../blob/master/sandpiper_env.yml) to create a suitable environment (will be named "sandpiper_env").
* in the Anaconda Prompt terminal, type:
  ```sh
  conda env create --file sandpiper_env.yml
  ```
  > The [richdem](https://pypi.org/project/richdem/ "richdem pypi page") package is the only one installed by PIP, which might cause an error.
  > If this is the case:
  > 1. Remove the attempted environment `conda remove --name sandpiper_env --all`
  > 2. Open sandpiper_env.yml and remove **richdem** from the requirement list, but leave **pip**
  > 3. Re-create the environment with the modified sandpiper_env.yml file `conda env create --file sandpiper_env.yml`
  > 4. Once created, activate the environment and `pip install richdem`

### Installation (temporary - will be a package in PyPI)

1. Clone the repo inside the environment **sandpiper_env** site-packages folder.
   ```sh
   git clone https://github.com/npucino/sandpiper.git
   ```
2. Once you open a Jupyter Notebook in 
   ```sh
   conda install
   ```



<!-- USAGE EXAMPLES -->
## Usage

TO DO.

_For more examples, please refer to the [Documentation](https://example.com)_



<!-- ROADMAP -->
## Roadmap

See the [open issues](https://github.com/npucino/sandpiper/issues) for a list of proposed features (and known issues).



<!-- CONTRIBUTING -->
## Contributing

Contributions are what make the open source community such an amazing place to be learn, inspire, and create. Any contributions you make are **greatly appreciated**.

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request



<!-- LICENSE -->
## License

Distributed under the MIT License. See `LICENSE` for more information.



<!-- CONTACT -->
## Contact

Nicolas Pucino - [@NicolasPucino](https://twitter.com/@NicolasPucino) - npucino@deakin.edu.au

Project Link: [https://github.com/npucino/sandpiper](https://github.com/npucino/sandpiper)


<!-- Publications -->
## Publications

* [Pucino, N. et al. Citizen science for monitoring seasonal-scale beach erosion and behaviour with aerial drones. Sci. Rep. 11, 1-19 (2021)](https://rdcu.be/cfgvu)

<!-- ACKNOWLEDGEMENTS -->
## Acknowledgements

* [Funding provided by Deakin University and the Victorian Department of Environment, Land, Water and Planning](https://www.marineandcoasts.vic.gov.au/coastal-programs/victorian-coastal-monitoring-program)
* [Deakin University Citizen Science program webpage](https://www.marinemapping.org/vcmp-citizen-science)






<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[contributors-shield]: https://img.shields.io/github/contributors/npucino/repo.svg?style=for-the-badge
[contributors-url]: https://github.com/npucino/repo/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/npucino/repo.svg?style=for-the-badge
[forks-url]: https://github.com/npucino/repo/network/members
[stars-shield]: https://img.shields.io/github/stars/npucino/repo.svg?style=for-the-badge
[stars-url]: https://github.com/npucino/repo/stargazers
[issues-shield]: https://img.shields.io/github/issues/npucino/repo.svg?style=for-the-badge
[issues-url]: https://github.com/npucino/repo/issues
[license-shield]: https://img.shields.io/github/license/npucino/repo.svg?style=for-the-badge
[license-url]: https://github.com/npucino/repo/blob/master/LICENSE.txt
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555
[linkedin-url]: https://www.linkedin.com/in/nicolaspucino/

[Install Conda]:https://www.anaconda.com/products/individual "Anaconda download website"
