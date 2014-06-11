HyperLogLog++
===========

A fork of Eric Lesh's Go implementation of HyperLogLog https://github.com/eclesh/hyperloglog , attempting to incorporate Google's HyperLogLog++ empirical improvements from the 2013 research paper:

http://research.google.com/pubs/pub40671.html

Namely:

1. 64-bit hashed inputs replacing large range correction. FNV 64-bit is used in the example.
2. Switch-off between LinearCounting and bias corrected raw estimate
3. Sparse representation where useful

At the moment 8-bit bytes are used in the registers, but converting to 6-bit registers would be an additional efficiency improvement.

This fork is untested and should not be incorporated into production code.


hyperloglog
===========

Package hyperloglog implements the HyperLogLog algorithm for
cardinality estimation. In English: it counts things. It counts things
using very small amounts of memory compared to the number of objects
it is counting.

For a full description of the algorithm, see the paper HyperLogLog:
the analysis of a near-optimal cardinality estimation algorithm by
Flajolet, et. al. at http://algo.inria.fr/flajolet/Publications/FlFuGaMe07.pdf

For documentation see http://godoc.org/github.com/eclesh/hyperloglog

Quick start
===========

	$ go get github.com/eclesh/hyperloglog
	$ cd $GOPATH/src/github.com/eclesh/hyperloglog
	$ go test -test.v
	$ go test -bench=.

License
=======

hyperloglog is licensed under the MIT license.
