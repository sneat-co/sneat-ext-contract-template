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

> **⚠️ Rename with care — this repo has no rename script; do it by hand or
> with a tool, but NOT with a blind `s/template/<id>/g`.** A plain
> find-and-replace of the substring `template` also corrupts framework/tool
> names that happen to contain it, which have nothing to do with this repo's
> placeholder extension id. Confirmed false positives already present in this
> template (a prior blind rename on `ext-remindius` turned these into
> `strictRemindiuss` and `@angular-eslint/remindius/...`):
> - `strictTemplates` — an Angular/TypeScript compiler option in
>   `tsconfig.json`, unrelated to the extension id.
> - `@angular-eslint/template/...` — an ESLint plugin's rule namespace in
>   `eslint.config.mjs` (e.g. `@angular-eslint/template/click-events-have-key-events`).
> - `nx.configs['flat/angular-template']` — an Nx-provided ESLint config
>   preset name, also in `eslint.config.mjs`.
> - Prose uses of "template"/"templates" in comments and this README that
>   describe the *concept* of a template repo, not the placeholder id.
>
> Only rename identifiers that are actually built from the placeholder
> extension id: `@sneat/extension-template-contract`, the Nx project name
> `ext-template-contract`, the `domain:template` tag, the
> `libs/extensions/template/` path, the `prefix: 'template'` selector
> prefixes, and file names like `template-service.ts` / `template-team.ts`.

## Layout

```text
typespec/   # frozen wire contract
backend/    # contract-facing Go definitions and checks
frontend/   # @sneat/extension-<id>-contract workspace
```
