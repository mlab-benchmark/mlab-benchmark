# Machine Learning Application Benchmark

![alt text](media/mlab_logo.png "MLAB")

<Description of benchmark>
The Machine Learning Application Benchmark (MLAB) has the aim of combining aspects relevant to machine learning (ML) and hardware in order to create a unique ML benchmark for the space domain. It consists of multiple applications spanning anomaly detection, radio modulation classification, object detection for optical and multispectral images in order to detect ships, airplanes and wildfires, and land use / land cover classification. For every application, submissions can be made to one of four categories:

- Open Hardware & Model
- Open Hardware & Closed Model
- Closed Hardware & Open Model
- Closed Hardware & Model

Thereby, "open" and "closed" refer to the option of using different hardware platforms or ML models. Note that the submission category "Closed Hardware & Model" aims to compare different pre- and postprocessing techniques and hardware components.

------
### [Click here to open the leaderboard]()


<!-- ### [Click here to open dataset overview](https://www.bgd.ed.tum.de/en/projects/mlab/modeldb.html) -->
------
## Applications

| Use Case       |  Task  |  Dataset  |  Reference ML Model  | Reference HW |
| :---- | :----------: | :-----------------------: | :-----------------: | :------------: |
| A |  Anomaly Detection  |  [SMAP & MSL](https://github.com/khundman/telemanom/tree/master)  |  N-BEATS  | Xilinx Zynq Ultrascale+ ZCU102 |
| B |  Radio Classification  |  [RadioML 2018.01A](https://www.deepsig.ai/datasets/)  |  ResNet 1d  | Xilinx Zynq Ultrascale+ ZCU102 |
| C |  Multispectral Object Detection  |  OroraTech Wildfire Dataset  |  VGG 16  | Xilinx Zynq Ultrascale+ ZCU102 |
| D |  Image Classification Heavy  |  [EuroSAT](https://github.com/phelber/eurosat)  |  DenseNet 161  | Xilinx Zynq Ultrascale+ ZCU102 |
| E |  Image Classification Light  |  [Aibus Ship Detection](https://www.kaggle.com/competitions/airbus-ship-detection)  |  Mobilenet  | Xilinx Zynq Ultrascale+ ZCU102 |
| F |  Image Object Detection  |  [Airbus Aircraft Detection](https://www.kaggle.com/datasets/airbusgeo/airbus-aircrafts-sample-dataset)  |  Mobilenet  | Xilinx Zynq Ultrascale+ ZCU102 |
| G |  Image Segmentation  |  [Aibus Ship Detection](https://www.kaggle.com/competitions/airbus-ship-detection)  |  ResNet 50  | Xilinx Zynq Ultrascale+ ZCU102 |


## Submission Process
You are welcome to participate in the benchmark by submitting your results on any of the applications. For a new submission, two files need to be prepared:
```json
configuration.json
{
    "task": {
		"use_case": "",
		"dataset": "",
		"target_metrics": [],
		"inference_scenario": "",
		"submission_category": ""
	},
	"system": {
		"device": "",
        "hardware_image": "",
		"os": "",
		"framework": "",
		"application_type": "",
		"relevant_drivers": [],
		"power_monitors": [],
		"reproducibility_guidelines": ""
	},
	"model": {
		"name": "",
		"architecture": ""
	},
    "link_to_project": ""
}
```
```json
metrics.json, e.g.
{
    "accuracy": "",
	"throughput": "",
	"energy": "",
	"peak_power": "",
	"idle_power": ""
}
```

Thereby, the task use case, dataset and target metrics are fixed for the existing applications and examples can be found for the reference implementations. The inference scenario refers to either "batch" or "stream" and the submission category has to be chosen as one or more of the 4 categories described above, specifying whether the hardware or model are allowed to be varied. Make sure to add a link to your project!

Once these two files have been prepared, a submission can be made via a pull request:

1. Clone directory and create new branch with \<unique name>
2. Create folder in /submissions/\<task>/\<submission category>/\<unique name>
3. Add configuration.json and metrics.json
4. Copy the newly created folder to /website/_data/submissions/\<task>/\<submission category>/\<unique name>
5. File a pull request to merge your branch into the main branch


## List of Publications
- Amir Raoofy, Gabriel Dax, Vittorio Serra, Max Ghiglione, Martin Werner, and Carsten Trinitis. 2022. Benchmarking and feasibility aspects of machine learning in space systems. In Proceedings of the 19th ACM International Conference on Computing Frontiers (CF '22). Association for Computing Machinery, New York, NY, USA, 225–226. https://doi.org/10.1145/3528416.3530986
- Andreas Koch, Michael Petry, Max Ghiglione, Amir Raoofy, Gabriel Dax, Gianluca Furano, Martin Werner, Carsten Trinitis, and Martin Langer. 2023. Machine Learning Application Benchmark. In Proceedings of the 20th ACM International Conference on Computing Frontiers (CF '23). Association for Computing Machinery, New York, NY, USA, 229–235. https://doi.org/10.1145/3587135.3592769
- Andreas Koch, Gabriel Dax, Michael Petry, Harvey Gomez, Amir Raoofy, Urvij Saroliya, Max Ghiglione, Gianluca Furano, Martin Werner, Carsten Trinitis, Martin Langer, "Reference Implementations for Machine Learning Application Benchmark," 2023 European Data Handling & Data Processing Conference (EDHPC), Juan Les Pins, France, 2023, pp. 1-3, doi: https://doi.org/10.23919/EDHPC59100.2023.10396582

