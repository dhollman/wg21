# WG21: C++ Standards Committee Paper Formatting

This is a fork of [Michael Park](https://mpark.github.io/)'s excellent 
ISO-C++ WG21 paper generator, with his papers removed for convenience.
(I did this so this so that it looks more like a stand-alone community tool
rather than Michael Park's personal tool.  It'd be great if we could coalesce
some community effort around this!)

## Formatting

Refer to Michael's post, [How I format my C++ papers][FMT] for an overview.

[FMT]: https://mpark.github.io/programming/2018/11/16/how-i-format-my-cpp-papers

## Generation

Documents are generated in the `generated` directory by default, and
can be overridden by `OUTDIR=<outdir>`.

```bash
make <paper>.pdf               # `<paper>.md` -> `generated/<paper>.pdf`
make <paper>.pdf OUTDIR=pdf    # `<paper>.md` -> `pdf/<paper>.pdf`

make <paper>.html              # `<paper>.md` -> `generated/<paper>.html`
make <paper>.html OUTDIR=html  # `<paper>.md` -> `html/<paper>.html`
```

## Submodule

```bash
git submodule add https://github.com/mpark/wg21.git

# Command Line

make <paper>.pdf -f wg21/Makefile               # -> `generated/<paper>.pdf`
make <paper>.pdf -f wg21/Makefile OUTDIR=pdf    # -> `pdf/<paper>.pdf`

make <paper>.html -f wg21/Makefile              # -> `generated/<paper>.html`
make <paper>.html -f wg21/Makefile OUTDIR=html  # -> `html/<paper>.html`

# `Makefile`

echo "include wg21/Makefile" > Makefile
make <paper>.pdf                                # -> `generated/<paper>.pdf`

echo "include wg21/Makefile\nOUTDIR=pdf" > Makefile
make <paper>.pdf                                # -> `pdf/<paper>.pdf`
```

## Examples

- [P1390]: Suggested Reflection TS NB Resolutions
- [P1361]: Integration of chrono with text formatting

[P1390]: https://wg21.link/p1390
[P1361]: https://wg21.link/p1361

## Requirements

  - `pdflatex`
  - `pandoc` (>= 2.7)
  - `pandoc-citeproc`
  - `python3`
  - `panflute`

### OS X

```bash
brew cask install mactex

brew install pandoc
brew install pandoc-citeproc

brew install python
pip3 install panflute
```
