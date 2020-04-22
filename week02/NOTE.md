# 每周总结可以写在这里

### 匹配数字字面量
```js
/^[\+\-]{0,1}(([0-9]*)([eE][0-9]+){0,1}\.{0,1}([0-9]*)([eE][0-9]+){0,1})|(0[bB][0-1]+)|(0[oO][0-7]+)|(0[xX][a-fA-F0-9]+)$/
```

### UTF-8 Encoding 的函数

```js
    function encodingUTF8(chart) {
        const buffer = [];
        const str = '00000000';
        for (let i = 0; i < chart.length; i++) {
            const codePoint = chart[i].codePointAt();
            let binaryCode = codePoint.toString(2);
            if (binaryCode.toString().length < 8) {
                binaryCode = str.substr(0, 8 - binaryCode.toString().length) + '' + binaryCode.toString();
            }

            buffer.push(binaryCode);
        }

        return buffer;
    }

    encodingUTF8('hello world');
```

### 字符串字面量