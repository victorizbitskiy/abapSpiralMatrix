# SpiralMatrix

This is another implementation of the [spiral matrix](http://rosettacode.org/wiki/Spiral_matrix) based on a pattern I discovered while playing with it.

### Algorithm
Let's say we want to get a 5x5 (dimention = 5) spiral matrix like this:

![spiralMatrix](https://github.com/victorizbitskiy/abapSpiralMatrix/blob/main/docs/img/spiralMatrix-5x5.svg)

The elements of this matrix have the following coordinates:

![spiralMatrixCoordinates](https://github.com/victorizbitskiy/abapSpiralMatrix/blob/main/docs/img/spiralMatrix_5x5_coordinates.svg)

In essence, the task is to find the coordinates for each element. So, lets do it.  
If we represent the coordinates of rows (dy) and columns (dx) as a sequences of numbers, then we can notice a certain pattern.

![spiralMatrixTable](https://github.com/victorizbitskiy/abapSpiralMatrix/blob/main/docs/img/spiralMatrix-5x5_table.svg)

1. Total number of sequences = 2*dimention - 1.
2. The sequence dimention is repeated twice and then reduced by 1 (except for the first sequence).
3. The row coordinates (dy) for even sequences are incremented and then decremented by 1 (and so on). The row coordinates for odd sequences remain constant.
4. For column coordinates (dx), the opposite is true.

This algorithm is implemented in the spiralMatrix() function.

### Usage
```abap
  DATA(go_spiral_matrix) = NEW lcl_spiral_matrix( iv_dimention     = 5
                                                  iv_initial_value = 0 ).
  go_spiral_matrix->print( ).
```  
The result:  
![Result](https://github.com/victorizbitskiy/abapSpiralMatrix/blob/main/docs/img/result.png)
