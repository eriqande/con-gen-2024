# con-gen-2024

This is the repo for the website
[https://eriqande.github.io/con-gen-2024/](https://eriqande.github.io/con-gen-2024/)
that Eric C. Anderson is using for teaching
materials in 2024 while teaching at the remote/online version of the UMT/Flathead Lake
Conservation Genomics Workshop.

In order to build the site, from the top level of the directory, you can do this:

```sh
# render the book that has the narratives and schedule
quarto render --to html

# render the slides individually and copy them into the docs directory
mkdir -p docs/slides
for S in prob-slides snake-slides coal-slides; do  
  quarto render $S.qmd --to revealjs &&
    cp $S.html docs/slides/$S.html
done
```