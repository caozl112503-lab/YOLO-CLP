# YOLO-CLP Model Testing Instructions

This package provides the trained YOLO-CLP model and sample UAV images for detecting healthy and pest-damaged cotton leaves.

## Download and setup

1. Open [YOLO-CLP Releases](https://github.com/caozl112503-lab/YOLO-CLP/releases) and download `YOLO-CLP-review.zip` from the **Assets** section of the release.
2. Extract the archive to a folder with an ASCII-only path. Open a terminal in the extracted directory containing `insect_detect.py`.
3. Activate a Python 3.8 environment and run `python -m pip install -r requirements.txt`. For GPU inference, use CUDA-enabled builds of PyTorch 2.1.0 and torchvision 0.16.0 compatible with your NVIDIA GPU environment.

## Run inference

Run the following command to test the sample images on the first CUDA GPU.

```bash
python insect_detect.py --weights model_weights/best.pt --source sample_test_images --data data/insect.yaml --imgsz 640 640 --conf-thres 0.25 --iou-thres 0.45 --device 0
```

If a CUDA GPU is unavailable, replace `--device 0` with `--device cpu`. .
