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

When installing wget I get the error 
```
Warning: pkg-config 0.29.2 is already installed
Error: cmake 3.9.4_1 is already installed
To upgrade to 3.10.2, run `brew upgrade cmake`
```
