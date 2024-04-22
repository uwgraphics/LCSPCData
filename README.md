# Low Cost Single Photon Camera Dataset

Dataset of measurements from a low-cost single-photon camera used in our CVPR 2024 paper "Towards 3D Vision with Low-Cost Single-Photon Cameras"

([Project Webpage](https://cpsiff.github.io/towards_3d_vision/) | [PDF](https://arxiv.org/pdf/2403.17801.pdf))

![teaser image](https://cpsiff.github.io/towards_3d_vision/img/teaser.png)

## Dataset
The dataset contains both real and simulated data. Real data contains posed captures from the AMS TMF8820. Simulated data is from our own simulator. Real-world captures were completed by attaching the sensor to a robot arm, which moves around the object while capturing measurements.

Not all real-world captures have ground truth. Those that do contain a .stl file and a .blend file of the ground truth mesh.

## File Format
Data is stored in .json files with the following format:
```
[
    {
        "reference_hist": [...], // (128,) array (real data only)
        "hists": [...], // (9, 128) array (real data) or (128,) array (simulated data)
        "pose": [...] // (4, 4) homogeneous transform from origin to sensor pose
    },
    {
        // repeat for as many measurements
    }
]
```
For real data, there are additional fields (e.g. sensor temperature, depth estimates, robot state). These can be ignored.

## Troubleshooting
If you run into trouble, please make an issue on this GitHub repo.

## Citation
If you use this dataset for published work, please cite our CVPR 2024 paper:
```
@article{Mu24Towards3DVision,
    title={Towards 3D Vision with Low-Cost Single-Photon Cameras}, 
    author={Fangzhou Mu and Carter Sifferman and Sacha Jungerman and Yiquan Li and Mark Han and Michael Gleicher and Mohit Gupta and Yin Li},
    year={2024},
    eprint={2403.17801},
    archivePrefix={arXiv},
    primaryClass={cs.CV}
}
```