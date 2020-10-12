# Layers

## Doc
* [AWS Lambda C++ Runtime](https://github.com/awslabs/aws-lambda-cpp)
* [Rust Runtime for AWS Lambda](https://github.com/awslabs/aws-lambda-rust-runtime)
* [New for AWS Lambda – Use Any Programming Language and Share Common Components](https://aws.amazon.com/blogs/aws/new-for-aws-lambda-use-any-programming-language-and-share-common-components/)

## Acronym

## Intro
* Custom Runtimes
    * Ex: C++
    * Ex: Rust
* Externalize Dependencies to re-use them:

### Diagram
[<img src="https://i.imgur.com/yChp1ec.png">](https://i.imgur.com/yChp1ec.png)

---

## Demo
* Create new function
    * RadioButton: Author from scratch
    * Function name: Lambda-Layer-Demo
    * Runtime: python
    
* Layers
    * Default: **zero**
    * **click on Layer**
    
[<img src="https://i.imgur.com/Nj0fcW4.png">](https://i.imgur.com/Nj0fcW4.png)

* Add layer
    * Choose a layer: AWS layers
    * Name: AWSLambda-Python38-SciPy1x
    * Version: 29
* Add
    
[<img src="https://i.imgur.com/BID1PnY.png">](https://i.imgur.com/BID1PnY.png)
[<img src="https://i.imgur.com/LdTFidP.png">](https://i.imgur.com/LdTFidP.png)

* put this code in lambda from the doc
````python
import numpy as np
from scipy.spatial import ConvexHull

def lambda_handler(event, context):

    print("\nUsing NumPy\n")

    print("random matrix_a =")
    matrix_a = np.random.randint(10, size=(4, 4))
    print(matrix_a)

    print("random matrix_b =")
    matrix_b = np.random.randint(10, size=(4, 4))
    print(matrix_b)

    print("matrix_a * matrix_b = ")
    print(matrix_a.dot(matrix_b))
    print("\nUsing SciPy\n")

    num_points = 10
    print(num_points, "random points:")
    points = np.random.rand(num_points, 2)
    for i, point in enumerate(points):
        print(i, '->', point)

    hull = ConvexHull(points)
    print("The smallest convex set containing all",
        num_points, "points has", len(hull.simplices),
        "sides,\nconnecting points:")
    for simplex in hull.simplices:
        print(simplex[0], '<->', simplex[1])
````

[<img src="https://i.imgur.com/mv26veq.png">](https://i.imgur.com/mv26veq.png)

* Test this function:
    * random matrix_a...

[<img src="https://i.imgur.com/1ovg84A.png">](https://i.imgur.com/1ovg84A.png)
