# Simple-CV Customization Guide

This guide explains how to customize the Simple-CV template to suit your specific needs while maintaining its clean, professional aesthetic.

## Basic Information

Replace the placeholder information in the document header:

```latex
\begin{center}
  \LARGE\textbf{JOHN DOE}
\end{center}

\begin{center}
  John Doe \textbar{} 123 Main Street \textbar{} 12345 Anytown \textbar{} Country \\
  \Telefon~(555) 123-4567 \quad \Letter~\href{mailto:john.doe@example.com}{john.doe@example.com}
 \quad \(\diamond\)~www.johndoe.com
\end{center}
```

## Color Scheme

The template uses a minimalist black and white design with blue hyperlinks. You can change the hyperlink color by modifying:

```latex
\definecolor{lightblue}{RGB}{30,144,255}
\hypersetup{
    colorlinks=true,
    linkcolor=lightblue,
    filecolor=lightblue,
    urlcolor=lightblue
}
```

For a completely black and white document, you can set:

```latex
\hypersetup{
    colorlinks=false,
    hidelinks=true
}
```

## Margins and Page Layout

Adjust the page margins by modifying the geometry settings:

```latex
\geometry{a4paper, margin=2cm}
```

For more space, reduce the margins (e.g., `margin=1.5cm`). For a more traditional look, increase them (e.g., `margin=2.5cm`).

## Section Formatting

The section headings use small caps with an understated horizontal rule. Modify their appearance:

```latex
\titleformat{\section}
  {\normalfont\large\scshape}  % Format (size, small caps)
  {}
  {0em}
  {\hspace{-0.1em}}
  [{\titlerule[0.8pt]}]  % Rule thickness
\titlespacing{\section}{0pt}{12pt}{8pt}  % Spacing before/after
```

To change the rule thickness, adjust the value in `\titlerule[0.8pt]`.

## Entry Spacing

Control the spacing between entries by adjusting the value in the `\cventry` command:

```latex
\vspace{4mm}  % Space after each entry
```

## Adding Custom Sections

You can add specialized sections using the existing structures:

```latex
\section{Teaching Experience}
\begin{cvsection}
\cventry{Course Name, University}{Semester Year}
{\textit{Teaching Assistant}
\begin{itemize}
  \item Responsibilities and achievements
\end{itemize}}
\end{cvsection}
```

## Publications Section

For academics, you may want a more specialized publications section:

```latex
\newcommand{\publication}[3]{
  \item \textbf{#1}, #2, \textit{#3}
}

\section{Publications}
\begin{cvsection}
\begin{enumerate}[label={[\arabic*]}, leftmargin=1.5em, itemsep=1pt]
  \publication{Paper Title}{Author List with Your Name in Bold}{Journal/Conference, Year}
  % More publications...
\end{enumerate}
\end{cvsection}
```

## Footer Customization

Change the footer to show page numbers or other information:

```latex
\fancyfoot[R]{John Doe}  % Right footer
\fancyfoot[C]{Page \thepage\ of \pageref{LastPage}}  % Center footer
```

## List Styling

Modify the appearance of bullet points:

```latex
\setlist[itemize]{
  label=•,  % Change bullet symbol
  left=11pt,
  labelsep=0.5em,
  itemsep=1.5pt,
  nosep
}
```