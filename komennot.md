# Git-komennot
cd ~/workspace/openscience/digihist

git add 

git commit -a -m "msg"

git log -p

git log --stat --summary


git rm -r references/ --cached
git rm  r_lang.pdf --cached

# pandoc-komennot

## suomeksi
### pdf
cd ~/workspace/openscience/digihist
~/.cabal/bin/pandoc r_lang_fi.md -o r_lang_fi.pdf --toc --number-section --filter ~/.cabal/bin/pandoc-citeproc

### html
cd ~/workspace/openscience/digihist
~/.cabal/bin/pandoc -s r_lang_fi.md -o r_lang_fi.html --toc --number-section --filter ~/.cabal/bin/pandoc-citeproc

### epub
cd ~/workspace/openscience/digihist
~/.cabal/bin/pandoc r_lang_fi.md -o r_lang_fi.epub --toc --number-section --filter ~/.cabal/bin/pandoc-citeproc

