# segmentation-of-MRI-from-brain-tumor
-- Config virtual environment
conda create -n ShuWu python=3.6
conda activate ShuWu
pip install simpleitk
pip install opencv-python==3.4.2.16
pip install scipy
pip install scikit-learn==0.20
pip install scikit-image==0.14
conda  install numpy  mkl cffi

--install pytorch
https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/pytorch/
conda install --offline .\pytorch-0.4.0-py36_cuda80_cudnn7he774522_1.tar.bz2
conda install  torchvision  -c pytorch
conda install Pillow=6.1
conda install tqdm
conda install pandas
pip install -U scikit-image
pip install -i https://pypi.tuna.tsinghua.edu.cn/simple numba
pip install hausdorff


----------------------------------------------------------------------------
--Train UNet
python .\train.py --arch="Unet" --dataset=“ShuWu”

--Test result
python .\test.py --name="ShuWu_Unet_woDS" --mode="GetPicture"

--Evaluate test results
python .\test.py --name="ShuWu_Unet_woDS" --mode="Calculate"
