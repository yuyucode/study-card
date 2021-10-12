# Set

Set 对象允许你存储任何类型的唯一值，无论是原始值或者是对象引用。

### 阐述

Set对象是值的集合，你可以按照插入的顺序迭代它的元素。 Set中的元素只会出现一次，即 Set 中的元素是唯一的。

### Constructor

`Set()`

### 实例属性

- `Set.prototype.size` ：返回 Set 对象中的值的个数

```ts
const hashTable = new Set();
hashTable.add(5);
console.log(hashTable.length); // 1
```

### 实例方法

- `Set.prototype.add(value)` ：在Set对象尾部添加一个元素。返回该Set对象。

```ts
const test = new Set();
test.add(5); // 会返回Set对象 {0:5}
test.add(5); // 会返回Set对象 {0:5},因为Set中的元素只会出现一次
```

- `Set.prototype.clear()` ：移除Set对象内的所有元素。

```ts
const test = new Set();
test.clear();
```

- `Set.prototype.delete(value)` ：移除Set中与这个值相等的元素，返回`Set.prototype.has(value)`
  在这个操作前会返回的值（即如果该元素存在，返回true，否则返回false）。`Set.prototype.has(value`)在此后会返回false。

```ts
const test = new Set();
test.add(5); // 会返回Set对象 {0:5}
test.delete(5); // true
test.delete("test"); // false
```

- `Set.prototype.entries()`：返回一个新的迭代器对象，该对象包含Set对象中的按插入顺序排列的所有元素的值的[value, value]数组。为了使这个方法和Map对象保持相似， 每个值的键和值相等。

```ts
const test = new Set();
test.add(5); // 会返回Set对象 {0:5}
test.entries(); // {5:5}
```

- `Set.prototype.forEach(callbackFn[, thisArg])`：按照插入顺序，为Set对象中的每一个值调用一次callBackFn。如果提供了thisArg参数，回调中的this会是这个参数。

```ts
const test = new Set();
test.add(5); // 会返回Set对象 {0:5}
test.add("c"); // 会返回Set对象 {0:5}

test.forEach((v1, v2, o) => {
    console.log(v1, v2, o); // 5,5, Set对象{0:5,1:"c"}
    console.log(v1, v2, o); // "c","c", Set对象{0:5,1:"c"}
})
```

- `Set.prototype.has(value)`：返回一个布尔值，表示该值在Set中存在与否。

```ts
const test = new Set();
test.add(5); // 会返回Set对象 {0:5}
test.has(5); // true
```

- `Set.prototype.keys() (en-US)`： 与values()方法相同，返回一个新的迭代器对象，该对象包含Set对象中的按插入顺序排列的所有元素的值。
- `Set.prototype.values()`：返回一个新的迭代器对象，该对象包含Set对象中的按插入顺序排列的所有元素的值。
- `Set.prototype[@@iterator]()`：返回一个新的迭代器对象，该对象包含Set对象中的按插入顺序排列的所有元素的值。

```ts
const test = new Set();
test.add(5); // 会返回Set对象 {0:5}
test.add("hello"); // 会返回Set对象 {0:5, 1: "hellow"}
test.add("你好啊"); // 会返回Set对象 {0:5, 1: "hellow", 2: "你好啊"}

const b = test.values();
b.next(); // {value: 5, done: false}
b.next(); // {value: "hellow", done: false}
b.next(); // {value: "你好啊", done: false}
b.next(); // {value: undefined, done: true}
```


