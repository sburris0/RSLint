<!--
 generated docs file, do not edit by hand, see xtask/docgen 
-->
# valid-typeof

Enforce the use of valid string literals in a `typeof` comparison.

`typeof` can only return a small set of strings, `undefined`, `object`,
`boolean`, `number`, `string` or `function`, and if you provide
an invalid value, it's most likely a typo, and the comparison
will always return `false`.
This behaviour will be denied by this rule.

## Invalid Code Examples
```js
typeof foo === "strnig"
typeof foo == "undefimed"
typeof bar != "nunber"
typeof bar !== "fucntion"
```

## Config
| Name | Type | Description |
| ---- | ---- | ----------- |
| `requireStringLiterals` | bool | * If this option is `true`, `typeof` expression can only be compared<br>* to valid string literals, or other `typeof` expressions, but<br>* can not be compared to any other value.<br> |

<details>
 <summary> More incorrect examples </summary>

```js
typeof foo === "strnig"
```

```js
typeof foo == "undefimed"
```

```js
typeof bar != "nunber"
```

```js
typeof bar !== "fucntion"
```
</details><br>
<details>
 <summary> More correct examples </summary>

```js
typeof foo === "string"
```

```js
typeof bar == "undefined"
```

```js
typeof foo === baz
```

```js
typeof foo === 4
```

```js
typeof bar === typeof qux
```
</details>

[Source](https://github.com/RDambrosio016/RSLint/tree/master/crates/rslint_core/src/groups/errors/valid_typeof.rs)