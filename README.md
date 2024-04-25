# Build PyTorch Documentation

Preview in GitHub Pages: 

https://hwhsu1231.github.io/build-pytorch-docs



### Conda Install cmake>=3.18.2

```
conda install -c anaconda cmake==3.18.2
```

To solve the error messsage

```
Traceback (most recent call last):
  File "/home/runner/work/build-pytorch-docs/build-pytorch-docs/pytorch/setup.py", line 349, in <module>
    cmake = CMake()
            ^^^^^^^
  File "/home/runner/work/build-pytorch-docs/build-pytorch-docs/pytorch/tools/setup_helpers/cmake.py", line 40, in __init__
    self._cmake_command = CMake._get_cmake_command()
                          ^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/home/runner/work/build-pytorch-docs/build-pytorch-docs/pytorch/tools/setup_helpers/cmake.py", line 67, in _get_cmake_command
    raise RuntimeError("no cmake or cmake3 with version >= 3.18.0 found")
RuntimeError: no cmake or cmake3 with version >= 3.18.0 found
Building wheel torch-2.4.0a0+git59a1f1f
```
