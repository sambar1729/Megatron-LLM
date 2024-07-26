## How to convert phi3
Code is in launch.json
 or in `convert_phi3_ckpt.sh`

Run 
```
./convert_phi3_ckpt.sh
```

This produces the file in `~/tmp-phi`

Move it to `sambroy/pretraining/checkpoints/` in the posttraining container 

For megaflection:
```
cp -r tmp-phi /mnt/posttraining/sambroy/pretraining/checkpoints/phi3-megatron-iter0
```

### Loading the model
```
import torch

model = torch.load("/home/aiscuser/tmp-phi/model_iter_000000_mp_rank_000_000_000_optim_rng.pt")
```