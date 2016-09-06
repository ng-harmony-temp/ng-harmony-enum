# Ng-Harmony
============

## Development

![Harmony = 6 + 7;](logo.png "Harmony - Fire in my eyes")

Please concoct a rather useful gist here ...

## Concept

This extra lib to ng-harmony will serve the purpose of *[...]*

Use it in conjunction with

* [literate-programming](http://npmjs.org/packages/literate-programming "click for npm-package-homepage") to write markdown-flavored literate JS, HTML and CSS
* [jspm](https://www.npmjs.com/package/jspm "click for npm-package-homepage") for a nice solution to handle npm-modules with ES6-Module-Format-Loading ...

## Files

This serves as literate-programming compiler-directive

[build/index.js](#Compilation "save:")

You can extend these literate-programming directives here ... the manual is (on jostylr@github/literate-programming)[https://github.com/jostylr/literate-programming]

## Compilation

Now just start coding/commenting as you go ...

You might want to
    * code on the fly
    * use literate-programming as a full paradigm of some super-constructor
    * switch back and forth between the dev/master and gh-pages branches and use TDD/BDD

Imports

```javascript
// @flow
import { Mixin, UniqueArray } from "ng-harmony-decorator";
import { Service } from "ng-harmony-core";
```

The EnumService is an _Injectable_ that allows for app-wide unique Enum-Values.
It uses the _2^(0-n)_ operation to guarantee parsability of Enum-Sums.
Thusly one can use them eg. for a collective value of a subsummised super-component/app -state ...

*Example:*

SuperComponent State: 31

SubComponent1 State: 16
SubComponent2 State: 8
SubComponent3 State: 7

SubComponent3-Subcomponent State: 4
SubComponent3-Subcomponent State: 2
SubComponent3-Subcomponent State: 1


```javascript
export class EnumService extends Service {
    @UniqueArray()
    store;
    seed = 1;
    generate (o) {
        o.uid = this.seed;
        this.seed *= 2;
        this.store = o;
        return o;
    }
    parse (n) {
        return store.filter((enumerated) => {
            return (enumerated.uid === n);
        })[0] || null;
    }
}

export class Enum extends Service {
    uid = this.EnumService.generate(this);
    name = this.constructor.name;
}
Enum.$inject = "EnumService";

export class Plug extends Enum {}

export class EventPlug extends Plug {
    event = {
        selector: null,
        nthChild: null
        trigger: null
    };
}
```

## CHANGELOG

*v0.1.1* Plug, EventPlug
*v0.1.0* EnumService, StateEnum
