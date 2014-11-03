report.pdf: report.tex sim1.pdf sim2.pdf 
	texi2pdf report.tex

sim1.dat: params.r simulator.r
	rscript simulator.r rnorm > sim1.dat

sim2.dat: params.r simulator.r
	rscript simulator.r runif > sim2.dat

sim1.pdf: sim1.dat plotter.r
	rscript plotter.r sim1.dat

sim2.pdf: sim2.dat plotter.r
	rscript plotter.r sim2.dat


.phony: all clean

all: report.pdf

clean:
	rm -f report.pdf report.log report.aux
	rm -f sim1.* sim2*
