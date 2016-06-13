# Project overview & goal
This is a project when I was taking CS143 Database Systems at UCLA with professor Dr. Junghoo. The goal is to implement B+tree indexes and modify its SQL engine to make Bruinbase use a B+tree for query processing.

# Base version of Bruinbase without B+ Tree implemented
Build the Bruinbase executable by running "make" in the 'bruinbaseNoB+Tree' directory:
```
$ cd ~/bruinbaseNoB+Tree
$ make
```
Run "bruinbase" to enter its command line interface:
```
$ ./bruinbase
Bruinbase>
```
Once you are inside Bruinbase, you can interact with it by issuing SELECT, LOAD, and QUIT commands. All tables in Bruinbase have two columns, key (integer) and value (string of length up to 99). For example, the Movie table that has been preloaded to Bruinbase can be queried as follows:
```
Bruinbase> select * from movie where key > 1000 and key < 1010
1008 'Death Machine'
1002 'Deadly Voyage'
1004 'Dear God'
1003 'Deal of a Lifetime'
1009 'Death to Smoochy'
  -- 0.162 seconds to run the select command. Read 403 pages

Bruinbase> select count(*) from movie
3616
  -- 0.160 seconds to run the select command. Read 403 pages

Bruinbase> select * from movie where key=3421
3421 'Remember the Titans'
  -- 0.162 seconds to run the select command. Read 403 pages

Bruinbase> select * from movie where value='Die Another Day'
1074 'Die Another Day'
  -- 0.162 seconds to run the select command. Read 403 pages

Bruinbase> 
```

Once you are done, you can issue the QUIT command to exit.
```
Bruinbase> quit
```


# B+ Tree implementation Specification
'BruinbaseProjectSpecification.pdf' inlcudes Bruinbase Architecture, B+tree implementaion, and SqlEngine modification.

# Test Bruinbase with B+tree implemented.
Similar with base version Bruinbase, we need to run 'make' to generate executable 'bruinbase'.
At the same folder, shell executable/script 'test.sh' is provided. Run it with below command:
```
./test.sh
```