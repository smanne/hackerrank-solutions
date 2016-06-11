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
    var t = parseInt(readLine());
    for(var a0 = 0; a0 < t; a0++){
        var n = parseInt(readLine());
        console.log(findDecentNumber(n));
    }

}

function findDecentNumber(n) {
    if (n < 3) return -1;
    var remaining = n%3;
    var fValue;
    var tValue;
    while((n-remaining)%3 != 0 || (remaining)%5 != 0) {
      if (remaining > n) return -1;
      remaining++;
    }
    tValue = remaining;
    fValue = n - tValue;
    return Array(fValue+1).join(5) + Array(tValue+1).join(3)
}
```
