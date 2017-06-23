WWWDIR = ../www

RMDFILE = spirograph.Rmd
HTMLFILE = spirograph.html

all:
	@. /etc/environ.sh; \
		use -e -r R-3.4.0; \
		use -e -r rstudio-server-1.0.143; \
		LANG="en_US.UTF-8"; \
		Rscript -e "rmarkdown::render('${RMDFILE}',output_format=c('html_document'))"

install:
	install --mode 0444 -D ${HTMLFILE} ${WWWDIR}/${HTMLFILE}
	ln -s ${HTMLFILE} ${WWWDIR}/index.html

clean:
	rm -f ${HTMLFILE}

distclean: clean
	rm -rf ${WWWDIR}/${HTMLFILE}
	rm -rf ${WWWDIR}/index.html

.PHONY: all install clean distclean

