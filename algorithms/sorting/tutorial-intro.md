[**Solution**](https://www.hackerrank.com/challenges/tutorial-intro)

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
    var valueToSearch = parseInt(readLine());
    var n = parseInt(readLine());
    var array = readLine().split(' ');
    for (i = 0; i < n; i++) {
        if (array[i] == valueToSearch) {
            console.log(i);
            break;
        }
    }
}
```
