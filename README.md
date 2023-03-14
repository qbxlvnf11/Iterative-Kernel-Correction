
Description
=============

#### - Blind Super Resolution
  - 
  - 

Contents
=============

<img src="https://user-images.githubusercontent.com/52263269/176017021-514af297-0bba-4909-85b1-2629a7014586.png" width="45%"></img>

#### - Run test codes for SFTMD & IKC Methods in [official repository](https://github.com/yuanjunchai/IKC)
  - Configs
  -
  
Docker Environment
=============

#### - Download TensorRT Docker environment
```
docker pull qbxlvnf11docker/ikc_env:latest
```

#### - Run TensorRT Docker environment
```
nvidia-docker run --name IKC_env --gpus all -it -p 8888:8888 -e GRANT_SUDO=yes --user root -v {reposit_root_folder}:/workspace/IKC -v {data_folder}:/workspace/data -w /workspace/IKC pytorch/pytorch bash
```

Dataset
=============

#### - Download SR Dataset (DIV2K, Flickr2K, Set5, Set14, Urban100, BSD100)
  - [Download link](https://github.com/yuanjunchai/IKC#dataset-preparation)

#### - Generating All LRblur/LR/HR/Bicubic Data of each dataset (Set5, Set14, Urban100, BSD100) 
  - Default scale (up_scale, mod_scale): 4
  - Source data path lsit: set 'sourcedir_list' variable in line
  - Generated data path lsit: set 'savedir_list' variable in line
  - Run follow command in root folder
  ```
  python codes/scripts/generate_mod_LR_bic.py
  ```

Test SR
=============

#### - Download TensorRT Docker environment
```
docker pull qbxlvnf11docker/ikc_env:latest
```

#### - Download TensorRT Docker environment
```
docker pull qbxlvnf11docker/ikc_env:latest
```

References
=============

#### - IKC: Blind Super-Resolution With Iterative Kernel Correction Github

https://github.com/yuanjunchai/IKC

https://github.com/Lornatang/SFTMD-PyTorch

#### - YoloX paper
```
@article{IKC,
  title={Blind Super-Resolution With Iterative Kernel Correction},
  author={Jinjin Gu et al.},
  journal={arXiv},
  year={2019}
}
```

Author
=============

#### - LinkedIn: https://www.linkedin.com/in/taeyong-kong-016bb2154

#### - Blog URL: https://blog.naver.com/qbxlvnf11

#### - Email: qbxlvnf11@google.com, qbxlvnf11@naver.com

