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

  // compute distance between two points
  std::cout << p.distance(p1) << std::endl; // 2.23607
  std::cout << distance(p1, p) << std::endl;

  // meny ways to access coordinates
  std::cout << p.x() << std::endl;  // 2
  std::cout << p[1] << std::endl;  // 3
  std::cout << p(2) << std::endl;  // 4

  // there is a difference between access operators:
  p.x() += 1   // this changes p
  std::cout << p << std::endl;  // 3       3       4
  p[0] -= 1   // this also changes p
  std::cout << p << std::endl;  // 2       3       4
  // the following would give an error:
  // p(0) -= 3
}
```
