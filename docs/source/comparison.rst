Comparison with Other Frameworks
================================

A table for quick comparison
----------------------------

This table compares Chainer with other popular deep learning frameworks.
We hope it helps you to choose an appropriate framework for the demand.

.. note::

   This chart may be out-dated, since the developers of Chainer do not perfectly follow the latest development status of each framework.
   Please report us if you find an out-dated cell.
   Requests for new comparison axes are also welcome.


+-------+-----------------------------+-------------------+------------------------+-------------------+----------------------------------------------------+
|       |                             | Chainer           | Theano-based           | Torch7            | Caffe                                              |
+=======+=============================+===================+========================+===================+====================================================+
| Specs | Scripting                   | Python            | Python                 | LuaJIT            | Python                                             |
|       +-----------------------------+-------------------+------------------------+-------------------+----------------------------------------------------+
|       | Net definition language     | Python            | Python                 | LuaJIT            | Protocol Buffers                                   |
|       +-----------------------------+-------------------+------------------------+-------------------+----------------------------------------------------+
|       | Define-by-Run scheme        | Y                 |                        |                   |                                                    |
|       +-----------------------------+-------------------+------------------------+-------------------+----------------------------------------------------+
|       | CPU Array backend           | NumPy             | NumPy                  | Tensor            |                                                    |
|       +-----------------------------+-------------------+------------------------+-------------------+----------------------------------------------------+
|       | GPU Array backend           | PyCUDA [1]_       | CudaNdarray [2]_       | CudaTensor        |                                                    |
+-------+-----------------------------+-------------------+------------------------+-------------------+----------------------------------------------------+
| NNs   | Reverse-mode AD             | Y                 | Y                      | Y                 | Y                                                  |
|       +-----------------------------+-------------------+------------------------+-------------------+----------------------------------------------------+
|       | Basic RNN support           | Y                 | Y                      | Y (nnx)           | `#2033 <https://github.com/BVLC/caffe/pull/2033>`_ |
|       +-----------------------------+-------------------+------------------------+-------------------+----------------------------------------------------+
|       | Variable-length loops       | Y                 | Y (scan)               |                   |                                                    |
|       +-----------------------------+-------------------+------------------------+-------------------+----------------------------------------------------+
|       | Stateful RNNs [3]_          | Y                 |                        | Y [7]_            |                                                    |
|       +-----------------------------+-------------------+------------------------+-------------------+----------------------------------------------------+
|       | Per-batch architectures     | Y                 |                        |                   |                                                    |
+-------+-----------------------------+-------------------+------------------------+-------------------+----------------------------------------------------+
| Perf  | CUDA support                | Y                 | Y                      | Y                 | Y                                                  |
|       +-----------------------------+-------------------+------------------------+-------------------+----------------------------------------------------+
|       | cuDNN support               | Y                 | Y                      | Y (cudnn.torch)   | Y                                                  |
|       +-----------------------------+-------------------+------------------------+-------------------+----------------------------------------------------+
|       | FFT-based convolution       |                   | Y                      | Y (fbcunn)        | `#544 <https://github.com/BVLC/caffe/pull/544>`_   |
|       +-----------------------------+-------------------+------------------------+-------------------+----------------------------------------------------+
|       | CPU/GPU generic coding [4]_ | [1]_              | [5]_                   | Y                 |                                                    |
|       +-----------------------------+-------------------+------------------------+-------------------+----------------------------------------------------+
|       | Multi GPU (data parallel)   | Y                 |                        | Y (fbcunn)        | `#2114 <https://github.com/BVLC/caffe/pull/2114>`_ |
|       +-----------------------------+-------------------+------------------------+-------------------+----------------------------------------------------+
|       | Multi GPU (model parallel)  | Y                 |                        | Y (fbcunn)        |                                                    |
+-------+-----------------------------+-------------------+------------------------+-------------------+----------------------------------------------------+
| Misc  | Type checking               | Y                 | Y                      | Y                 | N/A                                                |
|       +-----------------------------+-------------------+------------------------+-------------------+----------------------------------------------------+
|       | Model serialization         | Y (pickle)        | Y (pickle)             | Y                 | Y                                                  |
|       +-----------------------------+-------------------+------------------------+-------------------+----------------------------------------------------+
|       | Caffe reference model       | Y                 | [6]_                   | Y (loadcaffe)     | Y                                                  |
+-------+-----------------------------+-------------------+------------------------+-------------------+----------------------------------------------------+

.. [1] We are preparing for changing the GPU array backend to `CuPy <https://github.com/pfnet/chainer/pull/266>`_. It enables us to write one code for both CPU and GPU arrays.
.. [2] They are also developing `libgpuarray <http://deeplearning.net/software/libgpuarray/>`_
.. [3] Stateful RNN is a type of RNN implementation that maintains states in the loops. It should enable us to use the states arbitrarily to update them.
.. [4] This row shows whether each array API supports unified codes for CPU and GPU.
.. [5] The array backend of Theano does not have compatible interface with NumPy, though most users write code on theano variables, which is generic for CPU and GPU.
.. [6] Depending on the frameworks.
.. [7] Also available in the `Torch RNN package <https://github.com/Element-Research/rnn>`


Benchmarks
----------

We are preparing for the benchmarks.