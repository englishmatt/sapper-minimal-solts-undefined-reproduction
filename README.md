Undefined Slots in Sapper
=========================

A minimal reproduction project to demonstrate the `undefined` slots in [Sapper][1]. Project based on `npx degit "sveltejs/sapper-template#rollup" my-app`.

Issue
-----

`$$props.$$slots` is unavailable during SSR. See code for more details.

[1]: https://github.com/sveltejs/sapper

Expected
--------

`$$props.$$slots` to not be undefined; instead to have references to the slots made available in the component.

Actual
------

`$$props.$$slots` is `undefined`.

Reproduce
---------

```
npm install
npm run dev
```

Observe Sapper logs in CLI, note the output `undefined`.

Environment
-----------

OS: Windows 10
Node version: 12.16.0
Sapper version: 0.27.16
