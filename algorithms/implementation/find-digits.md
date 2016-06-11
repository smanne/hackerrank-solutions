[**Solution**](https://www.hackerrank.com/challenges/find-digits)
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
        var n = readLine();
        var totalValue = 0;
        n.split('').forEach((value) => {
            if ((n%(parseInt(value)) == 0)) totalValue++;
        });
        console.log(totalValue);
    }

}
```
