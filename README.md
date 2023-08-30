# SpCQL-Dataset-Setup
Method to transfer neo4j database files to your own device on windows platform.

## DataSet
SpCQL-Dataset is a Text-to-CQL dataset of CIKM 2022 paper "SpCQL: A Semantic Parsing Dataset for Converting Natural Language into Cypher". Their dataset is available in [github](https://github.com/Guoaibo/Text-to-CQL/blob/main/README.md?plain=1). The dataset can be downloaded [here](https://pan.baidu.com/s/1aqMZFMOOpiB1GWUo5-I7xQ?pwd=b6ix).

## Environment
Experiments is under [neo4j-community-4.4.12](https://we-yun.com/doc/neo4j/4.4.12/). 
**Attention: JDK 11 is required.**

**Step1:** Download neo4j-community-4.4.12 and unzip to your own path.

**Step2:** Add environment variables.
```bash
NEO4J_HOME=YOUR/PATH/neo4j-community-4.4.12
PATH=%NEO4J_HOME%\bin
```

**Step3:** Open cmd and run
```bash
neo4j console
```
**PS:** If failed, please check environment variables.

## Replacement
**Step1:** 

Download Dataset and unzip `graph-all02.db.zip`.

**Step2:** 

Delete files in `neo4j-community-4.4.12/data/databases/neo4j/`.

Copy files in `/graph-all02.db/` and paste them to `neo4j-community-4.4.12/data/databases/neo4j/`.

Delete dir `neo4j-community-4.4.12/data/trasactions/`.

**Step3:** 

Edit config file `neo4j-community-4.4.12/conf/neo4j.conf`. Set
```bash
# Enable this to be able to upgrade a store from an older version.
dbms.allow_upgrade=true
```
Remove `#` in front of `dbms.allow_upgrade=true`

**Step4:**

Restart neo4j service and wait merging.

## Final
[SpCQL.dump](https://pan.baidu.com/s/1xt7R18VIlqlXIxqMIlE2Rw?pwd=8ec4) is available by using this method.
```bash
neo4j-admin dump --database=neo4j --to=./SpCQL.dump
```
Take if need.

## Reference
```bash
@inproceedings{DBLP:conf/cikm/GuoLXT022,
	  author       = {Aibo Guo and
	                  Xinyi Li and
	                  Guanchen Xiao and
	                  Zhen Tan and
	                  Xiang Zhao},
	  editor       = {Mohammad Al Hasan and
	                  Li Xiong},
	  title        = {SpCQL: {A} Semantic Parsing Dataset for Converting Natural Language
	                  into Cypher},
	  booktitle    = {Proceedings of the 31st {ACM} International Conference on Information
	                  {\&} Knowledge Management, Atlanta, GA, USA, October 17-21, 2022},
	  pages        = {3973--3977},
	  publisher    = {{ACM}},
	  year         = {2022},
	  url          = {https://doi.org/10.1145/3511808.3557703},
	  doi          = {10.1145/3511808.3557703},
	  timestamp    = {Tue, 21 Mar 2023 20:54:47 +0100},
	  biburl       = {https://dblp.org/rec/conf/cikm/GuoLXT022.bib},
	  bibsource    = {dblp computer science bibliography, https://dblp.org}
	}
```
