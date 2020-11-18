# AwesomeBranchless
Branchless programming transforms


## Spam the conditional
```c
if(x)
  return y;
else
  return z
```
```c
return x*y + (!x)*z;
```
[Branchless Dyk Word](https://github.com/cassioneri/Dyck)

```c
integer next_dyck_word(integer w) {
  integer const a = w & -w;
  integer const b = w + a;
  integer       c = w ^ b;
                c = (c / a >> 2) + 1;
                c = ((c * c - 1) & 0xaaaaaaaaaaaaaaaa) | b;
  return c;
}
```

[Microsoft CLR 6](https://github.com/dotnet/runtime/issues/43629)

[Rust safeeft -branchless floating point transforms](https://docs.rs/safeeft/0.0.5/safeeft/)

[Branchless Search Algorithms](http://www.cphstl.dk/Paper/Branchless-search/sea13.pdf)

[Stanford Bithacks](https://graphics.stanford.edu/~seander/bithacks.html)

[Google Patent](https://patents.google.com/patent/US20090070751)


[Brandless Programming (Creel)](https://www.youtube.com/watch?v=bVJ-mWWL7cE&t=4s)
