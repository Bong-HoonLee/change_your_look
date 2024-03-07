# change_your_look

#### project purpose
- The goal is to play with AI so that you don't feel intimidated by it.

#### target customer
- People who want to have fun changing the way they look or the way they want someone to look

#### How to play
1. Install the dependencies
   ```
      conda create -n stargan-v2 python=3.6.7
      conda activate stargan-v2
      conda install -y pytorch=1.4.0 torchvision=0.5.0 cudatoolkit=10.0 -c pytorch
      conda install x264=='1!152.20180717' ffmpeg=4.0.2 -c conda-forge
      pip install opencv-python==4.1.2.30 ffmpeg-python==0.2.0 scikit-image==0.16.2
      pip install pillow==7.0.0 scipy==1.2.1 tqdm==4.43.0 munch==2.5.0
   ```

2. downloads ckpt
   ```
      bash download.sh celeba-hq-dataset
      bash download.sh pretrained-network-celeba-hq
      bash download.sh wing
   ```
3. image align
   1) put image to custom male / female folder
   2) Please modify the code below to match gender
      ```
         python main.py --mode align \
               --inp_dir assets/representative/custom/female \
               --out_dir assets/representative/celeba_hq/src/female
      ```
   3) run
      ```
         python main.py --mode sample --num_domains 2 --resume_iter 100000 --w_hpf 1 \
               --checkpoint_dir expr/checkpoints/celeba_hq \
               --result_dir expr/results/celeba_hq \
               --src_dir assets/representative/celeba_hq/src \
               --ref_dir assets/representative/celeba_hq/ref
      ```
      

### sample result
![reference](https://github.com/Bong-HoonLee/change_your_look/assets/115579916/c5bd232c-cdf2-4b81-b49b-21bee70d9810)
