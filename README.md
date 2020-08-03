Undefined Slots in Sapper
=========================

A minimal reproduction project to demonstrate the `undefined` slots in [Sapper][1]. Project based on [sveltejs/sapper-template][2]

Issue
-----

`$$props.$$slots` is unavailable during SSR. It is currently not possible to render conditional slots, based on whether the slot was used, e.g.:

```
{#if slots.default}
    <slot></slot>
{/if}
```

See code for more details.

Expected
--------

For `$$props.$$slots` to have references to the slots made available in the component during SSR.

Actual
------

`$$props.$$slots` is `undefined` when rendered using SSR. ($$props.$$slots is available during CSR.)

Reproduce
---------

```
npm install
npm run dev
```

Observe Sapper logs in CLI, note the output `undefined`.
Observe the client-side console contains an entry with the expected slots.

Environment
-----------

- OS: Windows 10 
- Node version: 12.16.0 
- Sapper version: 0.27.16 

[1]: https://github.com/sveltejs/sapper
[2]: https://github.com/sveltejs/sapper-template
