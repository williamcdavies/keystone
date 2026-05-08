---
tags:
  - CS446
---
when a parent process dies before a [[Child processes|Child process]]
- in this case, the kernel knows that it's not going to get a `wait()` call
- the kernel will immediately put orphan processes under the care of `init`, which will routinely `wait` on and reap them eventually