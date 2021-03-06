# search-text-tokenizer

[![Build Status](https://travis-ci.org/tatsuyaoiw/search-text-tokenizer.svg?branch=master)](https://travis-ci.org/tatsuyaoiw/search-text-tokenizer)

A search query tokeniser inspired by Google.

- Split a space-delimitered query string into an array of terms
- Treat quoted terms as phrases
- Support tagged terms (tag:term)
- Detect excluded terms (-term)

## Examples

```js
var tokenizer = require( 'search-text-tokenizer' );

console.log( tokenizer( 'red bull' ) );
// [ { term: 'red' }, { term: 'bull' } ]

console.log( tokenizer( '"red bull" "gives you wings"' ) );
// [ { term: 'red bull', phrase: true }, { term: 'gives you wings', phrase: true } ]

console.log( tokenizer( 'author:tolkien' ) );
// [ { term: 'tolkien', tag: 'author' } ]

console.log( tokenizer( 'jaguars -car' ) );
// [ { term: 'jaguars'}, { term: 'car', exclude: true } ]
```

## Installation

```
$ npm install search-text-tokenizer
```

## Running test

To run the test suite run the following commands in the project directory.

```
$ npm install
$ npm test
```

## License

MIT © Tatsuya Oiwa, Dannii Willis, James Anthony Bruno
