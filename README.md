# suckless-conf

A small Lisp-like / s-expression configuration language with an
embedded scripting layer, plus `bf6`, its standalone script runtime.

## What it does

`suckless-conf` parses s-expression configuration files into a simple
`Syntax` tree (`Data.Config.Suckless.Syntax`, `.Parse`), exposes a
key-value access layer (`.KeyValue`) and bridges to Aeson, TOML, YAML
and INI. The same syntax doubles as a scripting language evaluated by
a tiny interpreter (`Data.Config.Suckless.Script`), and the package
installs the `bf6` executable that runs such scripts directly (for
example via a `#!` shebang).

## Modules

- `Data.Config.Suckless` - umbrella re-export.
- `Data.Config.Suckless.Syntax`, `.Parse`, `.Parse.Fuzzy` - the reader.
- `Data.Config.Suckless.KeyValue` - key-value access.
- `Data.Config.Suckless.Script`, `.Script.File`, `.Script.Internal` - the interpreter and `bf6` building blocks.
- `Data.Config.Suckless.System`, `.Almost.RPC` - helpers.

## Where it came from

Originally written by Dmitry Zuykov (voidlizard) inside the
[`hbs2`](https://github.com/NCrashed/hbs2) project. This Hackage
release is published from `github.com/NCrashed/suckless-conf` so
downstream projects can depend on it without vendoring.

The s-expression tokenizer and reader (`Data.Text.Fuzzy.Tokenize` and
`Data.Text.Fuzzy.SExp`) are derived from the
[`fuzzy-parse`](https://github.com/hexresearch/fuzzy-parse) package
(MIT) and bundled here as internal modules, carrying local fixes that
`suckless-conf` depends on.

## License

BSD-3-Clause for the `suckless-conf` code (see `LICENSE`); the bundled
`Data.Text.Fuzzy.*` modules are MIT (see `LICENSE.fuzzy-parse`).
Copyright holders are listed in the cabal file.
