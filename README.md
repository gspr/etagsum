# Entity tag (Etag) sums

This very simple and naïve program computes entity tag (Etag)
checksums, à la those reported by various AWS components.

See also
[https://nonempty.org/software/etagsum](https://nonempty.org/software/etagsum).

## About

This software is in no way affiliated with AWS.

The code is licensed under the GNU General Public License, verson 3.0.

## Installing

For now, etagsum is just a single executable Python script
`bin/etagsum`, and can be installed any way you like. All Python 3
versions should be supported.

## Running

Invocations are similar to those of `sha256sum` and friends from GNU
Coreutils, but one needs to explicitly specify the chunk size. This is
done with the `--size` switch. In
```
etagsum --size 8M a b --size 16M c
```
the files `a` and `b` are checksummed with a chunk size of 8 MB, and
`c` with a size of 16 MB. AWS tools tend to pick 8 or 16 MB as defaults.

More options can be seen by running `etagsum --help`.

