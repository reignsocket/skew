Problem Description  
In the skew binary representation, the value xk of the kth bit represents xk(2k+1-1). The possible number on each bit is 0 or 1, and the last non-zero bit can be 2, for example, 10120(skew) = 1(25-1) + 0(21)+1(231)+ 2 (22-1)+ 0(21-1) = 31 + 0 + 7 + 6 + 0 = 44. The first ten skew numbers are 0, 1, 2, 10, 11, 12, 20, 100, 101 And 102.  
  
Input data  
The input contains one or more rows, each containing an integer n. If n = 0 means the input ends, otherwise n is aNumber of skew  
  
Output requirements  
For each input, output its decimal representation. After converting to decimal, n does not exceed 2^31-1=2147483647
  
Input sample  
10120  
200000000000000000000000000000  
10  
1000000000000000000000000000000  
11  
100  
11111000001110000101101102000  
0  

Output sample  
44  
2147483646  
3  
2147483647  
4  
7  
1041110737  

Problem solving  
There is no equivalence between the bases on adjacent bits of the skew number. After calculating the cardinality of each bit, it is very simple to convert a skew number to a decimal representation. For a skew number of length k, the cardinality of the last digit is 2k
-1. Since n does not exceed 231-1 after conversion to decimal, the maximum length of the input skew number does not exceed 31. Use an integer array base[31] to store the base value of the last digit of the number of skew, the second digit of the last digit, ....., and the 31st digit. Use this array to convert each skew number to the corresponding decimal number.  
base[0] = 1
base[k] = 2^k+1 - 1 = 2 * (2^k - 1) + 1 = 2 * base[k -1] + 1 
