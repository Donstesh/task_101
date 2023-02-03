## 1. Write a program to reverse a given string. For example, if we pass the word 'john', the program should return the word 'nhoj'.

var letters= ["S", "I", "E", "N", "K", "O"];
                                         
    var result ="";
    for (var a = 5; a >= 0; a--)
    {
        result += letters[a] + " ";
    }
     
    document.write(result.slice(0,result.length-1));

## 2. Given an integer array with positive numbers from 0 to x, find the missing numbers and return them as an array. For example, given an array with the following numbers (0, 1, 2, 5, 14, 17, 18, 19, 20), the missing numbers are (3, 4, 6, 7, 8, 9, 10, 11, 12, 13, 15, 16).

function missingNum(nums,n){
  let j;
  let temp = [];
  for (j = 0; j <= n; j++) {
            temp[j] = 0;
        }
 
        for (j = 0; j < n; j++) {
            temp[nums[j] - 1] = 1;
        }
 
        let res = 0;
        for (j = 0; j <= n; j++) {
            if (temp[j] == 0)
                res = j + 1;
        }
        console.log(res);
}
 

        let nums = [ 0, 1, 2, 5, 14, 17, 18, 19, 20 ];
        let m = nums.length;
 
       missingNum(nums,m);
       
## 3. Given an array of strings, return an array containing only items with duplicates. For example, if you have an array with these items (a, b, c, b, f, g, a, d), your solution should give the output as (a, b).

function printDuplicates(arr, n)
{
    var repeated = new Map();
    for(let q = 0; q < n; q++)
    {
        if (repeated.has(arr[q]))
        {
            repeated.set(letters[q], repeated.get(letters[q]) + 1);
        }
        else
        {
            repeated.set(arr[q], 1);
        }
    }
    var dupLetter = false;
    for(let [key, value] of repeated)
    {
        if (value > 1)
        {
            document.write(key + " ");
            dupLetter = true;
        }
    }
    if (dupLetter == false)
        document.write("-1");
}
var letters = [ 'a', 'b', 'c', 'b', 'f', 'g', 'a', 'd' ];
var n = letters.length;
 
printDuplicates(letters, n);
