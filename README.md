## Point Pattern Analysis in PySAL

Statistical analysis of planar point patterns

**REORG IN PROGRESS**

This is work in progress towards [PEP 13](https://github.com/pysal/pysal/wiki/PEP-13:-Refactor-PySAL-Using-Submodules)


### History

#### 2016-12-23

	mkdir pysal_reorg
	cd pysal_reorg
	git clone git@github.com:sjsrey/pysal.git
	cp -R pysal pysal-copy
	cp -R pysal-copy pysal-points
	cd pysal-points
	git fetch origin
	git branch -a
	git checkout -b points origin/points_contrib
	git filter-branch --subdirectory-filter pysal/contrib/points -- -- all
	git remote -v
	git remote add upstream git@github.com:cgiscourses/pysal-points.git
	git push -u upstream points
	git branch -d master
	git checkout -b master
	git push upstream master


After these steps, on the Github settings for the repos change the default branch from `points` to `master`.


**Below here is from previous repos and will be updated**

### Introduction

This PySAL [contrib][] module is intended to support the statistical analysis of planar point patterns.

It currently works on cartesian coordinates. Users with data in geographic coordinates need to project their data prior to using this module.


### Examples

* [Basic point pattern structure](pointpattern.ipynb)
* [Centrography and Visualization](centrography.ipynb)
* [Marks](marks.ipynb)
* [Simulation of point processes](process.ipynb)
* [Distance based statistics](distance_statistics.ipynb)

### Installation

#### Requirements

- PySAL 1.11+
- Pandas 0.17.0+
- shapely
- descartes

### Why in Contrib and Not Core?

The initial implementation focuses on statistical functionality while using [pandas][] as an internal data structure. Future enhancements could either use core PySAL data structures, or swap in [GeoPandas][] for pandas. The former strategy would allow this to move into core, while the latter might postpone such a move until the team makes a decision on whether Pandas and/or GeoPandas were to be hard or soft dependencies in PySAL.


### TODO

- Enhance internal data structures


[contrib]: http://pysal.readthedocs.org/en/latest/library/contrib/index.html
[GeoPandas]: http://geopandas.org
[pandas]: http://pandas.pydata.org

