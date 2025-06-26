# ug_tt4

User Guide for the cronologic **TimeTagger4** time-to-digital converter.

This is a Sphinx project that creates the User Guide for the
[TimeTagger4](https://www.cronologic.de/product/timetagger), time-to-digital Converter
(TDC) from [cronologic GmbH & Co. KG](https://www.cronologic.de).

Find the documentation online at
[docs.cronologic.de/timetagger4](https://docs.cronologic.de/ndigo6g).

Python is necessary for creating the HTML output.

LuaLaTeX is necessary for creating the LaTeX/PDF output

## Setup and installation

Optionally, create and activate a virtual environment

```shell
python -m venv .venv
. .\.venv\Scripts\activate
```

Install the requirements of the project

```shell
pip install -r requirements.txt
```

After that, run

```shell
make html
```

or

```shell
make latexpdf
```

to compile the project as HTML or PDF. The HTML (PDF) output is in `build/html/`
(`build/latex/`).

## License

This documentation is licensed under the
[CC BY-ND 4.0](https://creativecommons.org/licenses/by-nd/4.0/) license. You are free to
copy and redistribute the material in any medium or format for any purpose, even
commercially unchanged if you give appropriate credit to cronologic GmbH & Co. KG. A
link to [this repository](https://github.com/cronologic-de/ug_tt4) or the
[product page](https://www.cronologic.de/product/timetagger) is sufficient. If you
decide to contribute to this repository, you transfer non-exclusive but unlimited rights
to your edit to cronologic GmbH & Co. KG.
![Creative Commons by-nd 4.0](https://i.creativecommons.org/l/by-nd/4.0/88x31.png)

The file [extraplaceins.sty](extraplaceins.sty) is in the public domain.
