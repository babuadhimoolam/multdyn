clean:
	rm -rf ./multdyn/NAMESPACE multdyn*tar.gz multdyn.Rcheck

namespace:
	echo "importFrom(utils, combn)"   >> ./multdyn/NAMESPACE
	echo "importFrom(stats, binom.test, "p.adjust")" >> ./multdyn/NAMESPACE
	echo "importFrom(utils, glob2rx)" >> ./multdyn/NAMESPACE
	echo "importFrom(stats, cor)" >> ./multdyn/NAMESPACE
	echo "importFrom(stats, var)" >> ./multdyn/NAMESPACE
	echo "importFrom(stats, quantile)" >> ./multdyn/NAMESPACE
	echo "importFrom(data.table, fread)" >> ./multdyn/NAMESPACE
	echo "importFrom(reshape2, melt)" >> ./multdyn/NAMESPACE
	echo "importFrom(ggplot2, ggplot, aes_string, geom_tile, scale_fill_gradient2, theme, element_blank, element_text, scale_y_reverse, scale_x_continuous, ggtitle, guides, waiver)" >> ./multdyn/NAMESPACE
	sed -i '1s/^/importFrom(Rcpp, evalCpp)\n/' multdyn/NAMESPACE	
	sed -i '1s/^/exportPattern("^[[:alpha:]]+")\n/' multdyn/NAMESPACE
	sed -i '1s/^/useDynLib(multdyn, .registration = TRUE)\n/' multdyn/NAMESPACE

build:
	R CMD build multdyn

check:
	R CMD check --as-cran $(file)
