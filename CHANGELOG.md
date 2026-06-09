# Revision history for suckless-conf

## 0.1.2.12 2026-06-09

  - Raise `prettyprinter-ansi-terminal` lower bound to `>= 1.1.2`: the
    `Prettyprinter.Render.Terminal` module (used by
    `Data.Config.Suckless.Script.Internal`) only exists from 1.1.2 on;
    earlier versions use the pre-rename `Data.Text.Prettyprint.Doc.*`
    names.

## 0.1.2.11 2026-06-09

  - Fix: import `ExitCode(..)` explicitly in
    `Data.Config.Suckless.Almost.RPC` instead of relying on a
    transitive re-export from `typed-process`. Older `typed-process`
    (e.g. 0.2.4.1, selected on GHC 9.4 with `--prefer-oldest`) does not
    re-export the type or the `ExitSuccess` constructor, so the package
    failed to compile there. No API or behaviour change.

## 0.1.2.10 2026-06-09

Bump versions:
  - mtl >= 2.3 -> >= 2.2
  - transformers >= 0.6 -> >= 0.5
  - interpolatedstring-perl6 >= 1.0 -> >= 1.0.2

## 0.1.2.9  2026-06-08

First Hackage release. Previously this package only lived as a
vendored subtree inside the `hbs2` repository; the source moves to
`github.com/NCrashed/suckless-conf` for independent maintenance.

  - No behavioural changes from the vendored 0.1.2.9.
  - The s-expression tokenizer and reader (`Data.Text.Fuzzy.Tokenize`
    and `Data.Text.Fuzzy.SExp`) are now bundled as internal modules,
    folded in from the `fuzzy-parse` package (MIT) with the local
    fixes this package depends on; the external `fuzzy-parse`
    dependency is dropped.
  - `Data.Config.Suckless.Parse.Fuzzy` and
    `Data.Config.Suckless.Script.Internal` moved from internal
    `other-modules` to `exposed-modules` so Hackage consumers can
    import them.
  - Cabal metadata filled in: synopsis, description, homepage,
    bug-reports, source-repository, `tested-with`, explicit version
    bounds on every dependency.
  - Maintainer is now `Anton Gushcha <ncrashed@gmail.com>`; original
    authorship by Dmitry Zuykov is preserved.
