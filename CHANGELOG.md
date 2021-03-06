# Changelog
All notable changes to this project will be documented in this file.

## 2.33.0 - 2020-06-18
### Added
- Added integration with TOTVS Identity using connector token.
- Added option to edit Mysql database properties.
### Improvements
- 2C validates if the schema exists and if there is any difference with Carol's staging schema before trying to send the data to Carol.
- Improvements the logs
### Fixed
- Fixed when the process to generate the payloads finish with error the CDS clear data is called again.
- Fixed when sent the payload to Carol with error and the 2C considers the payload sent with success.
- Fixed when 2C tries to load a file from disk but the directory has hidden files.

## 2.32.6 - 2020-06-04
### Fixed
- Fix sync via resync with a case sensitive database.

## 2.32.5 - 2020-04-30
### Fixed
- When the option CDS clear data is selected, 2C clear CDS data every minute.
### Improvements
- When the option CDS clear data is selected, 2C only sends data to Carol when the clear task is done.
### Added
- Add the option to schedule the first Full Load immediately.

## 2.32.4 - 2020-04-08
### Fixed
- Fix shows the original field name (Case Sensitive) when loading the entity.
### Removed
- Remove option to send data via CDS, with Carol 3.7 all data is CDS.
### Added
- Add option to delete all CDS before syncing Full Load.
- Add note that shows when the next sync is going to happen.
- Add oracleUseOwnerAsQueueSchema option in app.config.

## 2.32.3 - 2020-03-12
### Fixed
- Fix sending data to Carol when the database is Protheus and the table has group code.
- Fix SqlServer delete trigger when the crosswalk has date field.

## 2.32.2 - 2020-03-06
### Fixed
- Fix stuck threads when 2C is generating and sending payloads at the same time.

## 2.32.1 - 2020-02-21
### Fixed
- Fix the sync by timestamp on Oracle database

## 2.32.0-RC - 2020-02-12
### Added
- Option to sync by value considering the current date/time instead of the maximum date/time for the field's value.
### Improvements
- Performance - When enabled multiple entities the data will be generated and sent in parallel to Carol.

## 2.31.8 - 2020-02-11
### Fixed
- Fix the integration with Carol when the table has column name with special chars.

## 2.31.7 - 2020-02-06
### Fixed
- Fix 2C update schema on staging area.
- Fix Openedge query to get pending queue.
### Changed
- Enable multiple tables by Realtime flow and not via CDS flow.

## 2.31.5 - 2020-01-24
### Fixed
- Fix Openedge column name to status.

## 2.31.3 - 2020-01-16
### Fixed
- Fix start application when 2c don't have all info about the connection with Carol.

## 2.31.2 - 2020-01-15
### Fixed
- Fix entities values on heartbeat info.
### Added
- Added tables values with sync strategy to heartbeat data.

## 2.31.1 - 2020-01-07
### Fixed
- Fix triggers when the entity was configured with a condition SQL using `In clause` with `Subselect`.

## 2.31.0 - 2019-12-30
### Added
- Added on 2c the information about the total of Bytes sent to Carol.
### Changed
- Show limited results when search entities (max. 100 entities).
### Fixed
- Fix Chart data when had multiple databases configured.
### Improvements
- Performance - faster to show, enable and disable an entity.

## 2.30.8 - 2019-11-22
### Fixed
- Fix Openedge transaction isolation settings.

## 2.30.7 - 2019-11-20
### Added
- Added synchronization strategy info to heartbeat data.

### Fixed
- Fix Protheus table name regular expression.

## 2.30.6 - 2019-11-18
### Fixed
- Fix Oracle sync by timestamp when using OpenEdge schema holder.

## 2.30.5 - 2019-11-13
### Added
- Added information about last successful database access to heartbeats.

### Fixed
- Fixed Oracle delete triggers.
- Fixed select all button on UI.

##  2.30.4 - 2019-11-07
### Added
- 2c now reads the default definitions of anonymization of schema fields in Carol.

##  2.30.3 - 2019-11-07
### Fixed
- On Oracle databases, 2c is not listing string fields on Sync by Value.

