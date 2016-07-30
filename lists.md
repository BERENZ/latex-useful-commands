# shortcut for lists - [source](http://tex.stackexchange.com/questions/52769/automatically-itemize-a-paragraph)

```{tex}
\documentclass{article}

\makeatletter

\newcommand\startitems
{%
  \begingroup
  \parindent\z@
  \@itemdepth\@ne
  \@totalleftmargin\csname leftmargin\romannumeral\the\@itemdepth\endcsname
  \leftskip\@totalleftmargin
  \everypar
  {%
    \llap{%
      \makebox[\labelsep][l]
      {%
        \csname labelitem\romannumeral\the\@itemdepth\endcsname
      }
    }%
  }%
  \obeylines
}
\newcommand\stopitems
{%
  \bottom
  \par\endgroup
}

\newcommand\up
{%
  \par
  \begingroup
    \advance\@itemdepth\@ne
    \advance\@totalleftmargin\csname leftmargin\romannumeral\the\@itemdepth\endcsname
    \leftskip\@totalleftmargin
}

\newcommand\down{\par\endgroup}

\newcommand\bottom
{%
  \ifnum\@itemdepth>\@ne
    \down\bottom
  \fi
}

\makeatother

\begin{document}

\section*{title}
\startitems
this is a line of text
this is another line of text
\up
this is a subpoint
another
\up
sub-sub  point
\bottom
back to first level
\stopitems

\noindent Normal text
\end{document}

```
