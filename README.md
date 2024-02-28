# https://tea.xyz/what-is-this-file
---
version: 1.0.0
codeOwners:
  - '0x01dC2cFB4dAFBddCc09B6D7FEd46C02a9E364Ec1'
quorum: 1

# Installation

```npm install klon```

# Usage

```javascript
clone(source[, destination][, breakCircular]);
```

**source** is the object to be copied.

**destination** (optional) is the new object, where all properties from source will be copied to.

```javascript
var klon = require('klon'),
	myObject1 = {
		a: 1,
		b: 2,
		c: {
			u: 14
		}
	},
	myObject2 = {
		c: [
			{ d: new Date() },
			{ e: "Hello" },
			{ f: "Hello" }
		]
	};

// Clone
var newObject1 = klon(myObject1);

// Extend newObject1 with myObject2
klon(myObject2, newObject1)

// Merge two objects into a new one
var newObject3 = klon(newObject2, klon(newObject1, {}) );

// Clone and break circular references
var newObject4 = klon(myObject1, {}, true);

```


# License

MIT