### Changed
- Changed labels regarding organization and tenants on login screen.
- Schema definition now uses Carol API v2.

### Removed
- Removed Informix database support.

## 2.30.2 - 2019-11-01
### Fixed
- Fixed enabling multiple tables at once.

## 2.30.1 - 2019-10-30
### Added
- Allow to initialize the anonymization on 2C to a list of fields.
- Add type visualization to valued fields for sync by value.
- Add last values data from Sync by Value to heartbeat.

## 2.30.0 - 2019-10-24
### Added
- Option to ignore queue table for read-only databases.

## 2.29.7 - 2019-10-23
### Fixed
- Fix NPE when getting token from Carol.

## 2.29.6 - 2019-10-22
### Fixed
- Fix Carol's URL when using organization.
- Resend all data in Sync by Value, reset previous stored values to the original.

### Added
- Added support for organization to Carol test connection.
- Option to reset all anonymizations.

## 2.29.5 - 2019-10-15
### Fixed
- Disable table if no crosswalk available.
- Wrong trigger creation if `exists` keyword used in conditional sql on SQL Server databases.

## 2.29.4 - 2019-10-09
### Fixed
- Wrong json format for nested document from MongoDB on sync by value.
- Initial integer number on sync by value was been ignored if initial date was null.

### Changed
- The numeric data type in Postgresql with no defined decimal size is now treated as a double value.
- [UI] Enabling a lot of tables at same time is now did in batches.

## 2.29.3 - 2019-10-08
### Changed
- Sync by field value now supports dates in varchar fields.
- Initial load and sync by field value now uses cursor fetching on postgresql databases to avoid out of memory.

## 2.29.2 - 2019-10-03
### Fixed
- 2c wasn't handle correctly tables on Oracle using OpenEdge schema holder patterns without df file.

## 2.29.1 - 2019-10-02
### Added
- Support for MongoDB replicas set.

### Fixed
- Conditional test on Oracle databases with OpenEdge schema holder.

## 2.29.0 - 2019-10-01
### Added
- Support for tenant organizations.

### Changed
- Sync by timestamp is now Sync by field value. It handle fields with timestamp and integer data.

## 2.28.3 - 2019-10-01
### Fixed
- Fix anonymization on sync by timestamp using mongodb.

### Changed
- Change connection validation on MongoDB connection.

## 2.28.2 - 2019-09-25
### Fixed
- Fixed primary key validation.
- In trigger validation, 2c was ignoring conditional sql.

## 2.28.1 - 2019-09-24
### Fixed
- Directory synchrozation don't work if directory name contais whitespaces.
- Avoid enabling table synchronization without primary key definition.

### Changed
- Field anonymization list is now sorted.

## 2.28.0 - 2019-09-20
### Added
- New button to resend all data without needing to disable and enable the synchronization.
- New synchronization mode: Sync by Full Load.

## 2.27.8 - 2019-09-17
### Changed
- Handle new Carol's response codes for schema divergences.

## 2.27.7 - 2019-09-16
### Fixed
- Conditional criteria testing on SQL Server with nonstandard schemas is not working.
- Handle null data comming from Carol during resync.

### Changed
- Set the transaction isolation before initializing the connection pool.

## 2.27.6 - 2019-09-10
### Fixed
- Http User-Agent

### Reverted
- Pk modification detection on triggers on SQL Server Databases

## 2.27.5 - 2019-09-06
### Fixed
- Revert MS Sql Server driver to 7.2.2.
- MS Sql Server mishandling triggers when not prefixed table name.

### Added
- Button to remove fields from anonynimization.
- new config option `generateScriptsOnly` to avoid applying DDL to database.

### Changed
- Changed Http User-Agent from 2c.

## 2.27.4 - 2019-08-29
### Fixed
- Fix Oracle connection creation without df file.

## 2.27.3 - 2019-08-27
### Fixed
- Fix directory connection creation.
- Fix queue table fieldname on OpenEdge databases.
- Fix SQL Server fieldname case.

## 2.27.2 - 2019-08-21
### Fixed
- Fix date format on complex documents on MongoDB.

### Added
- Read primary key definition from df file on Oracle OpenEdge Schema Holder.

