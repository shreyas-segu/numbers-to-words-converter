# @kushalst/numbers-to-words-converter


[![npm version](https://img.shields.io/badge/npm-v1.0.3-blue)](https://github.com/JarvisStriker/numbers-to-words-converter)

`numbers-to-words-converter` lets you expand numbers to words. There are other auxiallry functions that might help you achieve other things while you are at it. 

</br>

### Documentation
</br>
```sh
npm i @kushalst/numbers-to-words-converter
```

Number systems supported 
`IN` - Indian Number System (Lakhs, Crores, ...)
`INTL` - International Number System (Millions, Billions, ...)

| Functions | Description |
| ------ | ------ |
| `isSafeNumber(param1)` | Takes in a number and returns `boolean`. `True` if number is between [`MAX_SAFE_INTEGER`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/MAX_SAFE_INTEGER) and [`MIN_SAFE_INTEGER`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/MIN_SAFE_INTEGER) integer value supported by Js |
|`toWords(param1, param2)` | `param1` - Number to be expanded to string <br/> `param2` - `IN` for Indian number system. `INTL` for International number system |
|`delCommas(param1)`|`param1` - Takes in string with commas. Function deletes commas in the string and returns it|

</br>

### Examples
</br>

```javascript
var converter = require('@kushalst/numbers-to-words-converter')

converter.isSafeNumber(123123123123123123123445555)
//false

converter.isSafeNumber(1233445555)
//true

converter.toWords('10,00,000,32,78,944', 'IN')
//ten lakh crore, thirty-two lakh, seventy-eight thousand, nine hundred forty-four

converter.toWords('103,278,944', 'INTL')
//one hundred three million, two hundred seventy-eight thousand, nine hundred forty-four

converter.toWords('10,00,000,32,78,944', 'INTL')
//ten trillion, three million, two hundred seventy-eight thousand, nine hundred forty-four

converter.toWords('10,,,46,3,278,944', 'IN') // commas don't matter
//one thousand, forty-six crore, thirty-two lakh, seventy-eight thousand, nine hundred forty-four

converter.delCommas(converter.toWords('10,,,46,3,278,944', 'INTL'))
//ten billion four hundred sixty-three million two hundred seventy-eight thousand nine hundred forty-four
```
 More features coming up soon!
