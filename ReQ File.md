To support the research code, the following `requirements.txt` lists all core libraries necessary for Latent Diffusion Models (LDMs), the DDIM scheduler, and evaluation metrics used in the study.



 **Core Machine Learning Framework**

torch>=2.0.0

torchvision>=0.15.0

accelerate>=0.20.0



 **Diffusion and Model Handling**

diffusers>=0.18.0   Stable Diffusion v1.5 backbone and DDIM scheduler

transformers>=4.25.1   CLIP and text-encoder support



 **Image Processing and Numerical Operations**

numpy>=1.23.0

Pillow>=9.0.0

scipy>=1.9.0   Kernel synthesis and Gaussian RBF computation



 **Evaluation Metrics and Validation**

clip-anytorch>=2.5.0   Structural alignment evaluation

lpips>=0.1.4   Textural coherence evaluation

scikit-learn>=1.0.0   Statistical validation and bootstrap analysis



 **Visualization and Utilities**

matplotlib>=3.5.0

tqdm>=4.64.0



 **Key Dependencies**



&nbsp;Diffusers: Implements Stable Diffusion v1.5 and the DDIM scheduler, core to PLPI.

&nbsp;SciPy: Required for Procedural Kernel Synthesis, including Gaussian RBF and distance calculations.

&nbsp;CLIP \& LPIPS: Metrics used to quantify structural alignment and textural coherence improvements.

&nbsp;Accelerate: Enables mixed-precision (FP16/BF16) optimizations for efficient inference.