## 2.27.1 - 2019-08-20
### Fixed
- Fix Protheus table names regex.

### Added
- Added resync differences report.

## 2.27.0 - 2019-07-16
### Added
- Support for MongoDB.
- Support for OpenEdge Oracle schema holder.
- Added pending count to heartbeat.

### Changed
- Simplified database version number on heartbeats.

## 2.26.3 - 2019-08-13
### Fixed
- Reduced memory usage on sync by timestamp

## 2.26.2 - 2019-08-02
### Fixed
- On MySQL databases, 2c was unable to read the last timestamp from returned payload.

### Changed
- By enabling timestamp synchronization, 2c will no longer trigger an initial load.

## 2.26.1 - 2019-07-16
### Added
- Available space on payload directory to heartbeat info.

### Changed
- Changed Carol's endpoint to send data to *Carol's Data Storage*.

## 2.26.0 - 2019-07-04
### Added
- 2c now supports primary key's values change. It'll send a delete and a insert operation to Carol.
- 2c now reads, on-the-fly, the payload size limit from Carol.
- Support for Carol's Data Storage. Just check the option before enable a table synchronization.

### Changed
- If there are already entities in Carol, the option to show only the entities in the staging area will be checked by default.

## 2.25.6 - 2019-06-11
### Fixed
- On Oracle databases, delete payload created by triggers are been lowercase.

## 2.25.5 - 2019-06-07
### Reverted
- On Oracle databases, delete payload from resync was sending table names uppercase.

## 2.25.4 - 2019-05-31
### Fixed
- On Oracle databases, delete payload from resync was sending table names uppercase.
- If a view on Protheus databases didn't contain soft deletion field, 2c wasn't able to synchronized it.

### Changed
- Updated embedded Derby database to 10.15.1.3.

