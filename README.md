
Description
=============

#### - Contributions of "Blind Super-Resolution With Iterative Kernel Correction"
  - Propose an intuitive and effective deep learning framework for blur kernel estimation in single image super resolution
  - Propose a new non-blind SR network using the spatial feature transform layers for multiple blur kernels
  - Test blind SR performance on both carefully selected blur kernels and real images: shows SOTA performance in blind SR problem

#### - Blind Super-Resolution Problem
  - Assume that the degradation kernels are unavailable
  - Formulated as follows: $I^{LR} = (k \otimes I^{HR}) \downarrow_s + n$
    - $I^{HR}$ = HR image, $I^{LR}$ = LR image related by a degradation model, $\otimes$ = Convolution operation
    - $k$ = blur kenel, $\downarrow_s$ = downsampling operation, $n$ = additive noise
  
#### - Kernel mismatch problem
  - SR methods assume that the downsampling blur kernel is known and pre-defined, but the blur kernels involved in real applications are typically complicated and unavailable
  - Bring regular artifacts (either over-sharpening or over-smoothing), which can be applied to correct inaccurate blur kernels
  - Conversely, if the input kernel is sharper than the correct one, then the results will be over-shapened with obvious ringing effects as follow figure

  <img src="https://user-images.githubusercontent.com/52263269/224943466-9fa68182-18f5-4e87-90d1-33c6e324ed79.png" width="35%"></img>

#### - Iterative Kernel Correction
  - Proposed Iterative Kernel Correction (IKC) framework consists of a SR model F, a predictor P and a corrector C
  
  <img src="https://user-images.githubusercontent.com/52263269/224943989-de78014b-bf99-43f4-b10a-18c9adc644bf.png" width="45%"></img>

#### - SFTMD network, Predictor/Corrector
  - SFTMD network
    - SR network architecture using spatial feature transform (SFT) layers to handle multiple blur kernels to alleiviate kernel mismatch problem
    - Architecture of SFTMD
    
    <img src="https://user-images.githubusercontent.com/52263269/224941758-52f9c898-9fee-4c24-bc63-9d577756c680.png" width="65%"></img>
  
  - SFT layer
    - Affine transformation for the feature maps $F$ conditioned on the kernel maps $H$ by a scaling and shifting operation
    - $SFT(F, H) = \gamma \odot F + \beta$
  
  - Predictor/Corrector
    - Predictor: to adopt a predictor function $k` = P(I^{LR})$ that estimates k from the LR input directly
    - Corrector: To correctly estimate $k$, we build a corrector function $C$ that measures the difference between the estimated kernel and the ground truth kernel
    - Architecture of Predictor/Corrector
  
    <img src="https://user-images.githubusercontent.com/52263269/224945169-0dfb542a-637f-4245-84f2-8af73cc54406.png" width="65%"></img>

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

