all: paper

# If you decide to go with pandoc-citeproc
#	pandoc -s -F pandoc-crossref -F pandoc-citeproc meta.yaml --data-dir=data-dir --template=mytemplate.tex -N \
#	-f markdown -t latex+raw_tex+tex_math_dollars+citations -o main.pdf main.md

# You can still use pandoc-crossref to easily reference figures with [@fig:label]

paper:
	@pandoc -s -F pandoc-crossref --natbib meta.yaml --template=mytemplate.tex -N \
	 -f markdown+raw_tex+tex_math_dollars+citations -t latex -o main.tex main.md
	@pdflatex main.tex > /dev/null 2>&1
	@bibtex main > /dev/null 2>&1
	@pdflatex main.tex > /dev/null 2>&1
