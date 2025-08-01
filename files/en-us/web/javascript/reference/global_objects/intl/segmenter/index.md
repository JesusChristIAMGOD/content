---
title: Intl.Segmenter
slug: Web/JavaScript/Reference/Global_Objects/Intl/Segmenter
page-type: javascript-class
browser-compat: javascript.builtins.Intl.Segmenter
sidebar: jsref
---

The **`Intl.Segmenter`** object enables locale-sensitive text segmentation, enabling you to get meaningful items (graphemes, words or sentences) from a string.

{{InteractiveExample("JavaScript Demo: Intl.Segmenter")}}

```js interactive-example
const segmenterFr = new Intl.Segmenter("fr", { granularity: "word" });
const string = "Que ma joie demeure";

const iterator = segmenterFr.segment(string)[Symbol.iterator]();

console.log(iterator.next().value.segment);
// Expected output: 'Que'

console.log(iterator.next().value.segment);
// Expected output: ' '
```

## Constructor

- {{jsxref("Intl/Segmenter/Segmenter", "Intl.Segmenter()")}}
  - : Creates a new `Intl.Segmenter` object.

## Static methods

- {{jsxref("Intl/Segmenter/supportedLocalesOf", "Intl.Segmenter.supportedLocalesOf()")}}
  - : Returns an array containing those of the provided locales that are supported without having to fall back to the runtime's default locale.

## Instance properties

These properties are defined on `Intl.Segmenter.prototype` and shared by all `Intl.Segmenter` instances.

- {{jsxref("Object/constructor", "Intl.Segmenter.prototype.constructor")}}
  - : The constructor function that created the instance object. For `Intl.Segmenter` instances, the initial value is the {{jsxref("Intl/Segmenter/Segmenter", "Intl.Segmenter")}} constructor.
- `Intl.Segmenter.prototype[Symbol.toStringTag]`
  - : The initial value of the [`[Symbol.toStringTag]`](/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/toStringTag) property is the string `"Intl.Segmenter"`. This property is used in {{jsxref("Object.prototype.toString()")}}.

## Instance methods

- {{jsxref("Intl/Segmenter/resolvedOptions", "Intl.Segmenter.prototype.resolvedOptions()")}}
  - : Returns a new object with properties reflecting the locale and granularity options computed during initialization of this `Intl.Segmenter` object.
- {{jsxref("Intl/Segmenter/segment", "Intl.Segmenter.prototype.segment()")}}
  - : Returns a new iterable [`Segments`](/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/Segmenter/segment/Segments) instance representing the segments of a string according to the locale and granularity of this `Intl.Segmenter` instance.

## Examples

### Basic usage and difference from String.prototype.split()

If we were to use [`String.prototype.split(" ")`](/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/split) to segment a text in words, we would not get the correct result if the locale of the text does not use whitespaces between words (which is the case for Japanese, Chinese, Thai, Lao, Khmer, Myanmar, etc.).

```js example-bad
const str = "吾輩は猫である。名前はたぬき。";
console.table(str.split(" "));
// ['吾輩は猫である。名前はたぬき。']
// The two sentences are not correctly segmented.
```

```js example-good
const str = "吾輩は猫である。名前はたぬき。";
const segmenterJa = new Intl.Segmenter("ja-JP", { granularity: "word" });

const segments = segmenterJa.segment(str);
console.table(Array.from(segments));
// [{segment: '吾輩', index: 0, input: '吾輩は猫である。名前はたぬき。', isWordLike: true},
// etc.
// ]
```

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- [Polyfill of `Intl.Segmenter` in FormatJS](https://formatjs.github.io/docs/polyfills/intl-segmenter/)
- {{jsxref("Intl")}}
