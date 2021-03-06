---
title: "4.1.0"
date: 2019-03-13T18:28:08-07:00
draft: false
weight: -4010
tags: ['skipIndexing']
---

### Hue v4.1.0, released October 4th 2017

Hue, http://gethue.com, is an open source Analytic Workbench.

Its main features:

   * Editors for SQL querying (Hive, Impala, MySQL, Oracle, PostGreSQL, SparkSQL, Solr SQL, Phoenix ...) or jon submission: Spark, MapReduce, Pig...
   * Dashboards to dynamically interact and visualize data with Solr or SQL
   * Scheduler of jobs and workflows
   * Browsers for Jobs, Metadata (Tables, Indexes, Sentry permissions) and files (HDFS, S3, ADLS)

Read the complete list of improvements on [Hue 4.1 is out!
](http://gethue.com/hue-4-1-is-out/).


Summary
-------
The focus of this release was to keep making progress on the modernization and simplification of the Hue [4.0 UI](http://gethue.com/hue-4-and-its-new-interface-is-out/). The SQL editor is smarter and the ground for better visualizations was prepared.

Quality release

* Continued effort of Hue 4 unified interface
* 900+ commits
* SQL improvements

Stability

* Risk alert fix suggestions

Security

* Kerberos Mutual Auth issue fixed


Notable Changes
---------------

SQL

* Impala stability investigations
* SQL Parser update 100% of Impala grammar, 90% Hive.
* Links available in record explorer
* Variables can now have default values


Query optimization recommendations

* Risk alerts and popular values improvements: suggestions on how to fix the alerts
* Auto upload of DDL
* Speed, more obvious, top right


Universal Search

* Top search UX
* Simplification, follow-up on Search and Tagging
* Listing of Hue documents and Table data via Navigator

Sentry HA

* Support for out of the box support of Apache Sentry HA
* Sentry is used in:
   ** Sentry / Security App (SQL, Solr)
   ** Applying Table privileges in Navigator searches and NavOpt popular values
   ** Future showing of DROP/CREATE actions availability in UI

Mutual Authentication

* Kerberos related HUE-7127
* When calls from different Threads to services on the same hosts

Solr Collection Browser

* UI/UX revamp
* Integrated with Importer Wizard
* Preparing scalable Morphline indexer integration


Interface

* Home can be set as starred app
* Easier sharing directly via the Editor or Dashboard


Compatibility
-------------

Runs on CentOS versions 5 to 6, Red Hat Enterprise Linux (RHEL 5, 6, 7), and Ubuntu 12.04, 14.04 and 16.04.

Tested with CDH5. Specifically:

- Hadoop 2.6.0
- Hive 1.1
- Oozie 4.1
- HBase 1.2
- Pig 0.12
- Impala 2.5
- Solr 4.10
- Sqoop2 1.99.5
- Spark 1.6

These minimum versions should work (not tested):

- Hadoop 0.20 / 1.2.0 / 2.0.0
- Hive 0.12.0
- Oozie 3.2
- HBase 0.92
- Pig 0.8
- Impala 1.0
- Solr 3.6
- Sqoop2 1.99.3
- Spark 1.4

Supported Browsers:

Hue works with the two most recent versions of the following browsers. Make sure cookies and JavaScript are turned on for the browser.

* Chrome
* Firefox LTS
* Safari (not supported on Windows)
* Internet Explorer

Hue might work with Chrome 23, Firefox 23, IE8, Safari 6, or older browser version, but you might not be able to use all of the features.


Runs with Python 2.6.5+

Note: CentOS 5 and RHEL 5 requires EPEL python 2.6 package.


List of 900+ Commits
--------------------
* ec139cb Romain Rigaux 2017-10-02  HUE-7403 [core] Add 4.1 release notes
* 9c61919 Romain Rigaux 2017-10-02  HUE-7403 [core] Bump version to 4.1
* a66106a Enrico Berti  2017-10-04  HUE-7412 [editor] Fix indexes for chart limit array slice
* f279de7 Romain Rigaux 2017-10-03  HUE-7409 [search] ptypes should properly match any type
* 2a8488d Romain Rigaux 2017-10-03  HUE-7410 [core] Support opening mini job browser links directly on the correct section
* c71dc70 Enrico Berti  2017-10-04  HUE-7411 [frontend] Cannot share documents on touchscreen machines
* 2d83597 jdesjean  2017-10-03  HUE-7248 [adls] fix upload hdfs root
* 9c5a8a3 jdesjean  2017-10-02  HUE-7248 [adls] fix path autocomplete
* 9824796 Romain Rigaux 2017-10-03  HUE-7409 [search] The collection scheam config was being ignored
* 169d9dc Romain Rigaux 2017-10-03  HUE-7394 [core] Have dev mode on by default in development
* 9350a73 Romain Rigaux 2017-10-02  HUE-7400 [editor] Slightly bigger icon size for the dashboard icon in menu
* 9f4fb40 Romain Rigaux 2017-10-01  HUE-7400 [editor] Slightly bigger show log toggling icons
* 493edf9 jdesjean  2017-10-02  HUE-7248 [adls] fix upload + error on upload cancel
* de05751 Romain Rigaux 2017-10-01  HUE-7401 [indexes] Add multi index select via SHIFT binding to list index page
* f69548a Romain Rigaux 2017-10-01  HUE-7401 [editor] Port quick save to dashboard to use the SolrClient
* e05e9a9 Romain Rigaux 2017-10-01  HUE-7299 [solr] Use the proper LISTALIAS API in Solr 6+ to list aliases
* 59d32bc Romain Rigaux 2017-10-01  HUE-7396 [dashboard] Adding config properties to enable query builder and report
* 0500461 Romain Rigaux 2017-10-01  HUE-7398 [dashboard] Do not 500 on Dashboard opening when the first collection is not queryable
* 06968bd Romain Rigaux 2017-10-01  HUE-7397 [editor] Adding headers to clipboard copy data
* 89f5600 Romain Rigaux 2017-10-01  HUE-7397 [editor] Add number of rows in clipboard copy to warn on possible truncation
* 26e7937 Romain Rigaux 2017-10-01  HUE-7396 [dashboard] Re-organize available layouts
* 114f5e4 Romain Rigaux 2017-09-29  HUE-7395 [jb] Support opening-up a query job id query
* 50d7a15 Romain Rigaux 2017-09-29  HUE-7395 [editor] Add built-in link to the mini query job browser
* 9d7b2dd Romain Rigaux 2017-09-29  HUE-7395 [jb] Enable mini Job Browser for queries
* 7b86ddc Johan Ahlen 2017-10-03  HUE-6958 [autocomplete] Add autocomplete support for Hive SHOW VIEWS statements
* a9537de Johan Ahlen 2017-10-03  HUE-6958 [autocomplete] Add autocomplete support for Hive DROP TEMPORARY FUNCTION statements
* 0ca4918 Johan Ahlen 2017-10-03  HUE-7394 [frontend] Use the dev flag instead of debug_mode to prevent caching of resources
* 5c73b7f Enrico Berti  2017-10-03  HUE-7366 [oozie] Simplify top right menu buttons on schedule editor
* 02d1bfc Enrico Berti  2017-10-03  HUE-7367 [oozie] Simplify top right menu buttons on bundle editor
* bbf5f3d HUE-7248 [adls] Avoid cyclic dependency that prevents login
* dfa5960 HUE-7401 [indexes] Add multi index select via SHIFT binding to list index page
* cac837b HUE-7401 [editor] Port quick save to dashboard to use the SolrClient
* e1efc78 HUE-7400 [editor] Slightly bigger icon size for the dashboard icon in menu
* a160b03 HUE-7400 [editor] Slightly bigger show log toggling icons
* a406b08 HUE-7299 [solr] Use the proper LISTALIAS API in Solr 6+ to list aliases
* 621095e HUE-7396 [dashboard] Adding config properties to enable query builder and report
* 089d51a HUE-7398 [dashboard] Do not 500 on Dashboard opening when the first collection is not queryable
* 7d350b8 HUE-7397 [editor] Adding headers to clipboard copy data
* 05bacfb HUE-7397 [editor] Add number of rows in clipboard copy to warn on possible truncation
* 4d27272 HUE-7396 [dashboard] Re-organize available layouts
* 74f0fb7 HUE-7395 [jb] Support opening-up a query job id query
* 723372e HUE-7395 [editor] Add built-in link to the mini query job browser
* f150245 HUE-7395 [jb] Enable mini Job Browser for queries
* 0bfd995 HUE-7394 [core] Flag for a dev mode
* 67ed22b HUE-7388 [core] Include schedule job counts into the global job count widget
* 02d1008 HUE-6958 [autocomplete] Update autocomplete for Hive ALTER TABLE statements
* 276fb58 HUE-6958 [autocomplete] Update the Hive reserved keyword lists
* dc3314e HUE-7387 [search] New ptypes from Solr 7
* dabfc81 HUE-7385 [solr] Do not install Solr 7 examples with auto creation of fields
* 8ae9c82 HUE-7386 [search] Use proper types for some of the collection examples
* cd3576f HUE-7384 [importer] Add support for boolean values to Solr collections
* b0d75a1 HUE-7383 [core] Show Notebook as first non SQL editor when enabled
* 63cbe94 HUE-7248 [adls] Avoid core libs import dependencies on apps
* 6bbd4ee HUE-7392 [editor] Simplify top right menu buttons on the editor
* 1af4147 HUE-7369 [frontend] Migrate all remaining color variables in the LESS files to variables
* fb7313e HUE-7365 [oozie] Simplify top right menu buttons on workflow editor
* d9c38f7 HUE-7361 [assist] Dashboard assistant long field names shouldn't go to a new line
* 0d99766 HUE-7368 [frontend] Upgrade the Cloudera UI css to the latest version
* 1de2d83 HUE-7380 [dashboard] Adjust spacing of dimensions to allow drag and drop
* 64a626e HUE-7377 [frontend] Reset list of globally uploaded files at every new global upload
* fcf7613 HUE-7378 [fb] File Save As modal input  is not styled correctly
* a5dde90 HUE-7390 [autocomplete] Fall back to only autocomplete the active statement in case there are surrounding errors
* 22ffe21 HUE-6958 [autocomplete] Update autocomplete for Hive CREATE TABLE statements
* 9391d4f HUE-6958 [autocomplete] Add the DOUBLE PRECISION data type to Hive
* 28ab731 HUE-6958 [autocomplete] Add support for Hive ALTER DATABASE statements
* 5751ad6 HUE-7382 [frontend] Use the default SQL interpreter as the source type for global search result entries
* 5f8afb6 HUE-7381 [assist] Enable show in assist from the right assistant
* 0080370 HUE-7363 [assist] Allow drag and drop of fields into a dashboard
* bc9d4d6 HUE-7354 [frontend] Changed mini JB icon to fa-tasks
* 869311e HUE-7354 [frontend] Reverted the counter to orange, made it more round and changed icon for the mini JB
* df773a6 HUE-7379 [fb] Avoid usernames and groups to go to a new line
* 8c40a88 HUE-7248 [adls] fix test test__get_fs & test__get_fs_pair
* 4644117 HUE-7248 [adls] fix file upload over 30mb, remove logging auth token
* 22afba2 HUE-3277 [assist] Use the same viewmodel for HDFS, S3 and ADLS entries
* c013587 HUE-7314 [home] Use svg icons for new document and folder in home
* 26c0467 HUE-7296 [assist] Style the document context panel
* 51c269d HUE-7359 [assist] Enable show in assist for documents in the global search results
* ab8c313 HUE-7360 [assist] Unify dashboard assistant look & feel with the SQL assistant
* d7cc626 HUE-7376 [indexes] Number of fields and sample records are not always shown
* 3fc2938 HUE-7345 [indexer] Accept x01 char as field separator
* f8b7705 HUE-7374 [home] The expanded search box shouldn't go under the breadcrumbs
* 4496319 HUE-7333 [search] Simplifies menu text and add autogrow to query boxes
* c8db2e4 HUE-7355 [home] Landing on Hue home with a wrong folder ID doesn't give the option of navigating away
* 999b0c4 HUE-7354 [frontend] The JB status counter should be more prominent
* bd88417 HUE-7358 [frontend] Enable show in assist from the context popover for databases
* b7d1118 HUE-7049 [frontend] Generify the context popover and get rid of unused code
* 39809e6 HUE-7357 [frontend] Remove the old global search
* 20bf23d HUE-7356 [frontend] Fix js error when clearing search if a result is selected
* f51930d HUE-7351 [assist] Always show the filter input in the assist panels
* 802f872 HUE-7348 [search] Do not error when loading a non analytics saved dashboard
* 299ce5a HUE-7349 [jb] New jobs are not inserted without a page refresh on an empty page
* ea04739 HUE-7348 [indexer] Properly use the table field delimiter when indexing them
* 0978a2f HUE-7347 [importer] Proper error message when input table does not exist
* cfa38e6 HUE-7346 [dashboard] Do not refresh the document panel on non save as
* 853f794 HUE-7345 [indexer] Index a Hive table into a Collection
* df68283 HUE-7344 [indexer] Avoid default 500 call to rdbms when not initialized
* 94d9966 HUE-7333 [search] Improve top bar after adding the right panel assistant
* f3e8457 HUE-7350 [assist] Right click on collections title should show a context menu
* 9cb78b9 HUE-7352 [assist] Add type to the collection right assistant
* ccf9e44 HUE-7190 [fb] Pressing back in fb when path is not accessible does nothing
* ec8c586 HUE-7248 [adls] fix assist hdfs error on root
* 1040c6d HUE-7340 [search] Solr 7 now supports min() max() on singlevalued strings
* 74644ad HUE-7342 [editor] Make the syntax checker aware of CTE aliases
* ac0afd6 HUE-7341 [autocomplete] Fix issue where the first folder is ignored for HDFS suggestions
* 3714470 HUE-7340 [search] Add new function types stddev() and variance()
* 6d6996a HUE-7339 [search] Bar chart with dimension one and an anlytics facet errors on click
* fc7113b HUE-7337 [search] Do not trigger several time the search() on dashboard load
* fcca1e5 HUE-7337 [search] Use the correct field type for the possible metrics
* 396d3dc HUE-7337 [search] Counter widget should be allowed even if there is no number columns
* 34c26cd HUE-7337 [search] Only show one available dimension in the hit-widget
* 42786d5 HUE-7248 [adls] Fix test_remove and splitpath()
* ded7bef HUE-7335 [editor] Make it possible to close the editor sessions panel form within the panel
* 6b980f5 HUE-7332 [editor] Make the syntax checker aware of database changes
* da621b1 HUE-7331 [assist] Make the assistant panel aware of snippet database changes
* 7a4cd3b HUE-7329 [editor] Don't warn when the syntax checker can't find a token
* d59412a HUE-7328 [assist] Don't reload assistant tables on every change
* 5851cce HUE-7248 [adls] Ability to compress / uncompress data in ADLS
* 129edfd HUE-7336 [search] Add button to add column to the left
* 65b1b47 HUE-7248 [importer] Automatically set as external table based on ADLS data
* 1214197 HUE-7269 [editor] Error popup when exploring table from assist and NavOpt on
* 1a7e797 HUE-6784 [oozie] Disable editor access also disable the browser
* ddf8623 HUE-7327 [impala] CTAS does not trigger an assist refresh
* 5578f55 HUE-7059 [search] Add list of fields to the right panel
* 201d30b HUE-7330 [assist] Improve filter for collection fields
* a0f0a08 HUE-7248 [adls] Fix path of the hueversion symlink
* 91bde74 HUE-7248 [adls] Ability to browse data / content in ADLS
* e5eb6fb HUE-7326 [assist] Include table names in the right assistant filter
* ea101d3 HUE-7325 [assist] Gracefully handle missing tables or backend errors in the assistant panel
* ba8562e HUE-7324 [autocomplete] Prevent js error on column alias selection in the autocomplete dropdown
* 80d579c HUE-7323 [frontend] Enable drag and drop from the global search results
* 72aab05 HUE-7322 [frontend] Re-open the global search results on focus if a query has been entered
* 3b258ab HUE-7321 [frontend] Close the global search results on show in assist
* 07d85f4 HUE-7264 [core] Fix cx_Oracle removed numbersAsStrings in 6.0 https://github.com/django/django/commit/d52577b62b3138674807ac74251fab7faed48331
* b1dfff5 HUE-7316 [jb] Skeleton of Impala Query integration into Job Browser
* 25310ee HUE-7305 [desktop] Revert "HUE-7192 [desktop] Hue Search is failing with DatabaseError"
* 3cb7ff4 HUE-7058 [search] Enable right panel for the search app in Hue 4
* fb340a1 HUE-7296 [assist] Show a generic details view of a document when we can't display the contents
* ef2b8f3 HUE-7296 [assist] Use the document context popover in the left assist
* 089082f HUE-7296 [frontend] Add initial document context panel for global search
* e6a00b3 HUE-7296 [frontend] Don't mark invisible space in the Ace highlight binding
* 0a0060c HUE-7296 [frontend] Add the UUID to returned documents in the global search result
* 5a21282 HUE-7296 [frontend] Improve ApiHelper fetchDocument function to optionally also return the contents
* c6d5e03 HUE-7314 [frontend] Add a plus svg addon
* 0a59e16 HUE-7248 [assist] Add custom icon for ADLS
* e364481 HUE-7313 [jb] Fix JS error on schedule detail page
* 245f220 HUE-7312 [core] Fix scroll to column on sample popup
* eefb87c HUE-6169 [editor] More obvious query log access when there is no "No error message"
* 44d89bf HUE-7304 [editor] Fix scroll rendering problems of the grid results in presentation mode
* 7869e92 HUE-7303 [editor] Avoid result grid size expansion on presentation mode
* 1266355 HUE-7287 [editor] Fix presentation mode list of fields height calculation
* 1b81290 HUE-7300 [scheduler] Simpler names for tasks of schedules
* a3525fb HUE-7300 [jb] Hide more job properties when in mini browser mode
* 0bb3220 HUE-7297 [doc] re.sub needs to be compatible with Python 2.6
* 05ac14e HUE-7297 [jb] Support middle click on the top 'Jobs' menu link
* 0cb5c11 HUE-7288 [editor] Don't check for risks for incomplete statements
* 7498c54 HUE-7299 [assist] Keep the type filter when navigating to different directories
* bbdc66f HUE-7299 [assist] Include directories in the assist document filter
* 5fe0a07 HUE-7297 [doc] Document search highlighting should be case insensitive
* 39673f5 HUE-7285 [oozie] Views should not return Python dates that are not jsonifable
* 51deaf6 HUE-7285 [oozie] Coordinator last modification date is always empty
* 5418494 HUE-7295 [frontend] Fix JS error on clearing the global search input with a selected result entry
* ca08aaa HUE-7294 [assist] Remove the nav search from assist
* 023abb2 HUE-7290 [editor] Make it possible to clear ignored syntax errors
* 753e0d2 HUE-7288 [editor] Don't check for risks when a statement has syntax errors
* bd2e71a HUE-7292 [core] Avoid JS error on window resize when the user has visited the server logs page
* d25f056 HUE-7291 [oozie] Avoid JS error when clicking on file chooser on Schedule submit modal
* e79cd89 HUE-7293 [home] Avoid using the class divider for the breadcrumbs
* ed241bd HUE-6875 [home] Introduce top header like all the other apps
* 40e9e27 HUE-7289 [core] Add article to the switch version message
* 17a8c74 HUE-6835 [autocomplete] Update the Impala SHOW statement autocomplete
* 09de50c HUE-6835 [autocomplete] Add support for TABLESAMPLE in Impala SELECT statements
* 095d2b8 HUE-6835 [autocomplete] Add support for the Impala UPSERT statement
* d967eff HUE-6835 [autocomplete] Improve Impala UPDATE autocomplete for Kudu
* f6dddd9 HUE-7284 [editor] Enable the syntax checker by default
* d0b8c7e HUE-6835 [autocomplete] Improve autocomplete of Impala TRUNCATE statements
* fed5cc5 HUE-6835 [autocomplete] Add PURGE to the Impala reserved keywords
* 2df4241 HUE-7283 [editor] Fix issue where analytic functions aren't found in the context popover
* 6b9136c HUE-6835 [autocomplete] Update Impala built-in UDFs
* 03a5451 HUE-7282 [jb] 'int' object has no attribute 'lower' when click on certain jobs
* 9d6a754 HUE-7275 [jb] Extract / Compress job has wrong timestamps and task names
* 70bca46 HUE-7254 [editor] Update the Schedule tab when saving a new query without requiring a page refresh
* 0785cfd HUE-7266 [oozie] Do not change the URL when saving a coordinator of an integrated scheduler
* ca53845 HUE-7265 [oozie] Avoid deadlock on multiple json GET to retrieve a coordinator
* 03c58a4 HUE-6835 [autocomplete] Improve Impala DELETE autocomplete for Kudu
* 5df44e1 HUE-7278 [editor] Fix JS error on missing parseLocation for the syntax checker
* 9cf96a3 HUE-7279 [editor] Include column aliases in possible suggestions for the syntax checker
* bbe6a88 HUE-7279 [autocomplete] Mark column alias locations
* 4859831 HUE-7277 [autocomplete] Fix issue where columns are marked as tables in the select list when qualified table references are used
* b054888 HUE-7276 [autocomplete] Support variable references in limit clause for Hive
* 3940535 HUE-7270 [core] Do not display warning in Hue 3 on login page
* 1d38458 HUE-7256 [fb] Improve UX for compress/extract as batch job
* e43ea22 HUE-7627 [fb] Fail batch extraction job when extracted files already exist in output folder
* d8f3dc0 HUE-6835 [autocomplete] Add the UNCACHED option to Impala CREATE TABLE statements
* 9777f96 HUE-6835 [autocomplete] Add SORT BY to Impala CREATE TABLE statements
* 4e734c6 HUE-6835 [autocomplete] Improve autocomplete for Impala CREATE FUNCTION statements
* 7635a36 HUE-6835 [autocomplete] Improve ALTER TABLE autocomplete for Impala
* 4e9e482 HUE-6835 [autocomplete] Fix issue with LIKE in SHOW FUNCTIONS
* fa110b7 HUE-7182 [editor] Accented characters not inserted correctly
* f504cda HUE-7268 [assist] Enable right click on the current selected database
* 77c3126 HUE-6835 [autocomplete] Add support for Impala IS DISTINCT FROM
* 468d992 HUE-6835 [autocomplete] Add support for the Impala <=> operator
* d336b06 HUE-6835 [autocomplete] Add support for Impala IREGEXP
* 879c4cf HUE-7259 [autocomplete] Suggest REGEXP instead of REGEX
* 82e8e0f HUE-7230 [editor] In full screen the left column filtering is too high and not shown when scrolling down
* 8cdb597 HUE-7261 [editor] Prevent enormous chart legend labels to take over the chart
* 8c17af9 HUE-7263 [editor] Resize handle off when scrolled down on editor and variables are present
* 60d4988 HUE-7260 [assist] Disable "Open in importer" option for folders in HDFS
* 6677f7b HUE-7124 [frontend] Fix global search escaping test to allow <em>
* cfec4e4 HUE-7245 [search] Protect buckets when other filters can empty their values
* e8c27a5 HUE-7249 [indexer] Index sample data tab can be empty when the collection is small
* 779dddb HUE-7252 [importer] CSV with quoted new lines in fields are not handled propertly
* 0edef68 HUE-7124 [frontend] The global search should highlight the match for Hue documents
* 422757e HUE-7245 [dashboard] Only propose dimention operations compatible with the data type
* fb31ac0 HUE-7244 [presentation] Add feedback effect to the global cancel operation
* 0dffdc7 HUE-7244 [presentation] Cancel a running presentation on exit
* 09a8bfa HUE-7244 [presentation] Support cancelling the main execution
* 146ddc1 HUE-7236 [metastore] Sample data shows the lock row functionality, but it does not work. Same for expand functionality
* 830fa6c HUE-7229 [editor] Expanding a result row a second time does not reset the scroll of the modal to the top
* 11016c8 HUE-6835 [editor] Update the Impala Ace highlight rules
* 261b7ba HUE-6835 [autocomplete] Add support for Impala ILIKE
* 096f8eb HUE-6835 [autocomplete] Add support for integer division with DIV
* 5356309 HUE-6835 [autocomplete] Suggest the NULL keyword in value expressions
* d605096 HUE-6835 [autocomplete] Add support for complex types in Impala column specifications
* 3a5d380 HUE-7246 [importer] Input file input styling can be too short sometimes
* 43e86b8 HUE-7237 [jb] Doc link in Oozie workflow has a mini scrollbar
* 6c12057 HUE-7222 [desktop] Document filtering on home page always return an empty list
* bd8b7d8 HUE-7088 [core] fix test_ui_customizations
* 74c58c0 HUE-7088 [core] Display a warning when users is accessing a Hue 3
* ba90027 HUE-7234 [editor] New variable should be empty
* 6b0c229 HUE-7240 [impala] No available paths to partitioned data
* f253330 HUE-7240 [impala] Workaround non support of partition_spec in DESCRIBE FORMATTED
* 73423e5 HUE-7154 [hive] Replace NoSuchObjectException by QueryServerException
* 61b5495 HUE-7226 [frontend] Log when the editor operations hang
* d9b957e HUE-7243 [assist] Make sure the SQL assist panel is opened from the context popover show in assist action
* dafcee9 HUE-7242 [frontend] Properly dispose the context popover contents for the global search results
* d3f8901 HUE-7162 [assist] Make the document type selection scrollable
* 6a10238 HUE-7241 [assist] Only refresh the docs assist when saving new documents in the editor
* 54e042f HUE-7231 [assist] Keep track of the last opened documents folder
* e8cc2f2 HUE-7186 [editor] Support commenting variables
* 3967dd5 HUE-6984 [editor] Use TeraGen instead of TeraSort
* 99c4a3f HUE-7226 [frontend] Log navigation usage
* 76e17c7 HUE-7227 [frontend] Log usage of popular values in the autocomplete
* a8d1659 HUE-7225 [autocomplete] Prevent new line on enter when a suggestion equals the typed text
* deac508 HUE-7223 [autocomplete] Fix issue where the old autocompleter inserts extra characters on exception
* 2946fb9 HUE-7188 [editor] The save dropdown should be under the horizontal scrollbar
* 8d0af70 HUE-7187 [editor] Save button should be enabled once table name being filled
* 7fc8993 HUE-7220 [dashboard] Correctly reload the loaded states of widgets
* 47cb638 HUE-7220 [dashboard] Also support downloading facet result in csv and xls
* a166299 HUE-7220 [dashboard] Support downloading individual facet data
* fef2c0b HUE-7219 [dashboard] New columns are one slot too small when adding a new one
* 1edda2f HUE-7218 [editor] Offer links if row values are pure http links in the record popup
* dcd371e HUE-7217 [dashboard] Avoid 500 on dashboard when search is blacklisted
* f26f96f HUE-7216 [presentation] Close the editor mode when leaving by other links than the exit button
* 4180058 HUE-6555 [editor] Remove the refresh button of the Saved Query tabs
* 6c951e8 HUE-7215 [indexer] Avoid duplicated column names
* b7ea959 HUE-6555 [editor] Avoid listing only a newly saved query in the Saved Queries tab
* 72e83db [oozie] Improve Spark action to pick up the hive-site.xml easier
* 2e1a8a6 HUE-7213 [editor] Mark the correct statement when executing selection after the first line
* 2169032 HUE-7212 [editor] Properly scroll to the executing query when selected queries are executed
* 2545df8 HUE-7211 [metastore] Invalidate the Impala cache when pressing refresh in the metastore
* 5bd9ec0 HUE-7210 [metastore] Fix the metastore refresh button
* fdf9fa6 HUE-7209 [editor] Make sure pubsub subscribes continue to work when switching between editor types
* 1589644 HUE-7201 [importer] 'Config' object has no attribute 'get' when Solr is not installed
* 31d0763 HUE-7126 [oozie] Improve Spark action to pick up the hive-site.xml easier
* 1c52eb2 HUE-7192 [desktop] Hue Search is failing with DatabaseError field_cast_sql deprecated after Django 1.8
* 42ce476 HUE-7189 [editor] Query result modal is shown only once
* 71e1588 HUE-7207 [frontend] Fix fileChooser search for IE 11
* f510e72 HUE-7206 [editor] Fix stack overflow from fileChooser binding in IE 11
* 193a4c2 HUE-7205 [editor] Fix leaking interval in logScroller
* f591ee5 HUE-5967 [filebrowser] Fix failing unit tests
* 34a454b HUE-1199 [metastore] Wrong time stamp for all export query result to directory or new table
* fec2f51 HUE-7200 [metastore] Refresh table and database js errors
* dab80b1 HUE-7198 [editor] Remove unused onBlur code to improve IE 11 debug performance
* 3f1abcb HUE-7197 [editor] Fix IE 11 JS errors in syntax checker
* 97a4a06 HUE-7196 [assist] Fix JS error for missing Object.values in IE 11
* f9f01a2 HUE-7194 [assist] Fix broken documents panel refresh
* 6870054 HUE-7193 [core] /desktop/debug/is_alive should allow GET requests
* 2fd7d3e HUE-7152 [editor] Enable execute query shortcut inside a variable input
* 5308eaf HUE-7175 [fb] Right click on file, click on a disable action actually clicks on the background
* d5fde8a HUE-5968 [fb] Enable batch extractor flag by default
* f66d9b1 HUE-5968 [filebrowser] Unify the file/archive upload and show extract after upload
* 5175da9 HUE-7185 [indexer] Go back to the index list after deleting one index
* 365eaac HUE-7183 [indexer] Properly bubble up errors when index creation fails
* ff881ff HUE-7184 [search] Protect against nested facets with empty buckets
* e0f6b7e HUE-6256 [presentation] Clear dead snippet from presentationSnippets list
* 2f65ea4 HUE-7177 [assist] Right click "Open in Importer"
* 455bcdc HUE-7169 [editor] Force re-render when swapping between chart and grid mode
* 6b445df HUE-7181 [assist] Collection field list does not get refreshed
* 68ad541 HUE-7180 [search] Hide horizontal column swap when there is only one
* f5a57de HUE-7179 [core] Avoid issue with searching documents on assist or global search box
* e7e3ad4 HUE-7176 [metastore] Open in metastore from Assist does not select the first tab in Hue 3
* c37f720 HUE-7173 [indexes] Add name label to the create alias modal
* e009a2b HUE-7172 [indexes] Analysis popup should disappear when navigating to the list of indexes
* 9e009d2 HUE-7170 [indexes] Analysis popup hidden a bit on non refreshed collection page
* ed61535 HUE-7167 [search] Enable swapping dashboard columns
* 2fe67a4 HUE-7159 [fb] Remove history dropdown
* 5245c84 HUE-7160 [importer] Make arrow in between steps bigger
* e341dd0 HUE-7168 [editor] Add keyboard shortcut for presentation mode and make esc work all the time
* a4c1194 HUE-7166 [aws] deleting s3 bucket throws console error
* 457158c HUE-7165 [aws] hue s3 browser should provide accessibility for all buckets in v2 regions
* 4c6e5af HUE-6831 [metastore] Editing view comments should use ALTER VIEW instead of TABLE
* 5929e00 HUE-7065 [dashboard] Integrate sharing button into the Dashboard
* 4b403df HUE-7156 [core] Fix failing live cluster test desktop.tests:test_dump_config
* 7d46c82 HUE-7156 [core] Fix failing live cluster test notebook.connectors.tests.tests_hiveserver2.TestHiveserver2ApiWithHadoop
* 8de31d0 HUE-7156 [core] Fix failing live cluster test desktop.tests.test_dump_config
* fb54c80 HUE-6256 [editor] Move the query button next to save button
* 7e0b419 HUE-7073 [backend] When user is login using LdapBackEnd, restrict certain characters from the Hue login name.
* c08ea55 HUE-7157 [presentation] Remove title bar if the notebook has no name or description
* 3ed57a9 HUE-6256 [presentation] Re-render all the snippet results in presentation mode
* 7d1ef4c HUE-6256 [presentation] Result grid often not displaying the cells when scrolling
* 563ad3d HUE-7157 [presentation] Align better the top variables
* 62bee8f HUE-7158 [editor] Remove border to the grid results column list
* 7e8b580 HUE-7073 [backend] When user is login using LdapBackEnd, restrict certain characters from the Hue login name.
* 94c9708 HUE-7073 [backend] When user is login using LdapBackEnd, restrict certain characters from the Hue login name.
* 652bedb HUE-7155 [backend] Hue needs to support TLSv1_1 and TLSv1_2 via Thrift connections
* 8b23415 HUE-7107 [core] HUE4 group access doesn't reflect on Interface
* 1c875d9 HUE-7023 [assist] Add a create button to the HDFS panel
* 010d93d HUE-7144 [core] Remove unnecessary tag from documents icon
* 6367ba3 HUE-6256 [presentation] Result grid often not displaying the cells when scrolling
* 63418a7 HUE-7096 [editor] Set opacity of the editors to semi-transparent when in presentation mode
* 55b295c HUE-6901 [oozie] Editor is missing regular ssh action
* 7a6c30f HUE-7096 [editor] Add propert titles to presentation and sharing buttons
* 74452ac HUE-7153 [core] Log usage of presentation mode
* 491f5c6 HUE-7153 [core] Log usage of add filter recommendation
* 391e2c9 HUE-7153 [core] Analytics call to add logging in the backend
* c6b7607 HUE-7096 [editor] Still add a new snippet at execution in notebook mode
* a95969f HUE-7096 [presentation] Restyled presentation mode toolbar
* 3e3e4da HUE-7096 [presentation] Avoid adding a snippet at execution
* 0749493 HUE-7096 [presentation] Fixed icon sizes for the execute and save dropdown
* c538002 HUE-7096 [presentation] Add readOnly to the editors when in presentation mode
* 0c43870 HUE-7150 [presentation] Skip storing the left and right assist status when toggling presentation mode
* fa386a1 HUE-7096 [presentation] Sync the SQL variables values in presentation mode
* d21df7e HUE-7151 [editor] Refactor previousChartOptions to avoid duplication
* f6f3dc0 HUE-7096 [presentation] Avoiding persisting the result data of presentation snippets
* 37dbd50 HUE-7096 [presentation] Reload persisted result grids
* f4bbd8b HUE-7117 [importer] Fix issue with missing trailing slash
* c192996 HUE-7149 [presentation] Missing common share import in Hue 3
* e582873 HUE-6347 [presentation] Split full result page and presentation into independant modes
* 1e7de8e HUE-7096 [editor] Save latest panel states before going in presentation mode
* 39eeae3 HUE-7096 [editor] Add config flag to turn on or off Presentation mode
* e5065d8 HUE-7098 [presentation] Toggle hiding/showing the code snippets
* b7cf645 HUE-7135 [presentation] Add SQL comment as snippet title or text widgets
* 612e430 HUE-7099 [notebook] Add notebook action to presentation mode
* 8971ac9 HUE-7135 [presentation] Hide extra execution information in presentation mode
* 7a15f4e HUE-7099 [notebook] Display variables on top
* afe3070 HUE-7144 [core] Switch document list icon in editors to the document one
* cd87ee2 HUE-6347 [presentation] Rename playerMode to Presentation mode
* f7d5f2d HUE-6347 [presentation] Convert player mode to presentation
* a65912c HUE-7100 [editor] Switch ko model betweeb editor and notebook presentation mode
* ea59bc9 HUE-7128 [core] Create an ENABLE_DOWNLOAD property in 'desktop' conf and use it for the editor and search dashboards
* c2cbf18 HUE-7127 [backend] Fix for Python requests Kerberos/GSSAPI authentication library fails to authenticate kerberos requests to the same destination host.
* 7117d59 HUE-4907 [editor] Provide a default value to parameters
* bcd60fb [aws] Hue throws "Unknown scheme s3a, available scheme" on iam clusters
* 10175e8 HUE-7136 [frontend] Remove references to download.js
* 0359279 HUE-7148 [frontend] Set a default size for SVG icons inside buttons
* e0ea937 HUE-7061 [search] Add the possibility of add/remove the left layout column
* 7223a44 PR584 [doc] Corrected an error spelling (#584)
* 1cae90d HUE-7145 [desktop] Properly revert HIVE_SERVER_HOST set for testing
* 88ff82b HUE-7137 [dashboard] Avoid js error about missing Clipboard in SQL dashboard
* e5570b1 HUE-7141 [dashboard] Menu shows an incomplete dropdown
* 113939d HUE-7055 [importer] Option to add column other than primary key to split-by
* d872748 HUE-7017 [importer] Revert breaking of assist table refresh
* 9ae1a14 HUE-7060 [search] Merge initial layout choices to one single widget and two columns grid
* 9614988 HUE-7137 [editor] Move copy to clipboard inside the download dropdown
* 73bc6b7 HUE-7139 [conf] Remove non-standard double quotes from the configuration files
* bfaa816 HUE-7138 [editor] Open notebook should work also when the editor has not been loaded before
* e62df10 HUE-7097 [notebook] Remove export to Jupyter
* e87ed34 HUE-7064 [editor] Integrate sharing button into the Editor
* 84b913e "HUE4907 [editor] Provide a default value to parameters"
* 7fa5513 HUE-6965 [importer] Supporting import in different file types with different delimeters
* a5aaf4c HUE-6045 [Pig] Update LOG_END_PATTERN to identify completed jobs
* f5ca17f HUE-7129 [desktop] Fix test failure when hbase is blacklisted
* f30e9f7 HUE-7017 [importer] Add JDBC option in both custom and config modes
* fde0544 HUE-7133 [oozie] Bulk add parameters parsed from XML
* 9259e2a HUE-7134 [oozie] Allow vertical resize of Sqoop arguments
* b8b697c HUE-7106 [oozie] New oozie doc url doesn't update after saving the page
* 2ba0e3e HUE-7041 [fb] Items in menu come and go when doing a right clicking on a file
* 0ecbabc HUE-7132 [frontend] Fix Selectize default placeholder i18n
* 6f96631 HUE-7131 [importer] Revert HUE-7051
* e6757c8 HUE-7125 [importer] Dropdown shrinks in the 'external database' section
* 65e9714 HUE-6364 [importer] Dock the bottom bar to the bottom
* f0158ee HUE-6815 [core] Enable new top search layout by default
* bb8fdba HUE-7117 [importer] Use Impala or Hive accordingly when creating a table from assist
* 2fc039a Revert "HUE4907 [editor] Provide a default value to parameters"
* bd10805 Revert "HUE4907 [editor] Provide a default value to parameters"
* 9bc6790 HUE4907 [editor] Provide a default value to parameters
* 30143b6 HUE4907 [editor] Provide a default value to parameters
* 08f0706 HUE-7056 [importer] Minimal arrow linking step 1 to 2
* e8cf424 HUE-6979 [editor] Sometimes editor title/summary are truncated too much
* 21da34d HUE-7024 [assist] The current selected item should have an 'open' action too
* 8d3d526 HUE-7022 [assist] Enable listing the Solr collection fields
* f0018cd HUE-6932 [indexes] Add field sample popover
* c71394c HUE-7108 [desktop] Add config check to see if the migration history table is up to date
* dc21298 HUE-7112 [oozie] Do not escape characters in decision node condition
* 1b9c238 HUE-7114 [filebrowser] Edit File could be in a fixed width font
* ed98097 HUE-7027 [fb] Opening a file directly via editing path lands on Hue 3
* 985f816 HUE-7079 [editor] Keep the last 50 risk responses and clear the risks on statement change
* fd8bce2 HUE-7124 [frontend] Use the orignalName attribute for inline autocomplete in the global search
* c479028 HUE-7123 [autocomplete] Include the join type if given when suggesting popular joins
* a55b545 HUE-7122 [autocomplete] Don't add db prefix in popular join conditions for Hive
* 4eb16f8 HUE-7118 [editor] Take statement location into account when marking query compatibility warnings
* 0c6a55f HUE-7115 [autocomplete] Show popular joins above popular filters
* 19bcf9c HUE-7116 [editor] Fix syntax checker js error when table ref is missing
* 3b993ac HUE-6815 [frontend] Make the new global search clearable
* 13d2dbb HUE-7093 [frontend] Unify table headers and sorters styles across the various apps
* 5ed5988 HUE-7117 [frontend] Harmonize all the monospace occurrences and move to Roboto Mono
* 6b899c4 HUE-7109 [useradmin] Add/Sync LDAP Group should refresh the group list and show a sync message
* 7379fbf HUE-7120 [presentation] Set a minimum height for the editors
* 493facc HUE-7025 [editor] Move copy to clipboard outside the download dropdown
* 43917dc HUE-7107 [core] Grant Hive permission in Notebook test
* 3658b32 HUE-7090 [security] Protect against another potentially missing groupName key
* b3926f7 HUE-7107 [core] Adding tests to check for custom user permissions
* f69521c HUE-7107 [core] Hue 4 group access doesn't reflect on Interface
* 6f05306 HUE-5991 [metastore]  New table with Date time works with Hive but not with Impala
* fff96b7 HUE-6815 [frontend] Enable open on enter and show in assist for the global search result entries
* 48a171e HUE-6815 [frontend] Add right panel contents for documents in the global search results
* c996918 HUE-6815 [frontend] Improve global search autocomplete and suggest documents
* ac1f1e6 HUE-6815 [frontend] Adjust the global search parser to also suggest results
* c276045 HUE-7105 [importer] Column list is not aligned on large screens
* 79c7412 HUE-7110 [editor] Focus on the SQL editor when opening Hue
* 6d9dab3 HUE-7030 [jb] Style Oozie SLA not available page
* 249d566 HUE-7029 [jb] Switching between log types should reset the log content before loading the new one
* ef04dd9 HUE-7094 [frontend] Filechooser should never navigate by default to an empty path
* 32cd816 HUE-7084 [useradmin] Remove @domain part of username when creating home directory for LDAP user
* 24caadf HUE-7104 [core] Hue and Isilon issue - UnsupportedOperationException: Unknown op 'GETTRASHROOT'
* 5337a95 HUE-7091 [assist] Follow case when adding filters with the risk quick-fix
* 965acfe HUE-7091 [assist] Show add filter action for missing partition filter risk
* 9ce33d9 HUE-7091 [autocomplete] Show whether a column is a partition key or not in the autocomplete suggestions
* 7e4e8bc HUE-7092 [autocomplete] Adjust the parser to also report location of select lists
* fa67a5b HUE-7018 [jb] disable_killing_jobs option is not supported in the new job browser
* eee7a04 Revert "HUE-7018 [jb] disable_killing_jobs option is not supported in the new job browser"
* 3638d77 HUE-7095 Table import not working
* 74b6fab HUE-7090 [security] Protect from missing groupName in the list_sentry_roles_by_group API
* 2801712 HUE-7087 [frontend] Skip showing assist.db.refresh output links on the history panel
* 3308a45 HUE-7086 [core] Clicking on a task item to select it closes the task popup
* 78157e7 HUE-7080 [oozie] Oozie HiveServer2 action is prompting for and 'Impalad hostname'
* 9618db7 HUE-7082 [aws] Create S3 bucket fails with error Bad request
* 4ebedb9 HUE-7019 [fb] show_download_button is not integrated in the backend
* 6e84bff HUE-7085 [useradmin] Remove unused view_user view
* ef13ceb HUE-7082 [aws] Create S3 bucket fails with error Bad request
* d6ba27b HUE-6659 [importer] Fix wrong ko if code on the list of fields
* 29cbef1 HUE-7004 [notebook] Fix special character typos
* d9238dd HUE-6976 [editor] Don't suggest to add filters in subqueries for risk quick fix
* 2b413c5 HUE-6976 [editor] Fix issue where filters are suggested in the wrong statement
* d869d8a HUE-7071 [frontend] The left nav should always be on top
* 8ab31a3 HUE-7052 [desktop] Retain last_modified when sharing sample docs in sync_documents
* dab8f5a HUE-7075 [assist] Allow to refresh other types than Hive and Impala
* 7445829 HUE-7074 [frontend] Extend hueDebug to accept the id of the element as well
* 7e1c983 HUE-7072 [importer] Disable fields that are not marked as keep
* 04bd640 HUE-7070 [importer] Prefill the destination name for the database importer
* 121e37c HUE-7104 [core] Kerberos section is not up to date in the inis
* 1e58534 HUE-7069 [editor] Remove the spinner for risk checking
* 117d36c HUE-7049 [assist] Add skeleton for generic assist contents
* a9bd843 HUE-7049 [assist] Unify popover pubsub ids
* 56cd07b HUE-7049 [assist] Add a generic breadcrumb component
* 378b69f HUE-7050 [assist] Add a feature flag for the new generic context popover
* 70b9764 HUE-7049 [assist] Extract a generic context popover component
* 583b541 HUE-6997 [core] Leaflet_tile_layer should allow case sensitive URIs
* 9c89076 HUE-7067 [dashboard] Refresh facet result when reordering sub-facets
* c45dcde HUE-7018 [jb] disable_killing_jobs option is not supported in the new job browser
* 3ca4983 HUE-7004 [notebook] Loading query with empty session param shows several JS errors
* f4eb5a7 HUE-7068 [frontend] Update knockout sortable binding to the latest version
* eba408a HUE-7035 [frontend] Close editor sessions panel on app switch
* 3a016b0 HUE-7033 [jb] Switching from Hue 3 to Hue 4 should remap the old URL to the new one
* dc056fe HUE-7066 [frontend] Missing grunt uglify dependency on packages.json
* bafd4c4 HUE-7057 [search] Make widget dimensions draggable
* 093ec6c HUE-7053 [search] Indexer requires options to avoid jar classes conflicts
* 3a51ecf HUE-7051 [importer] Add SQL editor to the importer for RDBMS
* a048a03 HUE-6659 [sqoop] Restyle password input and align test connection button
* fcc2dba HUE-7048 [oozie] User prompting doesn't work in share document popup in hue4
* fcf9a32 HUE-7031 [oozie] Promote tabs to the usual Documents icon for browsing documents
* ab3b119 HUE-7005 [oozie] sharing coordinator or bundle immediately after creating fails
* c2dfb6f HUE-6912 [sqoop] Securing Database password in oozie
* bd65589 HUE-7046 [frontend] Fix open.link on Hue 3
* 98b0aeb HUE-7044 [oozie] Be consistent with the Schedule name in Hue 4
* 55f3432 HUE-7043 [frontend] Switch fa-tags with fa-list for list of files links in the apps
* 198e2c6 HUE-7045 [hive] Avoid use database call for SET queries
* e1e1ef1 HUE-7010 [sqoop] Take configured databases from librdms instead of hardcoding the list of drivers
* cb5be91 HUE-7040 [oozie] Pressing Esc on share popup throws JS error in Hue4
* 97ba1c6 HUE-7039 [oozie] Remove JS auto center of the workflow actions
* 271cead HUE-7012 [jb] Wrong spelling of Job has not tasks
* b084c51 HUE-7036 [fb] Disable full page refresh on folder open
* 2ca6587 HUE-6976 [editor] Add a fix action to the missing filters risk
* 359f504 HUE-7028 [editor] Don't mark where and limit clauses on hover
* 243f286 HUE-7026 [editor] Allow Solr autocomplete even if Solr SQL is not enabled
* 90cc1a8 HUE-7026 [editor] Add an HBase connector
* a42e3fd HUE-6377 [importer] Submit doesn't give a feedback if the call takes a long time
* 29b898c HUE-7015 [frontend] Set default background color to white
* d09a62d HUE-6962 [importer] Index field operations overlap with the submit button
* 75f0cfa HUE-7011 [jb] JS error on workflow with taks without a startTime
* f2f33d9 HUE-6835 [autocomplete] Add support for new Impala join types
* 8a528ba HUE-6835 [autocomplete] Add support for Impala STRAIGHT_JOIN keyword in select statements
* 264ca3e HUE-6835 [autocomplete] Update Impala REFRESH statements to the latest syntax
* ffe5890 HUE-7020 [indexer] Provide the real lib_path at the Morphline config generation
* d6597d7 HUE-7016 [libsentry] HA retry on SOLR component does not set the component value
* 5bab140 HUE-6999 [core] Deleting admin user message yes button keeps circling
* dd2758d HUE-6785 [doc2] Return more useful error message when users try to create a directory within a read-only shared directory
* 0dfe47f HUE-6993 [sqoop] Support for configurable number of mappers
* 4c899c4 HUE-7006 [core] Ability in HUE to change Cookie name from default "sessionid"
* 730373d HUE-7013 [backend] Make Kerberos Mutual Authentication property case insensitive
* 5febf6f HUE-6988 [jb] After killing the MR job, the interface hangs
* 9d65704 HUE-7009 [editor] Do not show any progress during automatic uploads of stats
* 02dbb12 HUE-7009 [metadata] Automatic upload of table stats if missing
* 6ce125c HUE-7013 [backend] Provide Kerberos Mutual Authentication disable switch in "hue.ini"
* 92bde8e [HUE-6486] Move Hue Krb ticket cache out of /tmp
* 21f8e7a HUE-6934 [importer] Added backend for taking the sqoop jar paths from UI parameters/ asking from end-user
* 0851153 HUE-6934 [importer] Added Sqoop job libs multiple file chooser
* 738d921 HUE-7008 [autocomplete] Minify the generated parsers
* 6e5878b HUE-6835 [autocomplete] Add support for the PURGE keyword in DROP TABLE statements
* 6b9aa5f HUE-7001 [assist] Remember the last selected HBase cluster
* 739cc5d HUE-6990 [editor] Mark unknown columns and aliases in the syntax checker
* dfd92ee HUE-6990 [autocomplete] Take table aliases into account when verifying table existance
* 68249ed HUE-6990 [autocomplete] Add table and subquery alias locations
* 33a59db HUE-7000 [assist] HBase assist does not load the table the second time
* 7a68432 HUE-7002 [core] Welcome to Hue 4 tour could be also skipped by clicking on the white background
* 4bed593 HUE-6996 [frontend] Clicking on home doesn't allow to go back in history
* ce4d317 HUE-6989 [jb] Clicking on the jobs button doesn’t allow me to go back to the editor with the back button of the browser
* f605eef HUE-6659 [import] Cleaned code based on the code review. Added rdbms.py. Replaced test connection checkbox with button
* 1edcc00 HUE-6659 [import] added hive as a new option in Rdbms data import.
* b208bbf HUE-6659 [import] added test connection front-end for custom db and output options for external databases
* 05f07fd HUE-6659 [importer] Database name and Table name dropdown populated successfully for config mode
* 4617cc1 HUE-6659 [import] added custom and config database options
* bc92257 HUE-6659 [importer] Quick clean-up to submit sqoop as a task
* 46e2e39 HUE-6659 [import] Support RDBMs as input via Sqoop
* 2b938da HUE-6995 [oozie] Set minimum width of a workflow node
* fe5bd8c HUE-6969 [jb] Start time, Finish time, Elapsed time of tasks of MR jobs are not formatted
* 5fbdbb7 HUE-6981 [oozie] Configuration text filter spacing is a bit off
* e00844a HUE-6992 [editor] Unable to paste via right click menu
* ab7ae60 HUE-6975 [core] 500 in configuration on /hue/desktop/dump_config
* a3ff7af HUE-5217 [backend] Resolve LGPL copyleft issue - Paramiko in boto 2.46.1
* 7b15b90 HUE-6968 [metadata] Gather column stats via Impala
* 9b71571 HUE-6968 [metadata] Gather table stats via Impala
* d4f453f HUE-6954 [indexer] Support different number of shards, replication at index creation
* ff6fe4e HUE-6974 [importer] Refresh Assist collection list after create table wizard success
* e273d33 HUE-6973 [indexer] Open up the index page after creating a new index
* 048b7b9 HUE-6972 [metadata] Sometimes the DB owner is shown as ()
* ac41d00 HUE-6971 [jb] Schedule list is filtered by default on 7 days which hides most of them
* 96c9467 HUE-6977 [editor] Fix issue where the autocomplete dropdown doesn't show for column completion
* 55efd6b HUE-6976 [autocomplete] Report locations for WHERE and LIMIT clauses
* 48a76df HUE-6928 [assist] Add filter to right assistant
* 2820a04 HUE-6746 [autocomplete] Add USER and TIMESTAMP to non-reserved keywords list
* 96a64df HUE-5736 [autocomplete] Cancel any running API requests when closing the autocompleter
* b1600b1 HUE-6960 [frontend] Only suggest facet values and no results when autocompleting facets in the top search
* b194fb7 HUE-6952 [doc] Remove warning description
* 4e8f070 HUE-6950 [saml] Create home directory for new user login
* 9cc9adf HUE-6955 [metadata] Extend query suggest caching to 1 week
* fb74116 HUE-6944 [indexer] Support manual creation of collection
* 813b0be HUE-6953 [indexer] Support skipping field in non task mode
* bacfb9c HUE-6942 [indexer] 404 error when creating an index from a file that has a _version_ field
* 1071df9 HUE-6948 [indexer] Warn when indexer name is invalid
* 78ed73a HUE-6951 [indexes] Index with no data has an empty field section
* 77e23e9 HUE-6943 [indexer] Move out create Solr index of main create API
* a1f0aa7 HUE-6943 [indexer] Error when input file does not have any headers
* 62fc869 HUE-6949 [indexer] Cleaner error message when coming from Solr
* 1aa721e HUE-6945 [search] Aliases cannot be retrieved with Solr 4
* 27dedef HUE-6957 [importer] Primary Key dropdown opens on selecting Default field dropdown
* 39bc59b PR570 [core] Update JsonResponse to support set json_dumps_params (#570)
* ac26a61 HUE-6961 [frontend] Filechooser inputs sometimes have rounder corners on the right side of the input
* 954d520 HUE-6938 [indexes] Harmonized section titles
* 6de1d26 HUE-6959 [assist] Fix collection opening from left assist
* 719ed92 HUE-6937 [importer] Improve UX by giving context on what import you are executing
* d02e484 HUE-5463 [autocomplete] Add autocomplete support for partitions in Hive describe table statements
* 4be3c5a HUE-4031 [editor] Don't suggest dialect specific fixes for syntax errors if no dialect is specified
* 5724b31 HUE-5504 [oozie] Only use JDBC URL from hive2 action when hardcoded
* 04cdd49 HUE-2961 [indexer] Turn on the new interface by default
* d77736d HUE-6936 [indexer] Move SQL indexing into its own flag
* 18686df HUE-6930 [importer] Libs filechooser input should be shorter
* 4e28db0 HUE-6941 [editor] Don't show a pointer cursor for the risk check spinner
* e944143 HUE-6940 [editor] Cancel risk requests if editing while risk check is running
* 0259e65 HUE-6939 [editor] Improve interactions with the risk indicator
* c40cab2 HUE-4031 [editor] Suggest possible table names when it can't find a matching table in the syntax checker
* 1bdbab6 HUE-4031 [editor] Don't suggest parser specific tokens when there's a syntax error
* 2cb15d0 HUE-6938 [importer] Restyle section headers
* f009bf3 HUE-6937 [importer] Improve UX by not hiding the pre-filled wizard destination
* 4bf08b0 HUE-6891 [importer] Incorrect Warning for tables starting with #
* 916dd4f HUE-6931 [indexes] Hide table headers when tables are empty
* 3704868 HUE-6933 [indexes] Show a message when there's no sample data
* 2df69de HUE-6819 [oozie] Add test to validate graph with multiple generic actions
* 77cfeaa HUE-6926 [indexes] Make indexes table more compact and center vertically select all checkbox
* eab8d70 HUE-6926 [indexes] Refresh assist on collection removal and alias creation
* 2fec765 HUE-6926 [indexes] Clicking on the top level breadcrumb should reload the indexes
* 27cace1 HUE-6911 [indexes] Display sample data of schemaless collections
* 7e3241d HUE-6910 [indexes] Display dynamic and copy fields
* 24c82d8 HUE-6909 [libsentry] Use the new sentry config property sentry.service.client.server.rpc-addresses
* 59570c1 HUE-6908 [jb] Basic Livy session page
* 0210fda HUE-6908 [spark] Add get sessions API
* 9bff785 HUE-6908 [jb] Skeleton of Spark API
* 8c51399 HUE-5396 [spark] Hide extra add property dropdown
* ad9f5fa HUE-6923 [fb] Fix table header borders
* d6a9ce6 HUE-6922 [fb] When typing in the search box, last 1 or few characters get deleted when the list is refreshed
* a5d638f HUE-6925 [indexes] Enable column filtering
* 1ff8a2c HUE-6925 [indexes] Style the section titles
* 9813c85 HUE-6903 [dataeng] Add submitted status to list of running job statuses
* 4f7565e HUE-6903 [editor] Dataeng jobs should fully refresh their logs and not append them
* 1fdfd7a HUE-6903 [fb] Fix opening an external SQL file into the editor
* 4f3304a HUE-6903 [dataeng] Fix for s3 context popover
* 2879e95 HUE-6900 [dataeng] Fix killing a job command
* ebf2557 HUE-6885 [editor] Avoid double messages on HTTP 502
* 1d6037a HUE-6907 [search] The dashboard header is bigger than the other headers
* 8fe7020 HUE-6906 [frontend] 'Add more' should open in a new tab and not throw a 404 in Hue 4
* 51a684f HUE-6895 [frontend] Disable errorcatcher when in Django debug mode
* b7d0a1d HUE-6896 [frontend] Errorcatcher should not log jQuery triggered events
* 704cc16 HUE-6905 [jobsub] List of designs does not reloads after saving, copying, deleting and restoring
* 3eefdc0 Revert "HUE-6370 [jobsub] Save jobsub doesn't redirect to list-designs page."
* bbca5dc HUE-6905 [pig] Pig scripts have broken links on "Scripts" page
* 4dcf5eb HUE-6897 [oozie] Ensure that examples_dir exists before installing examples (#566)
* 32029a0 HUE-6901 [oozie] Editor is missing certain regular actions
* 9637772 HUE-6900 [useradmin] Do not link app title to list of users if user not a super user
* a286b3c HUE-6899 [core] Allow 403 to be accessed by regular users
* 3cf5686 HUE-6898 [oozie] Editor doesn't update job status to "finished" for finished Pig jobs (#565)
* e3bca30 HUE-6894 [core] Remove cluster config call on login page
* f0456e2 HUE-6890 [autocomplete] Add support for database prefixed UDFs
* 87a13e5 HUE-6889 [oozie] Force wrap oozie IDs on the detail page
* 773bb39 HUE-6885 [frontend] Catch all http 502 and show an HTML stripped version of the message
* 948e872 HUE-6888 [libopenid] Style clean-up of lib
* 717bf98 HUE-6888 [oozie] Fix link page on SLA  with Hue 4
* 78b0f75 HUE-6886 [oozie] SLA variable in workflow action are not getting retrieved
* ab6b4c6 HUE-6884 [core] Allow to blacklist the Hive
* fe08b64 HUE-6866 [core] Js error popup does not re-appear if same as previous one which was closed
* bc878c4 HUE-6868 [search] Field analysis popup shows up too high if down scrolling
* 496d627 HUE-6883 [metastore] Allow deletion of table comments
* b3e4742 HUE-6882 [metastore] Fix issues with the description overflow toggle
* 9aa89f7 HUE-6881 [editor] Display table type in the SQL context popover
* a5f3699 HUE-6877 [rdbms] Server error label misspelling
* cdf3a0e HUE-6880 [fb] Missing bottom gray border table header styling
* 4e19fa2 HUE-5304 [indexer] Corrected import positioning
* 4e577ce HUE-5304 [indexer] Made mini sample table scroll horizontally and big sample table sortable with fixed headers
* 4782611 HUE-5304 [indexer] Open correctly the links from Assist in the new indexer
* f498b4c HUE-5304 [indexer] Fix typo in the index list URL
* b3a7f64 HUE-6727 [jb] 0/1 map progress percent gets listed as 100%
* e26a199 HUE-6870 [jb] Add status API field to tasks and task attempts
* 4a6efde HUE-6870 [jb] Display workflow action properties on tab opening
* 1655b8e HUE-6870 [jb] Add filter on Job properties tab
* 04ae887 HUE-6870 [jb] Add filter on Job metadata properties
* ece5a27 HUE-6870 [jb] Offer stdout log of most interesting job task by default
* 0b8fee0 HUE-6870 [jb] Open launcher task log of workflow action in one click
* 6c9524d HUE-6870 [jb] Properly display color status of schedule tasks
* e2b4ad7 HUE-6870 [jb] Add link to workflow from job page if available
* 5a1a40f HUE-6870 [jb] Fix link to Tasks of schedule page
* 9df1b28 HUE-6870 [jb] Display job name of finished YARN jobs
* 1dc4dd9 HUE-6874 [search] Stabilize showing of nested document schema icon
* 22844dd HUE-6874 [search] Make showing of core automatic and only if in non Solr Cloud
* 21adaf8 HUE-6874 [search] Support nested facet of one dimension with no value in bucket
* 6e6366f HUE-6874 [search] Properly reinitialize the nested facet form
* 679ad16 HUE-6149 [search] Smarter catching of Solr error message
* 1485888 HUE-6855 [frontend] Set a default application tooltip sometimes doesn't disappear
* 56a4cef HUE-6859 [search] Fix default size of the search field
* 0404472 HUE-6868 [frontend] Improve bar label shadow/stroke
* 4ccf0c1 HUE-6864 [jb] Check for permission before killing a job
* 5669e4f HUE-6863 [jb] Job Kill buttons are enabled even when the user is not allowed
* 32c8f19 HUE-6863 [jb] Schedule Kill buttons are enabled even when the user is not allowed
* 65f2cca HUE-6859 [search] Provide a longer search bar by default
* c46ea1c HUE-6859 [core] Rename old Pig script type to avoid conflict with Pig script
* 668dddc HUE-4031 [editor] Enable suppression of syntax errors based on rule
* dd50287 HUE-4031 [editor] Mark trailing non expected tokens as errors
* 8c0a9fb HUE-6815 [frontend] Show a spinner while loading the search results
* d6d4d8d HUE-6815 [frontend] Add config flag to enable the new global search
* 10b3e0f HUE-6815 [frontend] Show details for SQL result
* c3c11f1 HUE-6815 [frontend] Show results in the new global search panel
* 1563db5 HUE-6815 [frontend] Clear the inline autocomplete when focus is lost
* 000d2f3 HUE-6815 [frontend] Don't suggest facets that are already entered in the global search autocomplete
* 34044dc HUE-6815 [frontend] Add facet value suggestions to the global search autocomplete
* 7054ca7 HUE-6815 [frontend] Enable inline autocomplete in the global search input
* 0c22475 HUE-6815 [frontend] Create a custom parser for global search autocompletion
* e137bfe HUE-6815 [frontend] Add event handlers for global search results
* 9dbc822 HUE-6815 [frontend] Initial styling of global search result categories
* 4eef737 HUE-6815 [frontend] Add basis for in-place autocomplete of global search
* ecc3dc2 HUE-6815 [frontend] Initial layout of new global search result panel
* 54a24e6 HUE-6815 [frontend] Improve the onClickOutside binding
* 18574ea HUE-6815 [frontend] Extract the top search to a separate KO component
* ee63a59 HUE-6862 [jb] Workflow filtering on username does not happen
* bdaedb8 HUE-6861 [search] Do not 500 when Search is not enabled
* 081ff19 HUE-6859 [index] Improve edition of aliases
* 5da671d HUE-6859 [index] Support creating collection aliases without page refresh
* 387bc1b HUE-6835 [autocomplete] Update the Impala ACE highlight rules
* e94c312 HUE-6858 [indexer] Add load data action
* ef1d219 HUE-6857 [dataeng] Retrieve batch Hive queries via troubleshooting API
* 441b026 HUE-6857 [dataeng] Only filter the jobs of the active cluster
* 4a0c75e HUE-6857 [metadata] Add skeleton of troubleshooting API
* d3e693b HUE-6857 [dataeng] Support latest job displaying API
* 55c9c3d HUE-6848 [jb] Add doAs impersonation when fetching job logs
* 37b529b HUE-6856 [search] Protect against reflected XSS in search query parameters
* 4d3e79f HUE-3797 [editor] Open submitted schedule in mini job browser
* 1aee214 HUE-6794 [editor] Update table stats upload with new assist format
* f86877a HUE-6850 [importer] Rely on default SQL editor type for creating tables
* f97e6c1 HUE-6850 [metastore] Rely on default SQL editor type for DDL operations
* 1cc6667 HUE-6850 [metastore] Rely on default SQL editor type for querying data
* a4434c4 HUE-6850 [importer] Add link to job submission libraries on HDFS
* 99300ff HUE-6852 [editor] Scroll left does not disappear when going to metastore from editor
* 3459708 HUE-6854 [home] Clicking on a folder should open it
* 9ad749a HUE-6853 [jb] On mini jb clicking on breadcrumbs shouldn't close the popup
* b300810 HUE-5304 [frontend] Revert changeURL check
* 4245f21 HUE-6835 [autocomplete] Add CASCADE and RESTRICT to Impala DROP DATABASE statements
* 0a0171f HUE-6835 [autocomplete] Add completion for Impala DELETE statements
* 062295c HUE-4031 [editor] Fix variable naming conflict with contextmenuListener
* 064436e HUE-4031 [editor] Adjust syntax error locations when there are multiple statements
* ede93e3 HUE-4031 [editor] Prevent JS error when hovering over a token while typing
* 0b18470 HUE-4031 [editor] Warn when an unknown table is found in the query
* 7756ce9 HUE-4031 [editor] Add missing variables to the syntax paraser
* 96ea2af HUE-4031 [editor] Log a warning when we can't mark a syntax error
* 20f1ed1 HUE-4031 [editor] Improved behaviour when enabling or disabling the syntax checker
* 0fc8f07 HUE-4031 [editor] Make the syntax suggestion drop-down scrollable
* 362c27e HUE-4031 [editor] Prevent duplicate syntax suggestions when a dialect is specified
* b537c17 HUE-4031 [editor] Don't suggest non-alpha chars for syntax errors
* c281b31 HUE-4031 [editor] Make sure repeated errors are marked
* 404adeb HUE-4031 [editor] Improve token marking based on error location
* 76fae74 HUE-4031 [editor] Show a dropdown with suggestions when right-clicking syntax errors
* 3ac4014 HUE-4031 [editor] Make sure the syntax parser has the same functions as the autocomplete parser
* b07e9ca HUE-4031 [editor] Add random parameter to web worker imports when in debug mode
* 5aaa25f HUE-4031 [editor] Fix for incorrect jison syntax error location
* 2d06dce HUE-4031 [editor] Follow case when suggesting syntax error corrections
* df98b33 HUE-4031 [editor] Sort expected alphabetically when distance is equal
* 8d3b4bc HUE-4031 [editor] Pre-calculate distances to improve performance
* 480bf91 HUE-4031 [editor] Mark syntax errors in the editor
* 7b8a7cc HUE-4031 [editor] Add a global config flag to enable or disable the SQL syntax checker
* b4ae7ff HUE-4031 [editor] Sort the error suggestions based on similarity
* 3c77ccf HUE-4031 [editor] Add a dedicated web worker for syntax checking
* 7fa834c HUE-4031 [editor] Make sure we only suggest clean keywords based on dialect
* 322f6a5 HUE-4031 [editor] Don't identify the current edited word as an error
* 5927775 HUE-4031 [editor] Create initial structure for the syntax parser response
* 8bcba6f HUE-4031 [autocomplete] Fix issue with parseError in the autocomplete parser
* 6387199 HUE-4031 [editor] Move the jasmine tests to the correct folder
* 2ae87fb HUE-4031 [editor] Create initial syntax parser for error highligting
* 84a63a3 HUE-4031 [autocomplete] Create a parser dedicated to autocomplete
* 709ad0c HUE-5304 [indexer] Support for old URLs when the feature is off
* 3bc1683 HUE-5304 [indexer] Integrate new URLs with Hue 4
* 7d89b80 HUE-5304 [indexer] Reset index when moving back to the list of indexes
* 549889d HUE-5304 [indexer] Moved index actions to the same level of breadcrumbs
* 50033d0 HUE-5304 [indexer] Hide search and creation buttons when viewing an index
* 27745f5 HUE-5304 [indexer] Plug in index filtering
* 40647cf HUE-6847 [metastore] Display table type as a property
* 44ebe2f HUE-6847 [metastore] Do not display if table is compressed as Hive information is incorrect
* e743c19 HUE-5304 [indexer] Update URLs when selecting an index or listing all the indexes
* fe9606b HUE-5304 [indexer] Add links to the list of indexes
* 326e806 HUE-6839 [home] Avoid action icons to be shown unstyled at page load
* 7303070 HUE-6835 [autocomplete] Add WITH REPLICATION suggestion to CREATE TABLE
* 21f5e65 HUE-6835 [autocomplete] Add WITH REPLICATION suggestion to ALTER TABLE
* 53cbb07 HUE-5304 [indexer] Support deleting an index
* ae948a5 HUE-6840 [notebook] Workaround lack of status flag in Impala profile page
* 2be81c2 HUE-6843 [metastore] Show partition icon on table browser sends to Hue 3
* 981e38e HUE-6846 [frontend] Make all proxy apps embeddable
* f7f487f HUE-6844 [frontend] Make all custom apps embeddable
* 491e50e HUE-6845 [frontend] Fix custom app mako generation
* 56ff3a0 HUE-6794 [assist] Show column tree in the right assistant
* 9f9c2be HUE-6794 [assist] Switch to using the AssistDbEntry instead of MetastoreTable in the right assistant
* cb66777 HUE-6842 [core] Correctly append the list of custom apps
* 410e714 HUE-6841 [oozie] Copy examples to HDFS as the hue user
* 6d33ecf HUE-5304 [indexer] Trigger only one time the install of search examples
* a465fd3 HUE-6820 [core] Log js errors with ERROR level
* bcfe0fb HUE-6380 [editor] Move clipboard option above Save menu
* d8c6b51 HUE-5304 [indexer] Added nice spinners to initial and sample loadings
* 81b255f HUE-5304 [indexer] Promoted create/edit alias to modal
* 54762b5 HUE-6796 [search] Port morpline indexer tests to SolrClient
* 555ac93 HUE-6796 [search] Clean-up the solr cvs columns to be compatible with Solr types
* de3a762 HUE-5304 [indexer] Fix Morplhine indexer to work with upstream Solr
* f202c88 HUE-6796 [search] Parallelize the installation of the search examples
* 9f232ba HUE-6796 [search] Port example indexing to new Solr Client to skip HDFS copies
* 0d2ab88 HUE-5304 [solr] Add tests about dynamically retrieving Solr properties
* db2b406 HUE-5304 [solr] Fix leaking of non specified Zookeeper ensemble and root
* 50d9914 HUE-5304 [indexer] Scoped JS on the page to avoid leaking into Hue 4
* a02e522 HUE-5304 [indexer] Added assist on Hue 3
* ba9dc0a HUE-5304 [indexer] Added LESS to the new indexer
* 6faf837 HUE-5304 [indexer] Sample data should be on the same line of the field name
* a8d9bdb HUE-5304 [indexer] Made indexes page available on Hue 4
* 2765bfa HUE-5304 [indexer] Support example install with Solr 4 or 6
* 4c34fa2 HUE-5304 [indexer] Auto conf with Solr in HDFS mode or not
* 067b959 HUE-5304 [indexer] Auto conf with Solr 4 or 6
* e3d2c34 HUE-5304 [indexer] Add listing of calls
* b829a89 HUE-5304 [indexer] Displaying error message if any when listing collections
* 2a75a64 HUE-5304 [indexer] Adding logic to turn on/off the new index page
* 6cf01ac HUE-5304 [indexer] Add index page with properties, sample data and field list
* a9f9c93 HUE-5304 [indexer] Revamp skeleton of index page
* 48b83e5 HUE-5304 [indexer] Revamp skeleton of indexes page
* ca70271 HUE-5304 [indexer] Add link to create index wizard to the assist
* 9a4ef1b HUE-5304 [indexer] Add column examples to the index field list
* 333fb91 HUE-5304 [indexer] Update default name when the output changes
* 4b31b81 HUE-5304 [indexer] Provide lib path to morphline indexer
* f3c95a8 HUE-5304 [indexer] Update tests with correct number of whitespaces
* 35b89d5 HUE-5304 [indexer] Update name when switching output format
* 7ddced4 HUE-5304 [indexer] Convert column types when switching between Hive or Solr output
* f26c379 HUE-5304 [indexer] Adding redirection to index after creation
* 540ff49 HUE-5304 [indexer] Add support to native CSV indexing
* 7bdd083 HUE-5304 [notebook] Do not 500 on query upload from notebook
* a75b45b HUE-5304 [indexer] Adding template variables to create a new collection
* d6401e4 HUE-5304 [indexer] Move SQL indexer into its own lib
* cffca3b HUE-5304 [indexer] Move morphline indexer into its own lib
* bd556c3 HUE-5304 [indexer] Use new API to list indexes
* 8de909d HUE-5304 [indexer] Port morphline job to work with task framework
* 377b9b5 HUE-5304 [libsolr] Copy solrconfig.xml accordingly to the type of Solr server
* adfd506 HUE-5304 [search] Move list of collections to use the new API
* f702763 HUE-3228 [dashboard] Add explore table to sample popup
* 81ae210 HUE-3228 [dashboard] Add explore table in assist menu
* 9d6a5b3 HUE-5304 [indexer] Integrate indexer with latest Solr API
* c81368d HUE-5304 [search] Asynchronously load the indexes
* b4fb595 HUE-5304 [solr] Fix listing collection aliases
* 3715e99 HUE-5304 [solr] Fix creating aliases
* c9d8613 HUE-5304 [solr] Add configs for upstream and non HDFS
* 1a1dc64 HUE-5304 [solr] Guess config path in ZooKeeper depending on Solr distribution
* 1fef107 HUE-5304 [search] Support upstream Solr Cloud mode
* e61ae6c HUE-5304 [solr] Refactor create a collection to support managed templates
* 4a76f84 HUE-5304 [indexer] Move api2 to solr_api
* 0535412 HUE-5304 [indexer] Move Solr Controller2 to SolrClient
* 356843f HUE-6763 [search] Add global default if in cloud mode
* 40a32bd HUE-5116 [indexes] Remove unfinished create collection from a file
* c1a127e HUE-5304 [indexer] Remove link to list of dashboards
* aff10c1 HUE-5304 [libsolr] Add a remove collection API
* 532aa9e HUE-5304 [indexer] Protect against alias fetching failure
* 0f585a4 HUE-5304 [libsolr] Add propert default to the Solr API url
* 5e0b573 HUE-5304 [assist] List collections via the new API
* d4999d5 HUE-5304 [search] List all the Solr cloud collections
* f4e0d75 HUE-6575 [home] Convert all links to use the hueLink binding
* c9d5a24 HUE-6835 [autocomplete] Add suggestions for dropping range partitions and recovering partitions
* 17daf7e HUE-6835 [autocomplete] Add RANGE PARTITION suggestions to ALTER TABLE statements
* 519cbd8 HUE-6835 [autocomplete] Improve completion around ALTER TABLE
* 4b5a7e3 HUE-6836 [jb] Reset select all checkboxes on interface change
* dd6772c HUE-6837 [frontend] Fix alignment of hueCheckbox and hueCheckAll icons
* f11c1d7 HUE-6808 [editor] Open logs job links on the mini JB
* bc8566e HUE-6808 [frontend] Remove _blank targets
* 030baab HUE-6830 [editor] Introduce copy to clipboard for results
* be3ce02 HUE-6063 [frontend] Remove double class attribute from element
* edab02a HUE-6833 [editor] Disable query builder tab for non-sql editors
* a7aa436 HUE-6819 [oozie] Set generic widget for generic actions in oozie graph
* 2adc63c HUE-6814 [search] Only return distinct usernames in security impersonate dropdown
* f5af846 HUE-6825 [autocomplete] Prevent exception when there's no identifierChain given for a table
* 7f32c00 HUE-6829 [editor] Set download dialog overwrite default value to false to improve UX
* 46f3e10 HUE-6828 [editor] Fix vertical alignment of save query result file chooser button
* 51574d4 HUE-6827 [editor] Fix padding on download modal body
* 5b05335 HUE-6826 [oozie] Better slicing of action commands property
* 915bd3e HUE-6824 [fb] Fix possible JS error after permanently deleting files
* ad635bf HUE-6823 [frontend] Sending JS errors to the backend should be transparent and still show the stacktrace on the console
* 9dbe5ff HUE-6798 [frontend] Rename main action button depending on the selected app
* 00a3e3b HUE-6821 [frontend] Add tooltip to favorite component and fix ko binding for properties update
* 18fe998 HUE-6821 [home] Add star to favorite on Hue 4
* 3554285 HUE-6820 [frontend] Catch all the JS errors and send them to the backend
* d469cd3 HUE-6816 [frontend] Fix flexbox sizing of the popover sample tab on Safari
* 3a8dabb HUE-6817 [editor] Do a better column name match for the scroll to column functionality
* 5e8151e HUE-6812 [frontend] Swap sortable column style from top to bottom blue border
* 3be2254 HUE-6807 [search] The rolling time picker should consider the user's timezone
* 6c3a3b2 HUE-6807 [frontend] Fix global datepicker z-index
* a81e090 HUE-6807 [search] Fix undefined variable in the facet builder
* 2b0ee43 HUE-6813 [metastore] Fix database comment last character truncation
* 1cceb1d HUE-6811 [editor] Prevent displaying small black lines in the upper left corner on editor load
* aef9889 HUE-6810 [assist] Improve positioning and visibility of side panel toggles
* b363151 HUE-6809 [home] Set a min width for the name column in the document list
* 63a453a HUE-6803 [editor] Only refresh the assist for CREATE, DROP and ALTER statements
* 8c640d5 HUE-6803 [editor] Let the statement parser return the first non-comment token of the statement
* 4c0ca0c HUE-6806 [frontend] Avoid double init of Nicescroll on the context popover
* 26bb470 HUE-6802 [editor] Don't check for column existence in the location handler when a column is prefixed with a table name or alias
* 45ac70f HUE-6801 [frontend] Set a minimum height to the log resizer binding
* 554ab92 HUE-6800 [frontend] Re-word the welcome tour
* 3cdca5e HUE-6797 [dashboard] Grid widget operation icons are not grayed much
* 615237a HUE-6794 [assist] Only update the tables in the assistant when there's been a change
* b0e12ce PR553 [core] common_notebook_ko_components.mako does not import logging (#553)
* bdcf582 HUE-6795 [fb] Fix minor logic error in trash directory creation (#554)
* bf34aff HUE-6792 [core] Middle/right click is not working as a link on main blue action button
* c414c67 HUE-6791 [search] Protect against pivot facets conflicting with nested facets
* d5a29d7 HUE-6790 [assist] Improve the assist functions filter
* 00854cd HUE-6756 [home] Add a type filter to the home document browser
* a4090e9 HUE-6789 [beeswax] Fix alignment of the assist headers
* 612e410 HUE-6162 [core] Empty string value for hue_load_balancer config should not trigger warning
* 4d6b299 HUE-6786 [metastore] Fix ko editable binding after applying toggle overflow to the db description
* 3e4ff16 HUE-6787 [oozie] Hide calendar on modal close for any submit action
* 5f4f5f7 HUE-6786 [metastore] DB configuration list shouldn't overflow into table list
* 44b8451 HUE-6780 [aws] Fix tests for empty configurations
* 484fb77 HUE-6780 [s3] Correctly infer and display region when connected to S3 by endpoint
* 4ce8186 HUE-6760 [jb] Filtering running jobs and batch killing them do not update their status
* ec67867 HUE-6783 [home] Don't close the modals until all files marked for deletion are actually deleted
* 1494284 HUE-6779 [jb] Disable click around checkbox in list of jobs
* 0ca51b0 HUE-6781 [jb] Workflow duration time is not humanized
* 5af95a8 HUE-6776 [search] Js error when clicking on the first two layout of a new dashboard
* ce4122b HUE-6778 [frontend] Visual hint on click or d'n'd to import in Hue 4
* 543a619 HUE-6777 [fb] Drag & drop upload not enabled if editor was loaded before
* 1ce24a4 HUE-6773 [core] Clicks on Logs, Dump config with middle click are not supported
* 4d2739b HUE-6772 [navigator] Update tests to also reset the password cache
* b332599 HUE-6774 [metadata] Update to the most recent optimizer hostname
* a3ff301 HUE-6772 [optimizer] Cache Navigator password read from scripts
* a07be00 HUE-6772 [navigator] Cache Navigator password read from scripts
* 8b7eed1 HUE-6771 [metastore] The table description should have a fixed height in the table page
* 8bf756e HUE-6770 [metastore] Remove unused partitions mako page
* ff8ee9b HUE-6768 [frontend] Remove shown tooltips on app change in Hue 4
* ac34e4c HUE-6758 [jb] Open a workflow workspace breaks the history
* 3e23dc7 HUE-6738 [jb] Kill button of workflow enabled when clicking on re-run
* cf62c0e HUE-6767 [jb] Submit a workflow sometimes generates a JS error
* 4b06aa8 HUE-6757 [fb] Used to have a fixed action menu when scrolling down
* a8f3b45 HUE-6756 [home] Fix race condition when assist documents is open while visiting home with type parameter set
* 0009997 HUE-6756 [home] Apply the active document type for text search
* 6d86662 HUE-6762 [assist] Offer right click to open table in editor
* 1fb1e62 HUE-6759 [jb] Variable section of workflow is shown even if empty
* fa5f51d HUE-6737 [fb] Submit workflow.xml sends to Hue 3
* 3d65add HUE-6735 [jb] A suspended workflow should also be killable
* 4edc90c HUE-6749 [editor] From metastore to editor with past query ran and scrolled can garble grid
* 775f883 HUE-6748 [editor] Select and copy the query from the query history
* 3e92085 HUE-6745 [frontend] The title of the browser is Filebrowser even if I’m in editor
* fea73f3 HUE-6755 [assist] Add link to create a collection
* c30b09a HUE-6754 [assist] Add open in dashboard to collections
* e847d5e HUE-6710 [notebook] Allow listing of queries even if notebook is disabled
* c25cc00 HUE-6730 [fb] Use SkipFile instead of StopUpload in case of exception during file upload
* 9100dc1 HUE-6704 [fb] Return empty dictionnary for the page in case of empty page
* 1c76aa9 HUE-6704 [fb] Handle empty page error on filebrowser filter requests
* 92757f3 Revert "[HUE-6739] Collect stderr of subprocess command"
* 50ced50 HUE-6732 [jb] Add clearable to job filters
* ca40e6d HUE-6723 [jb] Provide duration time of running Yarn jobs
* 489f415 HUE-6722 [jb] Task progress shows as 1 and not 100%
* 0c424a5 HUE-6742 [editor] Incorrect Sorting With TIMESTAMP Column Type
* cd6b794 HUE-6724 [jb] Job progress can have too many decimals
* 780c7c0 HUE-6741 [assist] Make sure we fetch more entries if needed in foreachVisible when there's no initial overflow
* 1c12ea1 HUE-6740 [assist] Enable text filter for document type in the assist
* 162ca3f HUE-6728 [assist] Fix truncated input in the assist filter
* 2ecda3d [HUE-6739] Collect stderr of subprocess command
* 6c14289 HUE-6726 [jb] New jobs gets pushed to the end of the list of jobs
* ceeb16c HUE-6734 [jb] Protect from jobs with no available tasks to get some default logs
* a3f4c23 HUE-6713 [jb] Avoid printing empty log array on running MapReduce job
* 4b85142 HUE-6713 [jb] Color progress according to job status
* 99f5abe HUE-6713 [jb] Show correct status of YARN jobs and enable killing running jobs
* 3ff93a2 HUE-5765 [editor] Drop the check for optimizer when using the statement parser
* c29400e HUE-6716 [metadata] Disable when password cannot be read instead of crashing with a 500
* a175962 HUE-6714 [jb] No tasks found for job when refreshing MapReduce job page
* 6c71362 HUE-6720 [editor] Correctly reference static contents from within the web worker
* 92ffdf8 HUE-6719 [assist] Add a close button to the assist function panel
* 820b635 HUE-6157 [core] Set expected impala query cache rows in test based on configuration
* f61ee55 HUE-6157 [core] Fix banner and Impala query limit in live-cluster tests
* bcd1e2b HUE-6712 [metastore] Properly refresh tables and databases when creating/dropping
* ff4c729 HUE-6710 [notebook] Application reachable directly by users without granted access
* 3efae65 HUE-6708 [metadata] Mock clusterName call in the tests
* 0aa1652 HUE-6707 [search] Do not send search call when the collection name is null
* 6e727b5 HUE-3228 [dashboard] Support Kudu timestamps and drop bigint as date option
* fbccc53 HUE-6705 [fb] Opening directory after opening editor does not load at first click
* 9cd7d30 HUE-6709 [editor] Column list can jump back and forth depending on its size
* d191fe7 HUE-6711 [frontend] Render 403 page properly on Hue 4
* f72b61d HUE-6703 [search] Adding a new widget on the + targets errors
* 9c22dde HUE-6595 [fb] Opening a job might throw a 500 error if its tasks are None
* 639b3e2 HUE-6694 [aws] Gracefully handle bucket creation error for non-DNS compliant names
* 07575ff HUE-6702 [about] About page is accessible without authentication
* 2bc3113 HUE-6701 [editor] Prevent JS error on Ace resize
* 82711bc HUE-6701 [editor] Fix issue where the right panel resize bar gets hidden on window resize
* 03a3b07 HUE-6684 [editor] Refresh the ace scrollbars on side panel toggle
* 5e85a73 HUE-6684 [editor] Refresh the ace scrollbars on side panel resize
* c20a309 HUE-5765 [editor] Mark the correct error line when the statement parser is used
* bc380e7 HUE-6700 [editor] Use the correct huePubSub ID in the viewmodel
* 67b0403 HUE-6463 [oozie] Refresh coordinator or bundle job page after submittion
* e89e561 HUE-6698 [oozie] Add link from bundle browser to editor if available
* 119089d HUE-6698 [oozie] Add link from coordinator browser to editor if available
* 40bc2b0 HUE-6463 [oozie] Refresh job page after submittion to point to the correct job after more than one time
* cc28677 HUE-6682 [doc] Remove $ signs that prevent from copy pasting commands
* 9db5f8a HUE-6696 [aws] Display user friendly message when accessing non-DNS compliant bucket
* aab3c6d HUE-6695 [aws] Provide user-friendly message when accessing forbidden paths
* beceab6 HUE-6693 [home] Open up the page properly when using Hue 3
* 366f46f HUE-6692 [oozie] Remove history from editor as redundant
* e12a054 HUE-6691 [oozie] Support Pig parameters and files in drag and dropped Pig script
* 0150af0 HUE-6690 [oozie] Fix drag and drop of Pig script into workflow
* 271f612 HUE-6689 [pig] Fix the parameters in the examples
* 5bb5794 HUE-6694 [aws] Gracefully handle bucket creation error for non-DNS compliant names
* 6e894bb HUE-6682 [doc] Simplify the README to be friendler to users
* 53bbb98 HUE-6686 [jb] Re-run modal should close on the mini JB too
* d6d2592 HUE-6685 [jb] Stabilize arrow drawing on JB on Hue 4
* 5c34693 HUE-6687 [editor] Make sure we cache autocomplete responses for tables that don't exist


Contributors
------------

This Hue release is made possible thanks to the contribution from:

- Aaron Newton
- Aaron Peddle
- Aaron T. Myers
- Abraham Elmahrek
- Aditya Acharya
- Adrian Yavorskyy
- Alex (posi) Newman
- Alex Breshears
- Alex Newman
- Ambreen Kazi
- Amit Kabra
- Andrei Savu
- Andrew Bayer
- Andrew Yao
- Andy Braslavskiy
- Ann McCown
- Antonio Bellezza
- Ashu Pachauri
- Atupal
- Avindra Goolcharan
- Ben Bishop
- Ben Gooley
- Ben White
- Bhargava Kalathuru
- Bruce Mitchener
- Bruno Mahé
- Chris Conner
- Chris Stephens
- Christopher Conner
- Christopher McConnell
- Christopherwq Conner
- Craig Minihan
- Daehan Kim
- Derek Chen-Becker
- Diego Sevilla Ruiz
- Dominik Gehl
- Eli Collins
- Enrico Berti
- Erick Tryzelaar
- Ewan Higgs
- Gilad Wolff
- Guido Serra
- Harsh
- Harsh J
- Henry Robinson
- Igor Wiedler
- Ilkka Turunen
- Istvan
- Ivan Orlov
- Jack McCracken
- Jaguar Xiong
- Jakub Kukul
- Jarcek
- Jenny Kim
- Joe Crobak
- Joey Echeverria
- Johan Ahlen
- Johan Åhlén
- Jon Natkins
- Josh Walters
- Karissa McKelvey
- Kevin Wang
- Kostas Sakellis
- Lars Francke
- Li Jiahong
- Linden Hillenbrand
- Luca Natali
- Luke Carmichael
- Marcus McLaughlin
- Mariusz Strzelecki
- Mathias Rangel Wulff
- Matías Javier Rossi
- Michael Prim
- Michal Ferlinski
- Michalis Kongtongk
- Mobin Ranjbar
- Nicolas Fouché
- NikolayZhebet
- Olaf Flebbe
- Oren Mazor
- Pala M Muthaia Chettiar
- Patricia Sz
- Patrycja Szabłowska
- Paul Battaglia
- Paul McCaughtry
- Peter Slawski
- Philip Zeyliger
- Piotr Ackermann
- Prachi Poddar
- Prakash Ranade
- Prasad Mujumdar
- Qi Xiao
- Renxia Wang
- Rick Bernotas
- Ricky Saltzer
- Romain Rigaux
- Roman Shaposhnik
- Rui Pereira
- Sai Chirravuri
- Scott Kahler
- Sean Mackrory
- Shahab Tajik
- Shawn Van Ittersum
- Shrijeet
- Shrijeet Paliwal
- Shuo Diao
- Siddhartha Sahu
- Simon Beale
- Simon Whittaker
- Stefano Palazzo
- Stephanie Bodoff
- Suhas Satish
- TAKLON STEPHEN WU
- Tatsuo Kawasaki
- Thomas Aylott
- Thomas Poepping
- Tianjin Gu
- Todd Lipcon
- Tom Mulder
- Vadim Markovtsev
- Wang, Xiaozhe
- Weixia Xu
- William Bourque
- Word
- Xavier Morera
- Xhxiong
- Yixiao Lin
- Yoer
- Yuriy Hupalo
- Zach York
- Zachary York
- Zhihai Xu
- abec
- airokey
- alheio
- alphaskade
- antbell
- arahuja
- bc Wong
- bcwalrus
- bwang
- cconner
- cmconner156
- cwalet
- dbeech
- fatherfox
- gdgt
- grundprinzip
- happywind
- jeff.melching
- krish
- linchan-ms
- lvziling
- motta
- mrmrs
- oxpa
- pat white
- peddle
- rainysia
- raphi
- robrotheram
- shobull
- sky4star
- spaztic1215
- thinker0
- todaychi
- van Orlov
- vinithra
- voyageth
- vybs
- wilson
- xq262144
- ywheel
- z-york
