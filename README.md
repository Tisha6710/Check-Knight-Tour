# Check-Knight-Tour
package BackTracking;

public class CheckKnightTour {
    public boolean helper(int[][] grid,int row,int col,int num) {
        int n = grid.length;
        // base case
        if(grid[row][col]==n*n-1) return true;
        int i, j;
        // 2 Up i right
        i = row - 2;
        j = col + 1;
        if (i >= 0 && j < n) {
            if (grid[i][j] == num + 1) return helper(grid, i, j, num + 1);
        }
        // 2 Up i left
        i = row - 2;
        j = col - 1;
        if (i >= 0 && j >= 0) {
            if (grid[i][j] == num + 1) return helper(grid, i, j, num + 1);

        }
        // 2 down 1 right
        i = row + 2;
        j = col + 1;
        if (i < n && j < n) {
            if (grid[i][j] == num + 1) return helper(grid, i, j, num + 1);
        }
        // 2 down 1 left
        i = row + 2;
        j = col - 1;
        if (i < n && j >= 0) {
            if (grid[i][j] == num + 1) return helper(grid, i, j, num + 1);

        }
        // 2 right 1 Up
        i = row - 1;
        j = col + 2;
        if (i >= 0 && j < n) {
            if (grid[i][j] == num + 1) return helper(grid, i, j, num + 1);

        }
        // 2 right 1 down
        i = row + 1;
        j = col + 2;
        if (i < n && j < n) {
            if (grid[i][j] == num + 1) return helper(grid, i, j, num + 1);

        }
        // 2 left 1 Up
        i = row - 1;
        j = col - 2;
        if (i >= 0 && j >= 0) {
            if (grid[i][j] == num + 1) return helper(grid, i, j, num + 1);

        }
        // 2 left 1 down
        i = row + 1;
        j = col - 2;
        if (i < n && j >= 0) {
            if (grid[i][j] == num + 1) return helper(grid, i, j, num + 1);

        }
        return false;
    }

    public boolean CheckVlidationGrid(int[][] grid) {
        if(grid[0][0]!=0) return false;
        return helper(grid,0,0,0);



    }
}
