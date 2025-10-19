# Figures

This directory contains images to be included in the figures of your LaTeX documents.

Place your image files (`.pdf`, `.png`, `.jpg`, etc.) here and reference them in your `.tex` files using:

```latex
\begin{figure}[htbp]
  \centering
  \includegraphics[width=0.8\textwidth]{figures/your-image.pdf}
  \caption{Your figure caption here}
  \label{fig:your-label}
\end{figure}
```
