Summary
-------

This is the README_EN.txt file for doing rman backup and recovery experiment on
oracle database server.There are two oracle database server,one is source
oracle database,it's production environment;another is target oracle
database,and it has only insalled linux and oracle database software,we need
to restore and recover a oracle database with source oracle's rman
backupsets.

Entire rman restore process include five shell scripts and introduction per
script:
---------------------------------------------------------------------------

-- 1. ssh_mutual_trust_linux_for_source.sh          ==> ( set target host's ssh mutual trust function on source host )

-- 2. ssh_mutual_trust_linux_for_target.sh          ==> ( set source host's ssh mutual trust function on target host )

-- 3. collect_info_from_source_oracle.sh            ==> ( collect some information from source host )

-- 4. scp_log_file_to_target.sh                     ==> ( scp file "/tmp/source_oracle_dbinfo.log" to target host ) 

-- 5. rman_restore_and_recover_to_target_oracle.sh  ==> ( with rman restore and recover oracle from target host )

Execute shell script process
----------------------------

All of shell scripts is executed on oracle user.

First,set ssh mutual trust function between source oracle database and target
oracle database,and execute script "ssh_mutual_trust_linux_for_source.sh" in
source host and execute script "ssh_mutual_trust_linux_for_target.sh" in target
host.

Second,execute script "collect_info_from_source_oracle.sh" for collect some information
on source host,and then execute script "scp_log_file_to_target.sh",scp file 
"/tmp/source_oracle_dbinfo.log" to dir "/tmp" of target host.

Finally,execute script "rman_restore_and_recover_to_target_oracle.sh" on target
host for restoreing and recovering oracle database.
