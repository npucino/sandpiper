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
        <li><a href="#built-with">Built With</a></li>
      </ul>
    </li>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#installation">Installation</a></li>
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

Here's a blank template to get started:


### Modules

* .outils: main storage of useful functions.
* .profile: extract elevation and colour information across profiles from a folder of rasters.
* .labels: use KMean and Silhouette analysis to help clean the extracted elevation data from unwanted non-sand points.
* .hotspots: use Local Moran's I to disscard spatial outliers and obtain significant hot/cold spots of beach change at site and transect levels.
* .dynamics: compute Beachface CLuster Dynamics indices at the site and transect levels.
* .volumetrics: compute volumetric timeseries of sand-only points and create plots.
* .space (under development): simple satellite and UAV instantaneous waterlines tidal-correction and error metrics.



<!-- GETTING STARTED -->
## Getting Started

To get a local copy up and running follow these simple steps.

### Prerequisites
HERE, the Requirments.txt file for COnda will be added.
* conda
  ```sh
  conda install geopandas
  ```

### Installation

1. Clone the repo
   ```sh
   git clone https://github.com/npucino/sandpiper.git
   ```
2. Install Conda packages
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

* [Pucino, N. et al. Citizen science for monitoring seasonal-scale beach erosion and behaviour with aerial drones. Sci. Rep. 11, 1-19 (2021)](www.nature.com/articles/s41598-021-83477-6)

<!-- ACKNOWLEDGEMENTS -->
## Acknowledgements

* [Deakin University Citizen Science program webpage](https://www.marinemapping.org/vcmp-citizen-science)
* [Funding provided by Deakin University and the Victorian Department of Environment, Land, Water and Planning](https://www.marineandcoasts.vic.gov.au/coastal-programs/victorian-coastal-monitoring-program)





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
