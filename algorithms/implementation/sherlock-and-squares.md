[**Solution**](https://www.hackerrank.com/challenges/sherlock-and-squares)
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
    var t = parseInt(readLine());
    for(var a0 = 0; a0 < t; a0++){
        var n = readLine().split(' ');
        console.log(parseInt(Math.sqrt(n[1])) - Math.ceil(Math.sqrt(n[0]))+1)
    }
}
```
