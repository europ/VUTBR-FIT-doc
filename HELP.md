# HELP

#### Removing bibliography

* Remove command `bibtex $(FILE)` from `Makefile`.
* Remove bibliography related LaTeX code at the end of `doc.tex` file.
	```
	\section{Bibliography}
	\bibliographystyle{englishiso}
	\begin{flushleft}
		  \bibliography{quotation}
	\end{flushleft}
	```
