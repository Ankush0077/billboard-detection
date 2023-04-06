# Installation

 - Run these commands
     
     - git clone https://github.com/Ankush0077/billboard-detection.git
     
     - cd billboard-detection
     
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
