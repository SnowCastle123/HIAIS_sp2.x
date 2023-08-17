# HIAIS_sp2.x
#Since the new GPU does not support lower versions of CUDA, the project will use spconv2.x, simplifying the deployment process

conda create -n hais_sp2 python=3.7
conda activate hais_sp2
conda install pytorch==1.7.0 torchvision==0.8 cudatoolkit=10.1 -c https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/pytorch/linux-64/
pip install -r requirements.txt  
#Choose the Spconv version based on your CUDA version
pip install spconv-cu102
# Compile ops
cd HAIS/lib/hais_ops
python setup.py build_ext develop
