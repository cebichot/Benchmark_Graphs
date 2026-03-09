# Graph benchmark for partitioning

## Graph instances, sizes and origins

| graph | \|V\| | \|E\| | original source |
|------|------|------|--------------------------------|
| add20 | 2395 | 7462 | www.cise.ufl.edu/research/sparse/matrices/Hamm/add20.html |
| data | 2851 | 15093 | http://staffweb.cms.gre.ac.uk/~c.walshaw/partition/archive/data/data.graph |
| 3elt | 4720 | 13722 | ftp://riacs.edu/pub/grids/3elt.grid.gz |
| uk | 4824 | 6837 | http://staffweb.cms.gre.ac.uk/~c.walshaw/partition/archive/uk/uk.graph |
| add32 | 4960 | 9462 | www.cise.ufl.edu/research/sparse/matrices/Hamm/add32.html |
| bcsstk33 | 8738 | 291583 | www.cise.ufl.edu/research/sparse/matrices/HB/bcsstk33.html |
| whitaker3 | 9800 | 28989 | ftp://riacs.edu/pub/grids/whitaker3.grid.gz |
| crack | 10240 | 30380 | www2.cs.uni-paderborn.de/fachbereich/AG/monien/RESEARCH/PART/GRAPHS/FEM2.tar |
| wing_nodal | 10937 | 75488 | http://staffweb.cms.gre.ac.uk/~c.walshaw/partition/archive/wing_nodal/wing_nodal.graph |
| fe_4elt2 | 11143 | 32818 | wotug.org/parallel/libraries/communication/scotch/Graphs/fe_4elt2.src.gz |
| vibrobox | 12328 | 165250 | www.cise.ufl.edu/research/sparse/matrices/Cote/vibrobox.html |
| bcsstk29 | 13992 | 302748 | www.cise.ufl.edu/research/sparse/matrices/HB/bcsstk29.html |
| 4elt | 15606 | 45878 | www.cise.ufl.edu/research/sparse/matrices/Pothen/barth5.html |
| fe_sphere | 16386 | 49152 | wotug.org/parallel/libraries/communication/scotch/Graphs/fe_sphere.src.gz |
| cti | 16840 | 48232 | http://staffweb.cms.gre.ac.uk/~c.walshaw/partition/archive/cti/cti.graph |
| memplus | 17758 | 54196 | www.cise.ufl.edu/research/sparse/matrices/Hamm/memplus.html |
| cs4 | 22499 | 43858 | http://staffweb.cms.gre.ac.uk/~c.walshaw/partition/archive/cs4/cs4.graph |
| bcsstk30 | 28924 | 1007284 | www.cise.ufl.edu/research/sparse/matrices/HB/bcsstk30.html |
| bcsstk31 | 35588 | 572914 | www.cise.ufl.edu/research/sparse/matrices/HB/bcsstk31.html |
| fe_pwt | 36519 | 144794 | wotug.org/parallel/libraries/communication/scotch/Graphs/fe_pwt.src.gz |
| bcsstk32 | 44609 | 985046 | www.cise.ufl.edu/research/sparse/matrices/HB/bcsstk32.html |
| fe_body | 45087 | 163734 | wotug.org/parallel/libraries/communication/scotch/Graphs/fe_body.src.gz |
| t60k | 60005 | 89440 | http://staffweb.cms.gre.ac.uk/~c.walshaw/partition/archive/t60k/t60k.graph |
| wing | 62032 | 121544 | http://staffweb.cms.gre.ac.uk/~c.walshaw/partition/archive/wing/wing.graph |
| brack2 | 62631 | 366559 | ftp://riacs.edu/pub/grids/brack2.grid.gz |
| finan512 | 74752 | 261120 | www.cise.ufl.edu/research/sparse/matrices/Mulvey/finan512.html |
| fe_tooth | 78136 | 452591 | wotug.org/parallel/libraries/communication/scotch/Graphs/fe_tooth.src.gz |
| fe_rotor | 99617 | 662431 | wotug.org/parallel/libraries/communication/scotch/Graphs/fe_rotor.src.gz |
| 598a | 110971 | 741934 | ftp://ftp.cs.umn.edu/users/kumar/Graphs/598a.graph.gz |
| fe_ocean | 143437 | 409593 | wotug.org/parallel/libraries/communication/scotch/Graphs/fe_ocean.src.gz |
| 144 | 144649 | 1074393 | ftp://ftp.cs.umn.edu/users/kumar/Graphs/144.graph.gz |
| wave | 156317 | 1059331 | ftp://riacs.edu/pub/grids/wave.grid.gz |
| m14b | 214765 | 1679018 | ftp://ftp.cs.umn.edu/users/kumar/Graphs/m14b.graph.gz |
| auto | 448695 | 3314611 | ftp://ftp.cs.umn.edu/users/kumar/Graphs/auto.graph.gz |


## Graph file format

Each of these undirected graphs is stored in a text file with the following format, where vertices are numbered from (1) to (|V|) :

```
|V| |E|
v_i v_j
v_k ...
...
```

* The first line contains two integers:
  (|V|), the number of vertices in the graph, and (|E|), the number of edges.

* Each subsequent line corresponds to one vertex (in the order (1, 2, ..., |V|)) and lists its adjacent vertices.
  
* For example, the first adjacency line corresponds to vertex (1).
If this line contains (v_i) and (v_j), then vertex (1) has two neighbors: (v_i) and (v_j).

