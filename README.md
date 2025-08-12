#include <stdio.h>

#define N 3

void rotate90Clockwise(int mat[N][N]) {
    // Step 1: Transpose the matrix
    for (int i = 0; i < N; i++) {
        for (int j = i; j < N; j++) {
            int temp = mat[i][j];
            mat[i][j] = mat[j][i];
            mat[j][i] = temp;
        }
    }

    // Step 2: Reverse each row
    for (int i = 0; i < N; i++) {
        for (int j = 0, k = N - 1; j < k; j++, k--) {
            int temp = mat[i][j];
            mat[i][j] = mat[i][k];
            mat[i][k] = temp;
        }
    }
}

int main() {
    int matrix[N][N] = {
        {1, 2, 3},
        {4, 5, 6},
        {7, 8, 9}
    };

    rotate90Clockwise(matrix);

    printf("Rotated Matrix:\n");
    for (int i = 0; i < N; i++) {
        for (int j = 0; j < N; j++) {
            printf("%d ", matrix[i][j]);
        }
        printf("\n");
    }

    return 0;
}
PYTHON
# Function to rotate a matrix 90 degrees clockwise
def rotate_matrix(mat):
    n = len(mat)
    
    # Step 1: Transpose the matrix
    for i in range(n):
        for j in range(i, n):
            mat[i][j], mat[j][i] = mat[j][i], mat[i][j]
    
    # Step 2: Reverse each row
    for i in range(n):
        mat[i].reverse()

# Example
matrix = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]

rotate_matrix(matrix)

# Print rotated matrix
for row in matrix:
    print(row)
OUTPUT
[7, 4, 1]
[8, 5, 2]
[9, 6, 3]
# Rotate-matrix-by-90-degree
