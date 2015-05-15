iNEXT (R package)
=================

<h4 style="text-align: right;">
Most recent update time: January 8, 2014 by Hsieh, T. C., K. H. Ma, and
A. Chao Institute of Statistics, National Tsing Hua University,
Hsin-Chu, Taiwan 30043
</h4>
The program iNEXT (iNterpolation and EXTrapolation) is an updated R
package from the original version supplied in Appendix of Chao et al.
(2014). In this updated version, we have added more user-friendly
features. Please notice the updated time and replace your old version by
the most recent one.

The user provides a vector of abundances of individual species
(abundance data) or incidences of individual species (incidence data).
iNEXT computes the iNEXT computes the following species richness
estimates and associated 95% confidence intervals:

1.  Sample-size-based rarefaction and extrapolation: species richness
    estimates for rarefied and extrapolated samples up to a size
    specified by the user (i.e., an endpoint, see below). Refer to
    Colwell et al. (2012) for details.
2.  Coverage-based rarefaction and extrapolation: species richness
    estimates for rarefied and extrapolated samples for sample coverage
    up to a coverage specified by the user (i.e., an endpoint, see
    below). Refer to Chao and Jost (2012) for details.

iNEXT also plots the following three integrated sampling curves
suggested in Chao et al. (2014) for unified sampling and estimation in
species diversity analysis.

1.  Sample-size-based rarefaction and extrapolation sampling curve: this
    curve plots the species richness estimates for a rarefied and
    extrapolated sample with respect to sample size up to a specified
    endpoint.

<!-- -->

    plot(object.iNEXT, type=1) # S3 method
    ggiNEXT(object.iNEXT, type=1) # ggplot2 method

1.  Sample completeness curve: this curve plots the sample completeness
    (as measured by sample coverage) with respect to sample size. The
    curve provides a bridge between sample-size- and coverage-based
    rarefaction and extrapolation.

<!-- -->

    plot(object.iNEXT, type=2) # S3 method
    ggiNEXT(object.iNEXT, type=2) # ggplot2 method

1.  Coverage-based rarefaction and extrapolation sampling curve: this
    curve plots the species richness estimates for rarefied sample and
    extrapolated sample with respect to sample coverage up to a
    specified endpoint.

<!-- -->

    plot(object.iNEXT, type=3) # S3 method
    ggiNEXT(object.iNEXT, type=3) # ggplot2 method

### Software needed to run the development version

-   Required: [R](http://cran.rstudio.com/)
-   Suggested: [RStudio IDE](http://www.rstudio.com/ide/download/)

### How to run: start R(Studio) and copy-and-paste the following commands:

Start R(Studio) and copy-and-paste the commands below:

    install.packages('devtools')
    library(devtools)
    install_github('JohnsonHsieh/iNEXT')
    library(iNEXT)

Remark that in order to install `devtools` package, you should update R
to the last version. Further, to get `install_github` to work, you
should install the `httr` package.

### Example

Copy-and-paste the commands below:

    data(spider)
    out <- iNEXT(spider, q=c(0, 1, 2), datatype="abundance", endpoint=500)
    ggiNEXT(out, type=1, facet.var="site")

![](./README_files/figure-markdown_strict/ex1-1.png)

    ggiNEXT(out, type=1, facet.var="order")

![](./README_files/figure-markdown_strict/ex1-2.png)

    # plot(out, type=1) 

    ggiNEXT(out, type=2, facet.var="none", color.var="site")

![](./README_files/figure-markdown_strict/ex2-1.png)

    # plot(out, type=2)

    ggiNEXT(out, type=3, facet.var="site")

![](./README_files/figure-markdown_strict/ex3-1.png)

    ggiNEXT(out, type=3, facet.var="order")

![](./README_files/figure-markdown_strict/ex3-2.png)

    # plot(out, type=3)

Run a sample-based example

    data(ant)
    iNEXT(ant$h50m, q=c(0,1,2), datatype="incidence") 

### How to cite

If you use iNEXT to obtain results for publication, you should cite at
least one of the relevant papers (Chao and Jost 2012; Colwell et al.
2012; Chao et al. 2013) along with the following reference for iNEXT:

> Hsieh, T. C., K. H. Ma, and A. Chao. 2014. iNEXT: An R package for
> interpolation and extrapolation in measuring species diversity.
> Unpublished manuscript.

### License

The iNEXT package is licensed under the GPLv2. To help refine iNEXT,
your comments or feedbacks would be welcome (please send them to [Anne
Chao](chao@stat.nthu.edu.tw)).

### Referance

1.  Chao, A., N. J. Gotelli, T. C. Hsieh, E. L. Sander, K. H. Ma, R. K.
    Colwell, and A. M. Ellison 2014. Rarefaction and extrapolation with
    Hill numbers: a unified framework for sampling and estimation in
    biodiversity studies, Ecological Monographs 84:45-67.
2.  Chao, A., and L. Jost. 2012. Coverage-based rarefaction and
    extrapolation: standardizing samples by completeness rather than
    size. Ecology 93:2533-2547.
3.  Colwell, R. K., A. Chao, N. J. Gotelli, S. Y. Lin, C. X. Mao, R. L.
    Chazdon, and J. T. Longino. 2012. Models and estimators linking
    individual-based and sample-based rarefaction, extrapolation and
    comparison of assemblages. Journal of Plant Ecology 5:3-21.
4.  Ellison, A. M., A. A. Barker-Plotkin, D. R. Foster, and D. A. Orwig.
    2010. Experimentally testing the role of foundation species in
    forests: the Harvard Forest Hemlock Removal Experiment. Methods in
    Ecology and Evolution 1:168-179.
5.  Hsieh, T. C., K. H. Ma, and A. Chao. 2013. iNEXT online:
    interpolation and extrapolation (Version 1.3.0) [Software].
    Available from
    <http://chao.stat.nthu.edu.tw/blog/software-download/>.
6.  Hsieh T. C., K. H. Ma, and A. Chao. 2014. iNEXT: An R package for
    interpolation and extrapolation in measuring species diversity.
    Unpublished manuscript.
7.  Longino, J. T., and R. K. Colwell. 2011. Density compensation,
    species composition, and richness of ants on a neotropical
    elevational gradient. Ecosphere 2:art29.
8.  Sackett, T. E., S. Record, S. Bewick, B. Baiser, N. J. Sanders, and
    A. M. Ellison. 2011. Response of macroarthropod assemblages to the
    loss of hemlock (Tsuga canadensis), a foundation species. Ecosphere
    2: art74.
