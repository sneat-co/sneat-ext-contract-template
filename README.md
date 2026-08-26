# sneat-ext-contract-template

> **DEFAULT: new extension contracts are created as `libs/<family>/` in
> [`sneat-co/sneat-ext-contracts`](https://github.com/sneat-co/sneat-ext-contracts)
> (see its README + the scaffold generator). Use this template ONLY when a
> standalone repo has been explicitly decided by the founder.**

Template repository for creating a public `ext-<id>` contract repository.
The guidance below applies to that exception case.

`frontend/` is the sole owner and publisher of
`@sneat/extension-template-contract`. The paired implementation template is
[`sneat-ext-template`](../sneat-ext-template); it consumes this package and owns
the runtime/app code.

For a new extension, create `ext-<id>` from this template, rename `template`,
publish the contract, and then point the `<id>` implementation at that release.

## Layout

```text
typespec/   # frozen wire contract
backend/    # contract-facing Go definitions and checks
frontend/   # @sneat/extension-<id>-contract workspace
```
