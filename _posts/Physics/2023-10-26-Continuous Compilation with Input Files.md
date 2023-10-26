---
layout: blog
title: Continuous Compilation with Input Files
---

I take notes and do exercises in LaTeX thanks to the tutorial by [Gilles Castel](https://castel.dev/post/lecture-notes-1/). However, there is one minor problem. When I work with multiple documents, the intention is usually to compile them into a single large document with \input{}. This means that I cannot have a preamble in the sub-documents, and thus cannot compile them separately. I needed a way to compile the main document every time the old document is updated.

As it turns out, this is not as hard as I expected. We open both documents simultaneously (vim doc1.tex main.tex), and then compile main.tex

Once the document is open, we simply edit doc1.tex and use :wall. This can be bound to Ctrl S with :nmap <C-s> :wall<CR>. This allows for continuous compilation even while editing documents included with \input{}