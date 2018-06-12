sudo yum install -y git python-pip python-devel python-nose python-setuptools gcc gcc-gfortran gcc-c++ blas-devel lapack-devel atlas-devel
virtualenv virtualenv --python="/usr/bin/python" --always-copy --no-site-packages

source virtualenv/bin/activate

find virtualenv/ -name "*.so" | xargs strip

mkdir build
cd build
mkdir lib

pip install numpy
pip install keras
pip install h5py
pip install tensorflow


cp -r ~/virtualenv/lib/python2.7/site-packages/tensorflow .
cp -r ~/virtualenv/lib/python2.7/site-packages/pkg_resources .
cp -r ~/virtualenv/lib/python2.7/site-packages/keras .
cp -r ~/virtualenv/lib64/python2.7/site-packages/* .
rm -r scipy*
