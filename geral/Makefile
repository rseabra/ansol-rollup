SOURCES = $(wildcard *.svg)
PDFs = $(SOURCES:.svg=.pdf)
PNGs = $(SOURCES:.svg=.png)

run: $(PDFs) $(PNGs)

%.png: %.svg
	inkscape -d 300 $< -e $@

%.pdf: %.svg
	inkscape -d 300 $< -A $@.tmp && gs -dSAFER -dBATCH -dNOPAUSE -dNOCACHE -sDEVICE=pdfwrite -sColorConversionStrategy=CMYK -dProcessColorModel=/DeviceCMYK -sOutputFile=$@ $@.tmp && rm -f $@.tmp

clean:
	rm -f *.pdf *.png
