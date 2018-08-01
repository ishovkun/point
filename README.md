# Point
## Description
This is lightweight header-only template-based implementation of a C++ point class.
Not well-tested, so use at your own risk.

## Examples

```cpp
#include "Point.hpp"
#include <vector>

int main()
{
  // easy construction
  angem::Point<3> p = {1, 2, 3};
  std::cout << p << std::endl;    // 1 2 3

  // many useful functions
  p += 1;
  std::cout << p << std::endl;    // 2 3 4

  // construction from std::vector
  std::vector<double> v = {4, 4, 4};
  angem::Point<3> p1 = v;

  // let's compute Euclidian norm
  std::cout << p1.norm() << std::endl; // 6.9282

  // add points
  std::cout << p + p1 << std::endl; // 6 7 8

  // several versions of dot product
  std::cout << p.dot(p1) << std::endl; // 36
  std::cout << dot(p, p1) << std::endl;
  std::cout << p*p1 << std::endl;

}
```
