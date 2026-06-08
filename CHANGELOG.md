# Revision history for suckless-conf

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
