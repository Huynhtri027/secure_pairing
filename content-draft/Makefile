TEXFILE=content_draft
BIBFILE=references

SRCDIR=.
BIBDIR=${SRCDIR}/../references
TMPDIR=${SRCDIR}/tmp

TEXFLAGS=-output-directory ${TMPDIR}

build: ${SRCDIR}/*.tex ${BIBDIR}/*.bib
	mkdir -p ${TMPDIR}
	pdflatex ${TEXFLAGS} ${SRCDIR}/${TEXFILE}.tex
	bibtex ${TMPDIR}/${TEXFILE}.aux
	pdflatex ${TEXFLAGS} ${SRCDIR}/${TEXFILE}.tex
	pdflatex ${TEXFLAGS} ${SRCDIR}/${TEXFILE}.tex
	mv -f ${TMPDIR}/${TEXFILE}.pdf ${SRCDIR}/

clean:
	rm -rf ${TMPDIR}

distclean: clean
	rm ${SRCDIR}/${TEXFILE}.pdf
