# Adding a button
Adding a button requires you to add `{ .<class_name> }` to the link. It adds the button.

````
[Subscribe to our newsletter](#){ .md-button }
````

Generates the following button:

[Subscribe to our newsletter](#){ .md-button }


# Adding [[Languages/mermaid/cheatsheet|mermaid]] graphs

``` mermaid
graph LR
  A[Start] --> B{Error?};
  B -->|Yes| C[Hmm...];
  C --> D[Debug];
  D --> B;
  B ---->|No| E[Yay!];
```



$$
\operatorname{ker} f=\{g\in G:f(g)=e_{H}\}{\mbox{.}}
$$

The homomorphism $f$ is injective if and only if its kernel is only the 
singleton set $e_G$, because otherwise $\exists a,b\in G$ with $a\neq b$ such 
that $f(a)=f(b)$.

# Embedding code



````md
```rs title="test.rs" 
--8<--
code/test.rs
--8<--
```
````
