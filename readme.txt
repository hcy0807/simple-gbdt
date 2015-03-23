how to use in 64-bit linux

1. install tbb lib(very easy)
2. cd src;make (make sure tbb lib in your path)
3. cd bin;(start to work with gbrt)


ools update: 

asymmetric prior Latent Dirichlet Allocation (LDA) by c++ ——https://code.google.com/p/as-lda/

adaboost codes——http://code.google.com/p/simple-adaboost/ 

any problem please contact benwang177@gmail.com 

introduction: 

it is simple implement of gbdt(actually gradient boost regression tree)--compared to others, parallelization with tbb lib.

this project can be easily used in regression problem or point wise learning to rank problem(l2r), and can be good material to know about gbdt.

there are several more features:

1. support data sample configure

2. using tbb lib for parallelization(http://threadingbuildingblocks.org/)

3. empty features in l2r data will be skipped (to avoid unnecessary cost)

4. support two input format(l2r format and cvs format)

Usage 

-i input file

-f [cvs, l2r] input format , default 'l2r'

-c gbrt model config file , default './gbrt.conf' 

-t or -p act type(t for train,p for predict): 

-m model file , default './gbrt.model' 

-d max dimention(only for L2R format) 

Example 

train example: ./gbrt -t -i train_l2r.dat -d 415

predict example: ./gbrt -p -i test_l2r.dat -d 415 -m gbrt.model

Input Format

l2r: "-1 qid:1234 1:1 3:1 8:1"

csv: "1,3,-1" last column is label

configure example

max_tree_leafes=20

feature_subspace_size=40

use_opt_splitpoint=true

learn_rate=0.01

data_sample_ratio=0.4
