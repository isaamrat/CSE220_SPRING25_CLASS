
 # Two-Dimensional Arrays - Java and Python Implementations

 ## Introduction to Two-Dimensional Arrays
 A two-dimensional (2D) array is an array of arrays, where data is stored in rows and columns, resembling a table or matrix. It is indexed using two indices: `row` and `column`.

 ## Memory Storage of 2D Arrays
 In memory, a 2D array is stored in a linear fashion. The elements can be stored in two ways:
- **Row-Major Order**: Elements are stored row by row.
- **Column-Major Order**: Elements are stored column by column.

 ### Converting Multi-Dimensional Index to Linear Index
 Given a 2D array of size `rows × cols`, the linear index `L` for an element at position `(i, j)` (row index `i`, column index `j`) is computed as:

 **Row-Major Order:**
 \[ L = i \times \text{cols} + j \]

 **Column-Major Order:**
 \[ L = j \times \text{rows} + i \]

 **Examples:**
 Consider a 3×3 matrix:
 ```
  0  1  2
  3  4  5
  6  7  8
 ```
 In row-major order, the index of `mat[1][2]` is:
 \[ L = 1 \times 3 + 2 = 5 \]

 In column-major order, the index of `mat[1][2]` is:
 \[ L = 2 \times 3 + 1 = 7 \]

 **Converting Linear Index Back to (Row, Column) Pair**
 Given a linear index `L`, the row and column indices can be obtained as:
 **Row-Major Order:**
 \[ i = \frac{L}{\text{cols}}, \quad j = L \mod \text{cols} \]
 **Column-Major Order:**
 \[ i = L \mod \text{rows}, \quad j = \frac{L}{\text{rows}} \]

 ## Functions Implemented

 ### Java Implementation
 #### `sumAll(int[][] mat)`
 - Computes the sum of all elements in the matrix.
 ```java
 public static int sumAll(int[][] mat) {
     int sum = 0;
     for (int i = 0; i < mat.length; i++) {
         for (int j = 0; j < mat[i].length; j++) {
             sum += mat[i][j];
         }
     }
     return sum;
 }
 ```

 #### `columnSum(int[][] mat)`
 - Computes and prints the sum of each column.
 ```java
 public static void columnSum(int[][] mat) {
     int[] arr = new int[mat[0].length];
     for (int j = 0; j < mat[0].length; j++) {
         for (int i = 0; i < mat.length; i++) {
             arr[j] += mat[i][j];
         }
     }
     System.out.println(Arrays.toString(arr));
 }
 ```

 #### `rowSum(int[][] mat)`
 - Computes and prints the sum of each row.
 ```java
 public static void rowSum(int[][] mat) {
     for (int i = 0; i < mat.length; i++) {
         int sum = 0;
         for (int j = 0; j < mat[i].length; j++) {
             sum += mat[i][j];
         }
         System.out.println(sum);
     }
 }
 ```

 #### `multiplyMatrix(int[][] matA, int[][] matB)`
 - Multiplies two matrices and prints the result.
 ```java
 public static void multiplyMatrix(int[][] matA, int[][] matB) {
     int[][] result = new int[matA.length][matB[0].length];
     for (int i = 0; i < matA.length; i++) {
         for (int j = 0; j < matB[0].length; j++) {
             for (int k = 0; k < matB.length; k++) {
                 result[i][j] += matA[i][k] * matB[k][j];
             }
         }
     }
     printMatrix(result);
 }
 ```

 #### `printDiagonal(int[][] mat)`
 - Prints the main diagonal elements.
 ```java
 public static void printDiagonal(int[][] mat) {
     for (int i = 0; i < mat.length; i++) {
         System.out.println(mat[i][i]);
     }
 }
 ```

 ### Python Implementation
 #### `sumAll(mat)`
 ```python
 def sumAll(mat):
     return sum(sum(row) for row in mat)
 ```

 #### `columnSum(mat)`
 ```python
 def columnSum(mat):
     col_sums = [sum(row[j] for row in mat) for j in range(len(mat[0]))]
     print(col_sums)
 ```

 #### `rowSum(mat)`
 ```python
 def rowSum(mat):
     row_sums = [sum(row) for row in mat]
     print(row_sums)
 ```

 #### `multiplyMatrix(matA, matB)`
 ```python
 def multiplyMatrix(matA, matB):
     import numpy as np
     result = np.dot(matA, matB)
     print(result)
 ```

 #### `printDiagonal(mat)`
 ```python
 def printDiagonal(mat):
     for i in range(len(mat)):
         print(mat[i][i])
 ```

 ## Applications of 2D Arrays
 - **Image Processing:** Pixels in images are stored in a 2D array.
 - **Graph Representations:** Adjacency matrices store graph edges.
 - **Game Development:** Chess boards and grids use 2D arrays.
 - **Scientific Computing:** Data tables in simulations.
 - **Matrix Operations:** Fundamental to machine learning.


