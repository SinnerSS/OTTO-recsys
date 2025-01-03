# OTTO Recsys
## Requirements

- **NVIDIA GPU** with CUDA support
- **Docker** installed ([Install Docker](https://docs.docker.com/get-docker/))
- **NVIDIA Container Toolkit** ([Install instructions](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/install-guide.html))

---

## Installation 

### 1. Pull NVIDIA Merlin Docker Image

Pull the latest NVIDIA Merlin Docker image, which comes preloaded with libraries like cuDF, TensorFlow, and PyTorch for recommendation systems:

```bash
docker pull nvcr.io/nvidia/merlin/merlin-pytorch:23.12 
```
### 2. Run the Docker Container

Run the container:

```bash
docker run --gpus all -it --rm -p 8888:8888 -v $(pwd):/workspace
```


---
### 2. Clone the Repository

```bash
git clone https://github.com/your_username/OTTO-recsys.git
cd OTTO-recsys
```

### 3. Install python packages

```bash
pip install -r requirements.txt
```

### 4. Launch Jupyter Lab:

```bash
jupyter lab --ip=0.0.0.0 --allow-root
```

Access the notebook in your browser at `http://localhost:8888`.

## Running the Project

### 1. Install ([Kaggle OTTO dataset](https://www.kaggle.com/competitions/otto-recommender-system)) and extract to data/lb folder

> [!NOTE]
> To be able to run the pipeline using local validation, use the ([host script][https://github.com/otto-de/recsys-dataset]) to split the last week from train.jsonl
> and extract to data/cv folder

### 2. Run notebook according to pipeline preprocess -> word2vec/t4r/covisit -> xgboost
