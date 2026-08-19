- inscrutable errors
- slow compile time compared to typst
- \begin{table} puts table single column, but \begin{table\*} is double-column?
  - doesn't match other objects, e.g. equation vs equation\*
  
- easy equation label footgun (needs to be inside)

    ``` latex
    \begin{equation} 3x + 4 \end{equation}
    \label{eqn:cost_function}
    ```

- doesnt support unicode in source - e.g. O₂ fails silently as O
