# RuntimeError: DataLoader worker (pid 953) is killed by signal: Bus error. It is possible that dataloader's workers are out of shared memory. Please try to raise your shared memory limit.

**Solution**: https://github.com/pytorch/pytorch/issues/2244#issuecomment-318864552

Setting a higher amount by adding ```--shm-size 8G``` to the ```docker run``` command
