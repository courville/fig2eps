# Fig2eps: a tool to convert xfig figures to eps with embedded LaTeX commands

## Motivation

When I did my PhD (long ago?), I faced the challenge to generate clean eps figures containing some mathematical formulas from my xfig figures. For that purpose I produced the fig2eps script that does the job. Note that since the first version of the script, both Laurent Mazet and Cyril Humbert have contributed to various useful enhancements (e.g. inclusion of a resource file containing LaTeX macros). The result of these contributions are included in the current version.

## Usage

    Usage: fig2eps [-h] [-m level] [-r resource]  <file[.fig]>...

    -h            display help (this page)
    -m level      set magnification level. A value of 1000 corresponds to
                  100% and the scale is linear. Default value is [1000].
    -r resource   specifies the name of a resource file which contains TeX macros.
	      TeX macro must be one line to allow multiple resource files.
              By default, it tries to open ~/.fig2epsrc
    -v            show version.
    -x            exclude standard resource file.


    <file1> <file2>... figure's name

The fig2eps script generates the encapsulated postscript file `<filename>.eps`
to be included as a figure in any document based on the `<filename>.fig`
xfig figure file (e.g. for latex with `graphics.cls`).

This script allows to generate an encapsulated postscript figure created
by xfig containing text and equations to be processed by latex.
Fonts are scaled properly.  The fonts to be used in xfig are the latex
fonts. In that purpose it is thus convenient to use the following command
to launch xfig:

    xfig -Portrait -specialtext -latexfonts -startlatexFont default
