JAX - a high performance numerical computing library which optimizes scientific computing applications by offering:
JIT compilation in GPU/TPU (different from Numpy which only has CPU support), Automatic parallelization, Automatic vectorization, and Automatic differentiation (for deep learning). In short, JAX is developed for speed purposes, especially known as >5 times faster than Numpy, and with GPU support.

JAX = XLA (JIT compiler for Linear Algebra) + Autograd (autograd is computation library like numpy, which comes with extra features like reverse-mode differentiation - a.k.a backpropogation, and essentially more optimized  functions from numpy. It is currently not developed - while maintained, its developers are currently working on JAX.
Composable Function Transformations - an operator on a function whose output is another function. So, JAX has 4 of these main "function-inside-functions": 
```
grad(), vmap(), pmap(), jit()
```
Why use JAX
1. Numpy is on CPU only - JAX is Numpy on steroids: on CPU/GPU/TPU
2. XLA - Accelerated Linear Algebra (e.g. XLA from TF boost BERT's speed by 7.3x by computational speed point of view alone)
3. JIT - JAX makes your own functions into compiled, making orders of magnitude different from np.
4. Auto-differentiation
5. Deep Learning with   Flax, Haiku, Elegy
