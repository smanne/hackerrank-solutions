Given an array of integers, calculate which fraction of its elements are positive, which fraction of its elements are negative, and which fraction of its elements are zeroes, respectively. Print the decimal value of each fraction on a new line.

**Note:** This challenge introduces precision problems. The test cases are scaled to six decimal places, though answers with absolute error of up to 10<sup>-4</sup>  are acceptable.

**Input Format**

The first line contains an integer, *N* , denoting the size of the array.
The second line contains *N* space-separated integers describing an array of numbers (a<sub>0</sub>, a<sub>1</sub>, a<sub>2</sub>,... a<sub>n-1</sub>)

**Output Format**

You must print the following  lines:

A decimal representing of the fraction of positive numbers in the array.
A decimal representing of the fraction of negative numbers in the array.
A decimal representing of the fraction of zeroes in the array.

**Sample Input**

    6
    -4 3 -9 0 4 1      

**Sample Output**

    0.500000
    0.333333
    0.166667
**Explanation**

There are *3* positive numbers, *2* negative numbers, and *1* zero in the array.
The respective fractions of positive numbers, negative numbers and zeroes are <sup>3</sup>/<sub>6</sub> = 0.500000, respectively.

**Solution**
```javascript
    process.stdin.resume();
    process.stdin.setEncoding('ascii');

    var input_stdin = "";
    var input_stdin_array = "";
    var input_currentline = 0;

    process.stdin.on('data', function (data) {
        input_stdin += data;
    });

    process.stdin.on('end', function () {
        input_stdin_array = input_stdin.split("\n");
        main();    
    });

    function readLine() {
        return input_stdin_array[input_currentline++];
    }

    /////////////// ignore above this line ////////////////////

    function main() {
        var n = parseInt(readLine());
        arr = readLine().split(' ');
        var result = [0, 0, 0];
        arr.forEach(function(element, index, array ){
            if (element > 0) {
                result[0]++;
            } else if (element < 0) {
                result[1]++;
            } else if (element == 0) {
                result[2]++;
            }
        });

        console.log((result[0]/n).toFixed(6));
        console.log((result[1]/n).toFixed(6));
        console.log((result[2]/n).toFixed(6));
    }
```
