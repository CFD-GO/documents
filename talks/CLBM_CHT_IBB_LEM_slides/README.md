# ZA beamer template

This theme is based on the Metropolis packge ([Metropolis repository](https://github.com/matze/mtheme)). I have changed few colors and included MEiL and PW logos. To use it just place all files in proper directory and edit (e. g. change the name) the template_example.tex file. This file contains few examples of using beamer with this theme.

Below 2 Metropolis usefull links
[demo slides]: http://mirrors.ctan.org/macros/latex/contrib/beamer-contrib/themes/metropolis/demo/demo.pdf
[manual]: http://mirrors.ctan.org/macros/latex/contrib/beamer-contrib/themes/metropolis/doc/metropolistheme.pdf


## Metorpolis Usage

The following code shows a minimal example of a Beamer presentation using
Metropolis.

```latex
\documentclass{beamer}
\usetheme{metropolis}           % Use metropolis theme
\title{A minimal example}
\date{\today}
\author{Matthias Vogelgesang}
\institute{Centre for Modern Beamer Themes}
\begin{document}
  \maketitle
  \section{First Section}
  \begin{frame}{First Frame}
    Hello, world!
  \end{frame}
\end{document}
```
## Fira fonts installation (debian based OS - tested on Ubuntu 18.04)
```shell
wget https://github.com/bBoxType/FiraSans/archive/master.zip
unzip master.zip
sudo mkdir -p /usr/share/fonts/opentype/fira
sudo mkdir -p /usr/share/fonts/truetype/fira
sudo find FiraSans-master/ -name "*.otf" -exec cp {} /usr/share/fonts/opentype/fira/ \;
sudo find FiraSans-master/ -name "*.ttf" -exec cp {} /usr/share/fonts/truetype/fira/ \;
```
## License

The theme itself is licensed under a [Creative Commons Attribution-ShareAlike
4.0 International License](http://creativecommons.org/licenses/by-sa/4.0/). This
means that if you change the theme and re-distribute it, you *must* retain the
copyright notice header and license it under the same CC-BY-SA license. This
does not affect the presentation that you create with the theme.



