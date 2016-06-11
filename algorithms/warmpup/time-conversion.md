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
      var time = readLine();
      var meridiem = time.substr(8, 2);
      var hour = parseInt(time.substr(0, 2));
      if (meridiem == "AM") {
        if (hour == 12) console.log("00"+time.substr(2, 6))
        else console.log(time.substr(0, 8));
      } else {
          if (hour == 12) console.log((12)+time.substr(2, 6))
          else console.log((hour+12)+time.substr(2, 6));
      }
    }


```
