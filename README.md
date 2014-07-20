<div id="table-of-contents">
<h2>Table of Contents</h2>
<div id="text-table-of-contents">
<ul>
<li><a href="#sec-1">1. CL Machine-Learning</a>
<ul>
<li><a href="#sec-1-1">1.1. Author(s):</a>
<ul>
<li><a href="#sec-1-1-1">1.1.1. Original</a></li>
<li><a href="#sec-1-1-2">1.1.2. Current Branch Maintainer(s)/Authors(s):</a></li>
</ul>
</li>
<li><a href="#sec-1-2">1.2. Installation</a></li>
<li><a href="#sec-1-3">1.3. Requirements</a></li>
<li><a href="#sec-1-4">1.4. Installation Notes</a>
<ul>
<li><a href="#sec-1-4-1">1.4.1. Obtaining code</a></li>
<li><a href="#sec-1-4-2">1.4.2. Installing</a></li>
<li><a href="#sec-1-4-3">1.4.3. External Dependencies <b>*</b></a></li>
</ul>
</li>
<li><a href="#sec-1-5">1.5. Documentation</a>
<ul>
<li><a href="#sec-1-5-1">1.5.1. User and API Documentation</a></li>
</ul>
</li>
<li><a href="#sec-1-6">1.6. Sample Data</a></li>
<li><a href="#sec-1-7">1.7. Usage</a></li>
</ul>
</li>
</ul>
</div>
</div>


# CL Machine-Learning