## 2.25.3 - 2019-05-27
### Fixed
- 2c is not handling apostrophe (') in pk values.
- Resync on OpenEdge databases is consuming 100% CPU.

## 2.25.2 - 2019-05-08
### Fixed
- Avoid starting concurrent initial loads of the same entity.
- Disabling a table on Oracle is getting error when using user schema.

## 2.25.1 - 2019-05-06
### Fixed
- When using user schema to store the triggers on Oracle, 2c wasn't able to check them.

### Changed
- Change the default max image size to 800 pixels.

## 2.25.0 - 2019-04-30
### Added
- Multiple table initial loader manager.
- Cron expression to schedule initial load process.

### Fixed
- Reading table metadata is leaking connections.

## 2.25.0-beta - 2019-04-18
### Added
- Added anonynimization feature to 2c.

### Changed
- Only create queue table when triggers are enabled on 2c.
- Heartbeat statistics are now sent every 15 minutes to Carol.

## 2.24.3 - 1019-04-16
### Fixed
- When enabling a table with sync by timestamp with null fields, 2c is getting a NPE.
- Refreshing pending count with no enabled tables is getting error on 2c.

## 2.24.2 - 2019-04-09
### Fixed
- Resynchronization fix of the Openedge database with table names that use the hyphen character in the name.

## 2.24.1 - 2019-04-05
### Fixed
- Fix Oracle queue query when using Protheus database with company codes enabled.

## 2.24.0 - 2019-04-03
### Added
- In timestamp synchronization, you can now choose more than one date field for monitoring.

## 2.23.2 - 2019-04-01
### Fixed
- Oracle queue table was not being consumed by 2c.

### Added
- Suport for Oracle's timestamp with timezone datatype.

## 2.23.1 - 2019-03-27
### Added
- Suport for Oracle's timestamp with local timezone datatype.

## 2.23.0 - 2019-03-21
### Added
- Mask filter for directory synchronization.
- SQL filter for directory synchronization. 2c can now query a database connection for filenames to be sent to Carol.

## 2.22.0 - 2019-03-08
### Added
- Support for Azure Active Directory authentication to SQL Server databases.
- Current queue size visualization on databases screen.

### Changed
- Deselect entities after a bulk enable/disable to avoid more than one start.

### Fixed
- 2c was not able to identify which entities are already under Carol's staging when using the protheus company codes.

## 2.21.1 - 2019-02-26
### Fixed
- Fixed a bug with protheus company codes on oracle databases.

## 2.21.0 - 2019-02-25
### Added
- Support for directory synchronizaton.

## 2.20.2 - 2019-02-19
### Fixed
- Fixed a bug who prevents 2c has more than one connection to the same Carol's connector.

## 2.20.1 - 2019-02-12
### Changed
- Updated MySQL driver due timezone problems.

## 2.20.0 - 2019-02-08
### Added
- Support for TOTVS Protheus company codes.
- Support for TOTVS Protheus soft delete on PostgreSQL databases.

### Changed
- Improved notification messages.
- Update Apache Commons HTTP dependency.
- Update MS SQLServer driver dependency.

### Fixed
- Bug on database menu UI when there are more databases syncronizations.
- When change records with binary datatypes, 2c wasn't sending new binary data in some databases.

### BREAKING CHANGES
- **Updated java version to 11.0.2. Need to update JDK folder.**

## 2.19.4 - 2019-02-01
### Fixed
- Sometimes reserved fields on Oracle Protheus databases get wrong data types.

## 2.19.3 - 2019-01-25
### Fixed
- Sync by timestamp is not working on Progress OpenEdge databases.
- Fix error on reading OpenEdge records with values exceeding its max length.

### Changed
- Update OpenEdge driver dependecy to 5.1.4.

## 2.19.2 - 2019-01-24
### Added
- Option to log payloads sent to carol. Just set enablePayloadLogging: true in app.config.yml

## 2.19.1 - 2019-01-18
### Fixed
- Deleting a database connection is not working.

### Added
- If connector was deleted, 2c will disable the table synchronization and notify tenante's admins.
- 2c needs an utility to validate Carol's connection.
- Jaxb libraries to Java 11 compatibility.

### Changed
- Updated java version to 8.0.202.
- Remove unnecessary log message when binary field is not an image.

## 2.19.0 - 2019-01-11
### Added
- 2c now notifies the tenant admins by e-mail when a table synchronization is being disabled by incompatible schema changes.
- Support for image type to MySQL, PostgreSql and Informix databases.

### Fixed
- Wrong date format on MySql initial load.
- Delete table's records on Carol was not working with Informix databases.

### Changed
- Improved log message when 2c is unable to connect to a database.
- Default log configuration to do file rotation.

## 2.18.8 - 2018-12-07
### Fixed
- Wrong date format on Oracle changed records.

## 2.18.7 - 2018-12-05
### Removed
- Payload directory statistics was removed because could lead to out of memory situations.

## 2.18.6 - 2018-12-03
### Fixed
- Poor performance accessing payload directory when there are too many files to send.

## 2.18.5 - 2018-11-27
### Fixed
- Add support for Oracle BLOB datatype
### Changed
- Increased number of crosswalks sent to Carol in delete operations.

## 2.18.4 - 2018-11-22
### Fixed
- NPE on timestamp datatype in oracle databases, when data is absent.
- 2C is trying create triggers on Views.

## 2.18.3 - 2018-11-21
### Fixed
- 2c failing on timestamp datatype in oracle databases.
### Changed
- Informix and Postgres databases now use payload directory to send data to Carol.

## 2.18.2 - 2018-11-19
### Fixed
- When the number of changed tables exceeds the size of the pool, database connection timeout may occur.

## 2.18.1 - Unreleased
### Added
- Parameter to use the user login as owner of the table and the triggers in oracle bases.
### Changed
- Carol's endpoint to delete staging records.

## 2.18.0 - 2018-11-09
### Added
- 2c now send health status to Carol.
### Changed
- Max number of Carol connectors increased to 100.
- Connector's label is now show with it's id.
### Fixed
- Image resizing was not working when using payload folder.
- If Carol is down, 2c becomes unstable.
- Fix Oracle field case names.

## 2.17.0 - 2018-10-30
### Added
- Payload files are now splitted if they are bigger than 8Mb.
- 2c on Oracle databases now support images payloads.
- Oracle Clob data type are now supported. 
- Oracle and SQL Server databases now use payload directory to send data to Carol.
- Number of tables found now is displayed in the entities configuration screen.
### Changed
- Updated oracle driver dependency to ojdbc8 18.3.
### Fixed
- Enter key now works on login screen.

## 2.16.0 - 2018-10-15
- 2c now warns if it is not the latest version released.

## 2.16.0-beta - 2018-10-09
### Added
- 2c can now specify schema name in Oracle databases.
- Triggers are now created with the conditional filter configured on table activation.

## 2.15.3 - 2018-10-01
### Fixed
- Date format on internal derby database.
### Changed
- MySQL databases use cursor queries to avoid memory overflow.
- MySQL queries now have a query timeout. Default: 1 hour.

## 2.15.2 - 2018-09-24
### Changed
- MySQL databases now use payload directory to send data to Carol.

## 2.15.1 - 2018-09-18
### Fixed
- Oracle trigger names was exceeding 30 characters.

## 2.15.0 - 2018-09-17
### Changed
- Initial load files for OpenEdge database are now gzipped.

## 2.15.0-RC2 - 2018-09-11
### Changed
- Initial load on OpenEdge databases will use a temporary directory instead the queue table.

## 2.15.0-RC - 2018-09-05
### Added
- Now intial timestamp can be setted.
### Fixed
- Bug on schema change.
- Openedge databases was getting wrong schema name.

## 2.15.0-beta2 - 2018-08-29
### Added
- Entities are now sorted to priorize lookup tables.

## 2.15.0-beta - 2018-08-24
### Added
- Support for image reducing before send them to Carol.
### Fixed
- Removed unnecessary record count on MySQL databases for initial load.
- Wrong data format on sync by timestamp.

## 2.15.0-alpha - 2018-08-16
### Added
- Support for OpenEdge databases.
- Option to select more then one table to enable/disable.
- Option to view only existing tables in Carol.

## 2.14.0 - 2018-08-10
### Fixed
- Wrong data type on SQL Server float type
### Changed
- Updated SQL Server driver depency to 7.0.0

## 2.14.0-Beta3 - 2018-08-09
### Added
- 2c config file validation.
### Fixed
- Fix schema name on sync by timestamp.
- Fix MySQL trigger for delete.
### Changed
- Change MySQL inital load to avoid select count.

## 2.14.0-Beta2 - 2018-08-01
### Fixed
- Column name case divergence on Postgresql databases.
- New fields in SQL Server databases were being ignored.
### BREAKING CHANGES
- Binary data is now sent as base64 type.

## 2.14.0-Beta - 2018-07-27
### Added
- Two new synchronization modes: Sync by timestamp field and Sync by recurrent resynchronization.
### Removed
- Removed unnecessary entity cache.

## 2.13.3 - 2018-07-24
### Changed
- Updated oracle driver dependency to ojdbc8 12.2.0.1.

## 2.13.2 - 2018-07-10
### Fixed
- Unnecessary insert in queue table when inclusions occur with soft delete in protheus databases.

## 2.13.1 - 2018-07-03
### Fixed
- Fixed detection of Oracle numeric data type.
- Reduced max batch size to 8Mb.
- Fixed Postgresql resync criteria filter.
- Fixed field cache retriever for uppercase databases.
- Fixed authentication title typo.

## 2.13.0 - 2018-06-26
### Added
- Now 2c have a resync feature. It compares local data with remote data and sends the difference. Need to set `enableReSync` option on `app.config.yml` file.
- Added an embedded derby database on 2c data folder.
### Changed
- Login for 2c is now optional. To enable, just set `enableLogin` option on `app.config.yml` file.
### Fixed
- Reduced payload size by avoiding sending null data.

## 2.12.3 - 2018-06-15
### Fixed
- Fix next batch query on Oracle databases.

## 2.12.2 - 2018-05-25
### Changed
- Disabled extra login for 2c.

## 2.12.1 - 2018-05-16
### Changed
- Automatic start is now default for windows service.
- Increased log messages related to record retrieval.

### Fixed
- NullPointerException when no schema is informed for MSQLServer.
- When a batch is larger than 10Mb and the table definition has not yet been synchronized, some parts of this batch are not processed.

## 2.12.0 - 2018-05-11
### Added
- Increase max batch size to 10mb.
- It is now necessary to log in with the same user used to access Carol in order to use the 2c interface.

## 2.11.1 - 2018-05-09
### Fixed
- Bug fix that occurs when all pk records fetched from queue are already deleted from the original data table.

## 2.11.0 - 2018-04-26
### Added
- Allow to edit the database connection changing: host, username, password, etc.

### Fixed
- Charset problem during payload compaction on windows platform.
- Reduced jar size by removing unnecessary files during the build phase.

## 2.10.2 - 2018-04-23
### Fixed
- Increase database timeout.
- Get pending count poor performance.
- MySQL was inserting duplicate records on queue.
- Access control on initial load when MySQL and Postgres databases.

## 2.10.1 - 2018-04-17
### Fixed
- Fix data order on Postgresql.
- Fix unnecessary queue reset when no data was found.
- Fix bug that make some entities to pause.
- Fix Yaml concurrent parse problem.

## 2.10.0 - 2018-04-02
### Added
- GZip compaction to payload sent to Carol.
- Informix database compatibility.

### Fixed
- Performance improvement on pending records search. 

## 2.9.2 - 2018-03-27
### Fixed
- Optimized oracle get pending count query.

## 2.9.1 - 2018-03-26
### Added
- Added mechanism to control the order of sending data.

## 2.9.0 - 2018-03-20
### Added
- Image data is now sent to Carol on Base64 encoding.
- Support for Totvs Protheus soft delete on SQL Server and Oracle databases.

## 2.8.8 - 2018-03-16
### Fixed
- Can't do initial load on SQL Server 2008, sql syntax error.

## 2.8.7 - 2018-03-13
### Fixed
- 2c queue table should not be listed at entity selection.
- MySQL error on databases with timestamp zero valued.
- Table definition cache refactoring. When more than one thread access a database conection, it mixes fields definition.

### Added
- Database access control to avoid to many record locks.

## 2.8.6 - 2018-03-08
### Fixed
- Queue query not respects batch size on MySQL and SQLServer databases.

## 2.8.5 - 2018-03-06
### Added
- New application parameter `ignoreTriggers`, when 2c will only do the initial load and read the queue table. The integrated application will feed the carol_3c_queue manually in this case.

## 2.8.4 - 2018-03-02
### Added
- MySQL Database support.

### Fixed
- Fix ISO-8601 date format on delete requests.
- Oracle wrong date format saved in 3c queue.
- SQL Server wrong date format saved in 3c queue.
- Avoid to more than one thread getting the same batch.

## 2.8.3 - 2018-02-27
### Fixed
- Oracle trigger creation bug when trigger name is bigger than 30 caracters.

## 2.8.2 - 2018-02-22
### Added
- Integration triggers validation.
- Queue table validation.

### Fixed
- Oracle trigger creation bug with pk with date fields.

## 2.8.1 - 2018-02-20
### Fixed
- Fix PostgreSQL bug.

## 2.8.0 - 2018-02-20
### Added
- Support deletion operation from DB side.
- Add a flag to control when 2C is still running the initial load.

### Fixed
- Fix PostgreSQL bug.

### Security
- Update dropwizard version to address security fixes.

### BREAKING CHANGES
- New trigger for deletion.
- New carol_3c_queue field op_type.

## 2.7.4 - 2018-02-19
### Added
- Allow to configure 2C as a service on Windows.

### Fixed
- Fix PostgreSQL bug.

## 2.7.3 - 2018-01-31
### Fixed
- Queue reset divided in small batches to avoid database lock.

## 2.7.2 - 2018-01-31
### Fixed
- Fix queue status bug.

## 2.7.1 - 2018-01-24
### Fixed
- Fix Carol API parameter name.

## 2.7.0 - 2018-01-24
### Fixed
- Initial load divided in small batches to avoid database lock.
- Change Carol API parameter `applicationId` to `connectorId` name.

The format is based on [Keep a Changelog](http://keepachangelog.com/en/1.0.0/) and this project adheres to [Semantic Versioning](http://semver.org/spec/v2.0.0.html).
