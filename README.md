Knayi Myanmar Script
====================

> Standalone Myanmar languages JavaScript library, use to build Myanmar **Unicode** standard web easily.

## Features
 - Detector (Unicode and Zawgyi)
 - Converter (Unicode and Zawgyi)
 - SyallBreak (Unicode and Zawgyi)
 - Spelling Check (Unicode and Zawgyi)

## Install
Using [npm](http://npmjs.com).
```bash
npm install knayi-myscript
```

## Usage
|Method Name | Arguments | Return | Note |
| --- | --- | --- | --- |
| `fontDetect` | `content: String(require)` | `String` | Font Detector, it will detect unicode/zawgyi of the **content** Text. If nothing is matched or possibility are equal, it will return as 'zawgyi' or specified font type in **defaultFont** params. |
| `fontConvert` | `content: String(require)`,<br>`convertTo: fontName(require)`,<br>`convertFrom: fontName(optional)`| `String` | Converting font to target font type. This method need spelling fix, so it gonna use **spellingFix** in default. **convertFrom** will be detect by **fontDetect** when you don't described.<hr> `fontName` must be one of `unicode` or `zawgyi`. |
| `syllBreak` | `content: String(require)`,<br>`fontType: fontName(optional)`,<br>`breakPoint: String(optional)` | `String` |To make systematic word break of Myanmar text. convertFrom will be detect by fontDetect when you don't described.<hr> `fontName` must be one of `unicode` or `zawgyi`. |
| `spellingFix` | `content: String(require)`,<br>`fontType: fontName(optional)` | `String` | **convertFrom** will be detect by **fontDetect** when you don't described. It fix spelling on Myanmar Text.<hr> `fontName` must be one of `unicode` or `zawgyi`. |

## Example

- **fontDetect(content, [defaultFont])**
```javascript
knayi.fontDetect('မဂၤလာပါ') // zawgyi
knayi.fontDetect('မင်္ဂလာပါ') // unicode
```

- **fontConvert(content, convertTo, [convertFrom])**
```javascript
knayi.fontConvert('မဂၤလာပါ', 'unicode', 'zawgyi') // မင်္ဂလာပါ
knayi.fontConvert('မဂၤလာပါ', 'unicode') // မင်္ဂလာပါ
```

- **syllBreak(content, [fontType] [,breakPoint])**
```javascript
knayi.syllBreak('မင်္ဂလာပါ', null, '$$') // 'မင်္ဂ$$လာ$$ပါ'
```

- **spellingFix(content, [fontType])**  
```javascript
knayi.spellingFix('မင်္ဂလာာပါါ') // 'မင်္ဂလာပါ'
```

## Todo

  - [ ] Imporve Docs
  - [ ] Support to [yarn](http://yarnpkg.com)
  - [ ] Contributing guide
  - [ ] Version release note

## License
[MIT](./LICENSE)
