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

### 安裝 katex

安裝：

```bash
npm
```

否則：

```
Traceback (most recent call last):
  File "/home/runner/work/build-pytorch-docs/build-pytorch-docs/pytorch/.venv/lib/python3.10/site-packages/sphinx/cmd/build.py", line 276, in build_main
    app.build(args.force_all, filenames)
  File "/home/runner/work/build-pytorch-docs/build-pytorch-docs/pytorch/.venv/lib/python3.10/site-packages/sphinx/application.py", line 329, in build
    self.builder.build_update()
  File "/home/runner/work/build-pytorch-docs/build-pytorch-docs/pytorch/.venv/lib/python3.10/site-packages/sphinx/builders/__init__.py", line 288, in build_update
    self.build(to_build,
  File "/home/runner/work/build-pytorch-docs/build-pytorch-docs/pytorch/.venv/lib/python3.10/site-packages/sphinx/builders/__init__.py", line 352, in build
    self.write(docnames, list(updated_docnames), method)
  File "/home/runner/work/build-pytorch-docs/build-pytorch-docs/pytorch/.venv/lib/python3.10/site-packages/sphinx/builders/__init__.py", line 541, in write
    self._write_parallel(sorted(docnames),
  File "/home/runner/work/build-pytorch-docs/build-pytorch-docs/pytorch/.venv/lib/python3.10/site-packages/sphinx/builders/__init__.py", line 588, in _write_parallel
    tasks.add_task(write_process, arg, on_chunk_done)
  File "/home/runner/work/build-pytorch-docs/build-pytorch-docs/pytorch/.venv/lib/python3.10/site-packages/sphinx/util/parallel.py", line 88, in add_task
    self._join_one()
  File "/home/runner/work/build-pytorch-docs/build-pytorch-docs/pytorch/.venv/lib/python3.10/site-packages/sphinx/util/parallel.py", line 114, in _join_one
    raise SphinxParallelError(*result)
sphinx.errors.SphinxParallelError: FileNotFoundError: [Errno 2] No such file or directory: 'katex'
Sphinx parallel build error:
FileNotFoundError: [Errno 2] No such file or directory: 'katex'
make: *** [Makefile:49: html] Error 2
```


https://github.com/pytorch/pytorch/issues/42003


