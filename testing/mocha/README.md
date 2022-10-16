# Testing JavaScript with Mocha

[Mocha](https://mochajs.org/) is a feature-rich JavaScript test framework running on Node.js. Mocha supports writing your tests as *ES modules*, and not just using *CommonJS*. Create `test.mjs`:

```javascript
import assert from 'assert';

describe('Array', function() {
    describe('#indexOf()', function() {
        it('should return -1 when the value is not present', function() {
            assert.equal([1, 2, 3].indexOf(4), -1);
        });
    });
});
```

Then

```bash
$ mocha

  Array
    #indexOf()
      ✓ should return -1 when the value is not present

  1 passing (18ms)
```

Two things to keep in mind:

- the extension shall be `mjs` because it imports ES modules;
- the file name shall be test.[js|mjs], which is the default;

Create `package.json` to set up a test script:

```json
{
  "scripts": {
    "test": "mocha"
  }
}
```

Then you will find `Debug` button in the editor. Depressing the button run the test code as follows:

```bash
$ npm test
> test
> mocha

  Array
    #indexOf()
      ✓ should return -1 when the value is not present

  1 passing (16ms)
```


