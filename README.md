# Installation

 - Run these commands
     
     - git clone https://github.com/Tessellate-Imaging/Monk_Object_Detection.git
     
     - cd Monk_Object_Detection/5_pytorch_retinanet/installation
     
 - Select the right requirements file and run
 
     - cat requirements.txt | xargs -n 1 -L 1 pip install
 
 - go to {HOME]/.local/lib/python3.x/site-packages/torch/nn/modules/upsampling.py
 
 - change the following code in the forward method of Upsample class from -
   ```
   def forward(self, input: Tensor) -> Tensor:
     return F.interpolate(input, self.size, self.scale_factor, self.mode, self.align_corners,
       recompute_scale_factor=self.recompute_scale_factor
   )
   ```

   to this -
   ```
   def forward(self, input: Tensor) -> Tensor:
     return F.interpolate(input, self.size, self.scale_factor, self.mode, self.align_corners,
       #  recompute_scale_factor=self.recompute_scale_factor
    )
   ```
