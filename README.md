# Arrow Series


/**
 * 二维数组中寻找是否存在指定数字
 */
public class Solution {

    public static void main(String[] args) {

        int[][] array1 = {{1, 11, 21}, {2, 12, 22}, {3, 13, 23}};
        System.out.println("result1 : " + new Solution().Find(12, array1)); // true
        System.out.println("result2 : " + new Solution().Find(13, array1)); // true
        System.out.println("result3 : " + new Solution().Find(10, array1)); // false
    }

    /**
     * 解题思路1
     * 先判断是否在每一行的最小和最大范围内
     *
     * @param target
     * @param array
     * @return
     */
    public boolean Find(int target, int[][] array) {

        int length1 = array.length;
        int length2 = array[0].length;
        for (int i = 0; i < length1; i++) {
            int min = array[i][0];
            int max = array[i][length2 - 1];
            if (target < min || target > max) {
                // 如果不再这行范围内，直接下一行
                continue;
            }
            for (int j = 0; j < length2; j++) {
                if (array[i][j] == target) {
                    return true;
                }
            }
        }
        return false;
    }
}
