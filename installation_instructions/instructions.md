# Installation Instructions for MAC OSX
https://www.pyimagesearch.com/2017/09/29/macos-for-deep-learning-with-python-tensorflow-and-keras/

# Installation Instructions for Linux(Ubuntu)
https://www.pyimagesearch.com/2017/09/27/setting-up-ubuntu-16-04-cuda-gpu-for-deep-learning-with-python/

# On Jacob's Mac
Tell Virtual Environment to use Python 3 instead of 2
- ```gedit ~/.bash_profile```
- Comment on python2 and comment in python3
- VIRTUALENVWRAPPER_PYTHON=/usr/local/bin/python3
- #VIRTUALENVWRAPPER_PYTHON=/usr/local/bin/python2

For some reason I also had to reinstall virtualenvwrapper for python 3
```
pip3 install virtualenvwrapper
```

Then follow OSX starting at **Creating the ‘dl4cv’ environment** section.

After installing tbb I get this warning and followed the recommendation
```
Python modules have been installed and Homebrew's site-packages is not
in your Python sys.path, so you will not be able to import the modules
this formula installed. If you plan to develop with these modules,
please run:
  mkdir -p /Users/JacobWagner/Library/Python/2.7/lib/python/site-packages
  echo 'import site; site.addsitedir("/usr/local/lib/python2.7/site-packages")' >> /Users/JacobWagner/Library/Python/2.7/lib/python/site-packages/homebrew.pth
  ```
  Then when running cmake I had some issues with the eigen3 library.
  I one cmake flag to point it to where eigen3 was installed with homebrew
  ```
  cmake -D CMAKE_BUILD_TYPE=RELEASE \
    -D CMAKE_INSTALL_PREFIX=/usr/local \
    -D OPENCV_EXTRA_MODULES_PATH=~/Documents/Repositories/opencv_contrib-3.3.0/modules \
    -D PYTHON3_LIBRARY=`python -c 'import subprocess ; import sys ; s = subprocess.check_output("python-config --configdir", shell=True).decode("utf-8").strip() ; (M, m) = sys.version_info[:2] ; print("{}/libpython{}.{}.dylib".format(s, M, m))'` \
    -D PYTHON3_INCLUDE_DIR=`python -c 'import distutils.sysconfig as s; print(s.get_python_inc())'` \
    -D PYTHON3_EXECUTABLE=$VIRTUAL_ENV/bin/python \
    -D BUILD_opencv_python2=OFF \
    -D BUILD_opencv_python3=ON \
    -D INSTALL_PYTHON_EXAMPLES=ON \
    -D INSTALL_C_EXAMPLES=OFF \
    -D BUILD_EXAMPLES=ON \
    -D EIGEN_INCLUDE_PATH=/usr/local/Cellar/eigen/3.3.4/include/eigen3 ..
    ```
    
    When installing tensorflow, pip was not able to find the tensorflow package, so I had to install it using the binary as described here.
     https://www.tensorflow.org/install/install_mac#the_url_of_the_tensorflow_python_package
```
pip3 install --upgrade https://storage.googleapis.com/tensorflow/mac/cpu/tensorflow-1.5.0-py3-none-any.whl
```
