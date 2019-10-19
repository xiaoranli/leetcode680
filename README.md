# 22、leetcode680. 验证回文字符串 Ⅱ
解法一：
--  
思路：
--
    双指针，从左右两端开始验证是否是回文串，若左右两边的字符不相等的时候，选择跳过左边或者右边的一个字符，再去验证一遍。    
代码： 
--
<pre>
/**
 * @author lihe
 * @date 2019/10/19 13:57
 * @descriptor
 */
public class ValidPalindrome_680 {
    public static boolean validPalindrome(String s) {
        int i = 0,j = s.length() - 1;
        while(i < j){
            char c1 = s.charAt(i);
            char c2 = s.charAt(j);
            if(c1 != c2){
                return valid(s,i+1,j) || valid(s,i,j-1);
            }
            i++;
            j--;
        }
        return true;
    }
    private static boolean valid(String s, int i, int j) {
        while(i <= j){
            char c1 = s.charAt(i);
            char c2 = s.charAt(j);
            if(c1 != c2){
                return false;
            }
            i++;
            j--;
        }
        return true;
    }
    public static void main(String[] args) {
        String s = "abca";
        boolean b = validPalindrome(s);
        System.out.println(b);
    }
}
</pre>

