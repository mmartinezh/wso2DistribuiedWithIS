# wso2DistribuiedWithIS
All instances running in the same machine. For that I has changed the ports of all components because all of them are shared machine.

Key Manager offset ->0  port -> 9443
Gateway offset ->1 port -> 9444
Publisher offset ->2 port -> 9445
Store offset ->3 port -> 9446
Traffic Manager	offset ->4	port -> 9447
Identity Sewrver offset ->5 port -> 9448

We need to create five BBDDD as following (user apiuser pwd apimanager):

mysql> create database apimgtdb;
mysql> use apimgtdb;
mysql> source <APIM_HOME>/dbscripts/apimgt/mysql.sql;
mysql> grant all on apimgtdb.* TO username@localhost identified by "password";
 
mysql> create database userdb;
mysql> use userdb;
mysql> source <APIM_HOME>/dbscripts/mysql.sql;
mysql> grant all on userdb.* TO username@localhost identified by "password";
 
mysql> create database regdb;
mysql> use regdb;
mysql> source <APIM_HOME>/dbscripts/mysql.sql;
mysql> grant all on regdb.* TO username@localhost identified by "password";
  
mysql> create database statdb;
mysql> grant all on statdb.* TO username@localhost identified by "password";
  
mysql> create database mbstoredb;
mysql> use mbstoredb;
mysql> source <APIM_HOME>/dbscripts/mb-store/mysql-mb.sql;
mysql> grant all on mbstoredb.* TO username@localhost identified by "password";