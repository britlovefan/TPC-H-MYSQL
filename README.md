# TPC-H-MYSQL (My steps)
1. Makefile change the parameter 
	cc = gcc
	DATABASE = SQLSERVER
	MACHINE = LINUX
	WORKLOAD = TPCH
	commands: make -f makefile

2. Runnning Dbgen to generate tables
	DBGEN is the utility that builds the data needed to load TPC-H. Typically, run it by typing(navigate to the dbgen/)
        ./dbgen –v –s 0.1 (0.1 Gb?)
        first two steps under the murphy machine of Northwesterh in LINUX 

3. Then scp the file in remote to local to use mysql ( Have tried to do it in ssh murphy but I don't have sql root permission) 
	   scp -r qwc695@murphy.wot.eecs.northwestern.edu:~/tpch_2_17_0 /cygdrive/c/Users/Christina

4. Once TPC-H is started, create a database and tpch account

5. Load the data in step 2 to tables:(experience error 1290, solve by moving the tbl to the legal position)
load data infile 'C:/ProgramData/MySQL/MySQL Server 5.7/Uploads/part.tbl' into table part fields terminated by "|" lines terminated by "\r\n";

6. Checked that the data have been corretly loaded: SHOW TABLE STATUS FROM tpch\G

7. Test.. to be implemented
	   