CL Machine-Learning is high performance and large scale statistical
machine learning package written in Common Lisp developed at 
[MSI](http://cl-www.msi.co.jp). 

## Author(s):

### Original

-   Salvi Péter
-   Naganuma Shigeta
-   Tada Masashi
-   Abe Yusuke
-   Jianshi Huang
-   Fujii Ryo
-   Abe Seika
-   Kuroda Hisao

### Current Branch Maintainer(s)/Authors(s):

-   Mike Maul

This repository contains is a modified version of CLML with the following goals in mind:

-   Remove dependent libraries available from the Quicklisp repository
-   Re-factor code to support Quicklisp packaging
-   Organize code into independent systems based on functional category
-   Support for Clozure Common Lisp short term and CLisp and ECL long term
-   Improve documentation

## Installation

## Requirements

-   Language: SBCL, Clozure Common Lisp, Allegro or Lispworks
-   Platform: Posix compatibile platforms (Windows, Linux, BSD and derivatives)
-   Optionally Intel Math Kernel Library
-   ASDF3 and optionally Quicklisp (This document assumes [Quicklisp](http://quicklisp.org))
-   C compiler
-   gfortran compiler

Currently development is taking place mostly on SBCL. For the near future SBCL is most stable platform.    

## Installation Notes

### Obtaining code

Code can be obtained by one of the following methods:
-   Clone this repository with:

    git clone https://github.com/mmaul/clml.git

Or download zip archive at

    https://github.com/mmaul/clml/archive/master.zip

### Installing

1.  For Quicklisp **\*\***

    1.  Place code in `~/quicklisp/local-projects`
    2.  Start LISP and enter `(ql:quickload :clml)`

2.  For ASDF3 only (Non quicklisp users)

    1.  Place in a location on your ASDF search path path such as `~/common-lisp`
    2.  Start LISP and enter `(asdf:load-system :clml)`

### External Dependencies **\***

    :alexandria
    :iterate
    :f2cl
    :simple-queue
    :clod
    :split-sequence
    :cl-ppcre
    :parse-number

## Documentation

### User and API Documentation

User and API documentation may be found on line at <http://mmaul.github.io/clml/>
and also in the project directories docs/clml-manual.html 
Notes and Algorithmic Details and Background    
    files in memo, notes and docs

## Sample Data

The sample datasets are located outside the CLML repository.
Fortunately CLML is able to download sample datasets from remote sites
via HTTP and HTTPS via the `clml.utility.data:fetch` function. Shown
below is an example:

    (clml.utility.data:fetch "https://mmaul.github.io/clml.data/sample/datafile.csv")

The `clml.utility.data:fetch` function downloads the file to a cache
location and returns the path to the downloaded file. Therefore
anywhere a path to a file is required the output from
`clml.utility.data:fetch` can be provided instead.

The contents of the Sample dataset repository can be found at:

-   [ CLML Extras: <http://mmaul.github.io/clml.data/> ](http://mmaul.github.io/clml.data/)

## Usage

This library is orginized as a hierarchical tree of systems, currently with two root
nodes clml and hjs. hjs is the core.
-   clml
-   clml.association-rule
    -   clml.association-rule
-   clml.classifiers
    -   clml.classifiers.linear-regression
    -   clml.classifiers.logistic-regression
    -   clml.classifiers.nbayes
-   clml-clml.statistics
    -   clml-clml.statistics
-   clml.clustering
    -   clml.clustering.cluster-validation
    -   clml.clustering.hc
    -   clml.clustering.k-means2
    -   clml.clustering.nmf
    -   clml.clustering.optics
    -   clml.clustering.optics-speed
    -   clml.clustering.spectral-clustering
-   clml.decision-tree
    -   clml.decision-tree.decision-tree
    -   clml-decision-tree.random-forest
-   clml.graph
    -   clml.graph.graph-anomaly-detection
    -   clml.graph.graph-centrality
    -   clml.graph.graph-utils
    -   clml.graph.read-graph
    -   clml.graph.shortest-path
-   clml.nearest-search
    -   clml.nearest-search.k-nn
    -   clml.nearest-search.k-nn-new
    -   clml.nearest-search.nearest
-   clml.nonparameteric
    -   clml.nonparameteric.statistics
    -   clml.nonparametric.blocked-hdp-hmm
    -   clml.nonparametric.dpm
    -   clml.nonparametric.ftm
    -   clml.nonparametric.hdp
    -   clml.nonparametric.hdp-hmm
    -   clml.nonparametric.hdp-hmm
    -   clml.nonparametric.hdp-lda
    -   clml.nonparametric.ihmm
    -   clml.nonparametric.lfm
    -   clml.nonparametric.sticky-hdp-hmm
    -   clml.numeric.fast-fourier-transform
-   clml.pca
    -   clml.pca
-   clml.som
    -   clml.som
-   clml.statistics
    -   clml.statistics
    -   clml.statistics.rand
-   clml.svm
    -   clml.svm.mu
    -   clml.svm.one-class
    -   clml.svm.pwss3
    -   clml.svm.smo
    -   clml.svm.svr
    -   clml.svm.wss3
-   clml.time-series
    -   clml.time-series.anomaly-detection
    -   clml.time-series.autoregression
    -   clml.time-series.burst-detection
    -   clml.time-series.changefinder
    -   clml.time-series.exponential-smoothing
    -   clml.time-series.read-data
    -   clml.time-series.state-space
    -   clml.time-series.statistics
    -   clml.time-series.util
-   clml.utility
    -   clml.utility.csv
    -   clml.utility.priority-que
-   fork-future
-   future
-   hjs
    -   hjs.learn.k-means
    -   hjs.learn.read-data
    -   hjs.learn.vars
    -   hjs.util.eigensystems
    -   hjs.util.matrix
    -   hjs.util.meta
    -   hjs.util.missing-value
    -   hjs.util.vector
-   lapack

Each system can be loaded independantly or the the clml system can be loaded which contains
dependencies to all child system definitions.

This library requires that default reader float for mat is set to double-float. This should
be done before loading the systems.

    (setf *read-default-float-format* 'double-float)
-   Example below is using CLML.EXTRAS

Here is a quick demonstration:

    CL-USER (ql:quickload :clml)
    
    CL-USER (clml.text.utilities:calculate-levenshtein-similarity "Howdy" "doody")
    0.6
    CL-USER 
    CL-USER (setf *syobu* (hjs.learn.read-data:read-data-from-file 
               (clml.utility.data:fetch "https://mmaul.github.io/clml.data/sample/syobu.csv")
               :type :csv :csv-type-spec '(string integer integer integer integer)))
    
    
    #<HJS.LEARN.READ-DATA:UNSPECIALIZED-DATASET >
    DIMENSIONS: 種類 | がく長 | がく幅 | 花びら長 | 花びら幅
    TYPES:      UNKNOWN | UNKNOWN | UNKNOWN | UNKNOWN | UNKNOWN
    NUMBER OF DIMENSIONS: 5
    DATA POINTS: 150 POINTS
    
    CL-USER (setf *tree* (clml.decision-tree.decision-tree:make-decision-tree *syobu* "種類"))
    
    
    (((("花びら長" . 30)
       (("花びら幅" . 18) ("花びら幅" . 23) ("花びら幅" . 20) ("花びら幅" . 19) ("花びら幅" . 25)
        ("花びら幅" . 24) ("花びら幅" . 21) ("花びら幅" . 14) ("花びら幅" . 15) ("花びら幅" . 22)
         ("花びら幅" . 16) ("花びら幅" . 17) ("花びら幅" . 13) ("花びら幅" . 11) ("花びら幅" . 12)
      ...
      (("Virginica" . 50) ("Versicolor" . 50) ("Setosa" . 50))
      ((149 148 147 146 145 144 143 142 141 140 139 138 137 136 135 134 133 132 131
      ...
     (((("花びら幅" . 18)
        (("花びら幅" . 23) ("花びら幅" . 20) ("花びら幅" . 19) ("花びら幅" . 25) ("花びら幅" . 24)
         ("花びら幅" . 21) ("花びら幅" . 14) ("花びら幅" . 15) ("花びら幅" . 22) ("花びら幅" . 16)
         ("花びら幅" . 17) ("花びら幅" . 13) ("花びら幅" . 11) ("花びら幅" . 12) ("花びら幅" . 10)
     ...
    
    )))
    CL-USER    
    CL-USER  (clml.decision-tree.decision-tree:print-decision-tree *tree*)
        [30 <= 花びら長?]((Virginica . 50) (Versicolor . 50) (Setosa . 50))
           Yes->[18 <= 花びら幅?]((Versicolor . 50) (Virginica . 50))
             Yes->[49 <= 花びら長?]((Virginica . 45) (Versicolor . 1))
                 Yes->((Virginica . 43))
                 No->[60 <= がく長?]((Versicolor . 1) (Virginica . 2))
                    Yes->((Virginica . 2))
                    No->((Versicolor . 1))
              No->[50 <= 花びら長?]((Virginica . 5) (Versicolor . 49))
                 Yes->[16 <= 花びら幅?]((Versicolor . 2) (Virginica . 4))
                    Yes->[70 <= がく長?]((Virginica . 1) (Versicolor . 2))
                       Yes->((Virginica . 1))
                       No->((Versicolor . 2))
                    No->((Virginica . 3))
                 No->[17 <= 花びら幅?]((Versicolor . 47) (Virginica . 1))
                    Yes->((Virginica . 1))
                      No->((Versicolor . 47))
           No->((Setosa . 50))