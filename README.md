# Reproducible Package for _"Evaluating Wi-Fi Round Trip Time for Accurate Indoor Positioning with Android Smartphones"_

[![nbviewer](https://raw.githubusercontent.com/jupyter/design/master/logos/Badges/nbviewer_badge.svg)](https://nbviewer.org/github/matey97/evaluation-wifi-rtt/)
[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/matey97/evaluation-wifi-rtt/HEAD)

This repository is the reproducibility package for the _“Evaluating Wi-Fi Round Trip Time for Accurate Indoor Positioning with Android Smartphones"_ conference paper.

> D. Pérez Senosiain, M. Matey-Sanz and J. Torres-Sospedra, "Evaluating Wi-Fi Round Trip Time for Accurate Indoor Positioning with Android Smartphones". 


## Reproducibility

### Reproduce online
Click the on the "Binder" badge above to open an interactive Jupyter environment with all required software installed.


### Reproduce locally
Install Python 3.9, download the repository, open a command line in the root of the directory and install the required software by executing:

```bash
pip install -r requirements.txt
```

### Reproduce locally with Docker
Install [Docker](https://www.docker.com) for building an image based on a `Dockerfile` with a Jupyter environment and running a container based on the image.

Download the repository, open a command line in the root of the directory and:

1. Build the image:

```bash
docker build . --tag evaluation-wifi-rtt
```

2. Run the image:

```bash
docker run -it -p 8888:8888 evaluation-wifi-rtt
```

3. Click on the login link (or copy and paste in the browser) shown in the console to access to a Jupyter environment.

### Reproduce the analysis
Open the Jupyter Notebook (*.ipynb) file. You can execute the code to reproduce the obtained results.


## Repository structure

- [`01_DATA`](./01_DATA): contains CSV files used in the analyses.
  - [`01_rtt-poco.csv`](./01_DATA/01_rtt-poco.csv): RTT measurements collected with Xiaomi POCO F2 Pro (M2004J11G) at 1, 2, 3, 4 and 5 meters from the AP.
  - [`01_rtt-xiaomi-m2007.csv`](./01_DATA/01_rtt-xiaomi-m2007.csv): RTT measurements collected with Xiaomi Mi 10T Pro (M2007J3SG) at 1, 2, 3, 4 and 5 meters from the AP.
  - [`02_rtt-orientations.csv`](./01_DATA/02_rtt-orientations.csv): RTT measurements collected with Xiaomi POCO F2 Pro at 0.5 meters from the AP and five different orientations.
  - [`03_rtt-throttle.csv`](./01_DATA/03_rtt-throttle.csv): RTT measurements collected with Xiaomi Mi 10T Pro at 2 meters from the AP and sampling periods ranging from 500ms to 1ms.
  - [`04_basemap.jpg`](./01_DATA/04_basemap.jpg): map of research laboratory. It is used to draw the collection environment for the multiple emitters setting.
  - [`04_collection-environment.jpg`](./01_DATA/04_collection-environment.jpg): collection environment with the four deployed APs and the three reference locations.
  - [`04_P1-rtt.csv`](./01_DATA/04_P1-rtt.csv): RTT measurements collected with Xiaomi POCO F2 at reference point **P1** from four APs.
  - [`04_P2-rtt.csv`](./01_DATA/04_P2-rtt.csv): RTT measurements collected with Xiaomi POCO F2 at reference point **P2** from four APs.
  - [`04_P3-rtt.csv`](./01_DATA/04_P3-rtt.csv): RTT measurements collected with Xiaomi POCO F2 at reference point **P3** from four APs.
- [`02_RESULTS`](./02_RESULTS): contains figures generated from the analyses.
  - [`01_rtt-variability-poco.pdf`](./02_RESULTS/01_rtt-variability-poco.pdf): figure showing the temporal variability of the collected samples in the Xiaomi Poco F2 Pro.
  - [`01_rtt-variability-m2007.pdf`](./02_RESULTS/01_rtt-variability-m2007.pdf): figure showing the temporal variability of the collected samples in the Xiaomi Mi 10T Pro.
  - [`02_rtt-orientations.pdf`](./02_RESULTS/02_rtt-orientations.pdf): figure showing effect of the device orientation in the RTT measurements.
  - [`03_rtt-throttle.pdf`](./02_RESULTS/03_rtt-throttle.pdf): figure showing the number of successful RTT measurements on different sampling periods.
  - [`04_rtt-multiple-emitters.pdf`](./02_RESULTS/04_rtt-multiple-emitters.pdf): figure showing the variability of the RTT collected samples for each AP and reference position.
  - [`04_rtt-multiple-emitters.csv`](./02_RESULTS/04_rtt-multiple-emitters.csv): table with the mean estimated distance and real distance for each AP and reference position.
- [`analysis.ipynb`](./analysis.ipynb): Jupyter Notebook containing the executed analyses and results.
- [`analysis.html`](./analysis.html): Static HTML version of the Jupyter Notebook. It can be downloaded and opened in the web browser.
- [`Dockerfile`](./Dockerfile): a recipe for the computational environment using Docker.
- [`requirements.txt`](./requirements.txt): dependencies required to run the analysis.


## License

All contained code is licensed under the [Apache License 2.0](./LICENSE).

All data used in this repository is licensed under [Open Data Commons Attribution License](http://opendatacommons.org/licenses/by/1.0/).