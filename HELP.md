# HELP

### Custom logo

* VUT logos are available [here](https://www.vutbr.cz/jvs).
* To change doc logo, add it to the `img/` folder and change the code below properly
  ```tex
  \includegraphics[scale=0.3]{vutbr-fit-logo.eps}
  ```

### No bibliography

* Remove command `bibtex $(FILE)` from `Makefile`.
* Remove bibliography related LaTeX code at the end of `doc.tex` file.
  ```tex
  \section{Bibliography}
  \bibliographystyle{englishiso}
  \begin{flushleft}
      \bibliography{quotation}
  \end{flushleft}
  ```

### Multiple person on the title page

* Change the related code to the following code
  ```tex
  \Large{
      \hfill\\
      Name Surname (xlogin00)\\
      Name Surname (xlogin00) \hfill \today
  }
  ```
