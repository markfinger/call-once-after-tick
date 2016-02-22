# call-once-after-tick

Enables multiple call-sites to enqueue a function call that will
occur both asynchronously and only once per tick.


## Install

`npm install --save call-once-after-tick`


## Example

```js
import callOnceAfterTick from 'call-once-after-tick';

let count = 0;
const fn = callOnceAfterTick(() => count++);

console.log(count); // 0

fn();
fn();
fn();

console.log(count); // 0

process.nextTick(() => {
  console.log(count); // 1
});
```
