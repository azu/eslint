# no assignment of the exception parameter


## Rule Details

This rule's purpose is to enforce convention. Assigning a value to the exception parameter wipes out all the valuable data contained therein and thus should be avoided. Since there is no `arguments` object to offer alternative access to this data, assignment of the parameter is absolutely destructive.

The following patterns are considered warnings:

```js
try {
    // code
} catch (e) { 
    e = 10;
}
```

The following patterns are considered okay and do not cause warnings:

```js
try {
    // code
} catch (e) { 
    var foo = 'bar';
}
```

## Notes

Related aside: there are some interesting caveats in IE 6-8 where the exception identifier will leak into the outer scope causing some unexpected behavior. Ben Alman has a [great article](http://weblog.bocoup.com/the-catch-with-try-catch/) that explains this behavior in detail

## Further Reading

* [Do not assign to the exception parameter](http://jslinterrors.com/do-not-assign-to-the-exception-parameter/)
* [The "catch" with try...catch -- Ben Alman](http://weblog.bocoup.com/the-catch-with-try-catch/)