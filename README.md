NoHoed
========
`NoHoed` is a convenience package to preserve the ability to debug your
code using Hoed. The package is designed to be used in conjunction with
Cabal flags.

Example
=======
The following excerpt of a Cabal descriptor illustrates the intended usage:
```
Flag Debug
  Description:         Enabled Hoed algorithmic debugging
  Default:             False
  Manual:              True

Library
    Exposed-Modules:     
                         Control.Arrow.Notation,
                         Control.Arrow.QuasiQuoter
    Build-Depends: base < 5,
                   array,
                   containers,
                   haskell-src-exts,
                   haskell-src-meta
    if flag(Debug)
       Build-Depends:       Hoed
       cpp-options:         -DDEBUG
    else
       Build-Depends:       NoHoed
```
