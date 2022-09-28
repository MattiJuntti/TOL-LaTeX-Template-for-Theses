# TOL LaTeX Template for Theses

A template for LaTeX document adhering to the layout given in University of
Oulu's &ldquo;BSc and MSc Formal Instructions&rdquo; / &ldquo;[Template for
theses][01]&rdquo; for students of [TOL][02] ([Information Processing
Science][02]).

## Template Structure

The template has the following structure

```
.
├── cfg
│   ├── document-settings.tex
│   ├── packages-settings.tex
│   └── packages.tex
├── img
│   ├── uni-logo.pdf
│   └── uni-logo.png
├── pre
│   ├── abstract.tex
│   ├── foreword.tex
│   └── title.tex
├── sec
│   ├── 01-introduction.tex
│   └── 02-example-section.tex
├── main.tex
├── Makefile
├── README.md
└── references.bib
```

## How to use?

### Steps

1. Add the `.tex` file containing section text to the `sec` directory.
1. Open `main.tex` in editor and add `\input{sec/<filename>}` under the entries of &ldquo;`Input sections`&rdquo; line.
1. Run `make`.

<details>
<summary><strong>Detailed explanation of the steps above</strong></summary>

1. Add the `.tex` file containing your section text to the `sec` directory.

   For example, assume that a section called `03-foobar.tex` is written. Then it
   can be added to `sec` directory. This would make the `sec` directory's
   structure look like

   ```
    ├── sec
    │   ├── 01-introduction.tex
    │   ├── 02-example-section.tex
    │   └── 03-foobar.tex            <-- The newly added file
   ```

1. Open `main.tex` in editor and add `\input{sec/<filename>}` under the entries of &ldquo;`Input
   sections`&rdquo; line.

    If the file is the `03-foobar.tex` and the `Input sections` is

    ```
    % Input sections
    \input{sec/01-introduction.tex}
    \input{sec/02-example-section.tex}
    ```
    
    adding the `\input{sec/03-foobar.tex}` would make the `Input sections` look
    like

    ```
    % Input sections
    \input{sec/01-introduction.tex}
    \input{sec/02-example-section.tex}
    \input{sec/03-foobar.tex}           <-- The newly added entry
    ```

1. Run `make`.

    This will make the file of the name defined by the `DOCUMENT` variable in
    the `Makefile` appear in the root of the directory.

    The default name for the compiled document is `Dissertationtitle.pdf`, but
    this can be changed in the `Makefile` at line

    ```
    DOCUMENT = Dissertationtitle.pdf
    ```
</details>

## More information

All of the files have documentation in them on how any given file contributes to
the compilation of the document.

## Deviations

1. The default typeface used in the section headers is _Helvetica_ instead of _Arial_.
1. The title page's logo is a colored version of the University's logo.

<!-- Web links -->
[01]: https://www.oulu.fi/en/for-students/thesis-and-graduation/graduation-masters-degree/masters-thesis#174
[02]: https://www.oulu.fi/en/for-students/thesis-and-graduation/graduation-masters-degree/masters-thesis#174 
