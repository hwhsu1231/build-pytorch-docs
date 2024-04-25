# Build PyTorch Documentation

Preview in GitHub Pages: 

https://hwhsu1231.github.io/build-pytorch-docs


### Deactivate Conda Environments

不要使用 conda 中的 libstdc++。因為的版本目前最高到 `GLIBCXX_3.4.29`。但是可能需要使用 GLIBCXX_3.4.30。

```bash
Traceback (most recent call last):
  File "/home/runner/work/build-pytorch-docs/build-pytorch-docs/pytorch/docs/source/scripts/build_activation_images.py", line 11, in <module>
    import torch
  File "/home/runner/work/build-pytorch-docs/build-pytorch-docs/pytorch/torch/__init__.py", line 238, in <module>
    from torch._C import *  # noqa: F403
    ^^^^^^^^^^^^^^^^^^^^^^
ImportError: /usr/share/miniconda/lib/libstdc++.so.6: version `GLIBCXX_3.4.30' not found (required by /home/runner/work/build-pytorch-docs/build-pytorch-docs/pytorch/torch/lib/libtorch_python.so)
make: *** [Makefile:17: figures] Error 1
```

### Conda Install cmake>=3.18.2

```bash
conda install -c anaconda cmake==3.18.2
```

To solve the error messsage:

```bash
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

https://github.com/pytorch/pytorch/issues/42003