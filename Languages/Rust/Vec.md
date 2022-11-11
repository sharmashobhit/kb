# `vec.windows(usize)`

Runs the code while using `usize` items at a time. Good for comparision

Eg:

Check if the vec is sorted

```rust
vec![0, 1, 2, 563, 12123].windows(2).all(|a| a[0] < a[1]);
/// true

vec![0, 1, 2, 1, 12].windows(2).all(|a| a[0] < a[1]);
/// false
```