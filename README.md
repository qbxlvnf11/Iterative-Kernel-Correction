
Description
=============

#### - Blind Super-Resolution Problem
  - Assume that the degradation kernels are unavailable
  - Formulated as follows: $I^{LR} = (k \otimes I^{HR}) \downarrow_s + n$
    - $I^{HR}$ = HR image, $I^{LR}$ = LR image related by a degradation model, $\otimes$ = Convolution operation
    - $k$ = blur kenel, $\downarrow_s$ = downsampling operation, $n$ = additive noise

#### - Contributions of "Blind Super-Resolution With Iterative Kernel Correction"
  (1) Propose an intuitive and effective deep learning framework for blur kernel estimation in single image super resolution
  (2) Propose a new non-blind SR network using the spatial feature transform layers for multiple blur kernels
  (3) Test blind SR performance on both carefully selected blur kernels and real images: shows SOTA performance in blind SR problem
  
#### - Kernel mismatch problem
  - 
  - Bring regular artifacts (either over-sharpening or over-smoothing), which can be applied to correct inaccurate blur kernels
  
#### - SFTMD network
  - Kernel mismatch problem: bring regular artifacts (either over-sharpening or over-smoothing), which can be applied to correct inaccurate blur kernels
  - SR network architecture using spatial feature transform (SFT) layers to handle multiple blur kernels to alleiviate kernel mismatch problem
  - SFT layer provides affine transformation for the feature maps $F$ conditioned on the kernel maps $H$ by a scaling and shifting operation
    - $SFT(F, H) = \gamma \odot F + \beta$
  - Architecture
  
  <img src="https://user-images.githubusercontent.com/52263269/224941758-52f9c898-9fee-4c24-bc63-9d577756c680.png" width="60%"></img>

Contents
=============

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

#### - Blind Super-Resolution With Iterative Kernel Correction paper
```
@article{IKC,
  title={Blind Super-Resolution With Iterative Kernel Correction},
  author={Jinjin Gu et al.},
  journal={arXiv},
  year={2019}
}
```

#### - Blind Super-Resolution With Iterative Kernel Correction Github Page

https://github.com/yuanjunchai/IKC

https://github.com/Lornatang/SFTMD-PyTorch

Author
=============

#### - LinkedIn: https://www.linkedin.com/in/taeyong-kong-016bb2154

#### - Blog URL: https://blog.naver.com/qbxlvnf11

#### - Email: qbxlvnf11@google.com, qbxlvnf11@naver.com

