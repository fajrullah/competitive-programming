```
Example 1:

Input: x = 121
Output: true
Explanation: 121 reads as 121 from left to right and from right to left.

Example 2:
Input: x = -121
Output: false
Explanation: From left to right, it reads -121. From right to left, it becomes 121-. 
Therefore it is not a palindrome.

Example 3:
Input: x = 10
Output: false
Explanation: Reads 01 from right to left. Therefore it is not a palindrome.

```

```javascript
var isPalindrome = function(x) {
    var reverse = 0;
    var copy = x;

    //The loop break when the copy of original number becomes zero
    //Also negative number cannot be a palindrome
    while (copy > 0) {
       // Get the last digit of 'copy' using modulo operation
      const digit = copy % 10;
      // Construct the reversed integer. For each iteration, shift the current 'reverse' one place to the left (multiply by 10)
      // and add the new 'digit' to it
      reverse = reverse * 10 + digit;
      // Remove the last digit from 'copy' using floor division
      // The '~~' is a bitwise operation that essentially floors the result of the division
      // it decrese every 10 10 10
      copy = ~~(copy / 10);
    }

    return reverse == x;
};

var isPalindrome = function(x) {
  return x < 0 ? false : (x === +x.toString().split("").reverse().join(""));
}
