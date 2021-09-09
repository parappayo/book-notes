
# About

* [A Curious Moon](https://www.bigmachine.io/products/a-curious-moon)
* by Rob Conery
* published by Big Machine, 2017

# Thoughts

Fun book, littered with helpful Postgres advice.

# Take-Aways

* Data is gold, the real value of a business
* Humans are not naturally equipped to be custodians of data; they are messy and work off of intuition; where humans are allowed to touch data, they corrupt data; information is power; do not manually fill in data gaps, let the data tell the story
* Database work tends toward high stakes compared to front-end or other domains; on the one hand you could gain a massive efficiency improvement with a well-placed index, on the other you could destroy the business by dropping a schema
* Data generated by applications needs to anticipate the questions that the business will have
* Import everything as text first, then impose types and constraints
* Use shell scripts with Makefiles until the complexity slows you down; capture the import, ETL, export process as a Makefile / script to make it reproducible
* Prefer text columns to varchar
* We trust you, but don't screw up

# Concepts

* `${CURDIR}` - Make variable, the working directory
* `::` - SQL cast operator, or just use `cast as`
* `@>` operator - used to check if a value is in a range, does not work with BTREE index
* `@@` operator - does tsvector match tsquery; use with to_tsquery; [see docs](https://www.postgresql.org/docs/current/functions-textsearch.html)
* `\x` - psql expanded view, useful for browsing larger records
* `drop if exists` - best practice to use this with create statements, avoids peppering the monitoring system with trivial errors
* `ilike` - case insensitive like
* `request.body` - is full of leeches and vomit
* `~` - POSIX regex match, use `~*` for case insensitive, `!~` to not match, etc.
* ACID - Atomic, Consistent, Isolated, Durable
* Analyst versus DBA - what the data is versus how well the data lives
* Arrange, Act, Assert - pattern for writing unit tests
* BTREE Index - Balanced Tree
* Common Table Expression (CTE) - SQL feature to pipe results from one query into the next query; `with..as` clauses that reference each other
* concurrently keyword - hint to employ parallelism; typically requires an enterprise license, but not with Postgres
* Cross Join - the cartesian product of two tables
* Daltons - Atomic Mass Units per charge; AMU/Z
* Database Heirarchy - cluster -> database -> schema -> table
* Date Types - common pain point; NASA date format is year-dayofyear; Postgres stores all dates as UTC, converting them at query time
* Dust Archive - NASA data
* Egregore - autonomous psychic group mind
* Enceladus - icy moon of Saturn, most reflective body in the solar system, discovered in 1789 by William Herschel, about the size of Great Britain
* explain - use to get a query plan
* Forty-Niners - 1849 gold rush
* Full-Text Indexing - `to_tsvector()` on text, `'text' @@ to_tsquery()` to search; consider concating text fields together (eg. title and description) to create a search vector; see [textsearch controls docs](https://www.postgresql.org/docs/current/textsearch-controls.html)
* Galapagos - 1977 deep sea trench survey near Galapagos found life living off of heat from hydrothermal vents and toxic chemicals; does not depend on sun's energy
* Generalized Inverted Index (GIN) - Postgres feature, [see doc](https://www.postgresql.org/docs/9.5/gin-intro.html)
* GIST Index - respects ranges
* idempotent script - if you run it more than once, you still get the same result
* Indexes vs Joins - indexing a column (eg. timestamp) to join on can be better than creating a junction table (consumes more disk space, one more step to worry about)
* International Astronomical Union (IAU) - source of much oblique terminology; produced the Enceladus Nomenclature report
* Julian date - used by some astronomical tools; big numbers starting with 2
* Junction Table - many-to-many join; relates two unrelated tables; primary key is a tuple of foreign keys from the tables, enforcing uniqueness is important
* Leap Years - Excel considers 1900 to be a leap year (it isn't) for compatibility with Lotus 1-2-3; famous outages caused by incorrect leap year calculations include Microsoft Azure in 2012, Zune in 2008
* Lightning Whistler - very low frequency radio signal generated by lightning
* M. Sullivan - we see in M. Sullivan who we need when we need them
* Marine Snow - organic matter that falls to the ocean depths from the surface, feeding life there
* Mars Climate Orbiter - crashed
* Materialized View - persisted view as a table, needs a command to refresh
* Mathieu Differential Equation
* Methanogenesis - deep sea microbes convert H2 and CO2 into CH4 and H2O
* Multi-Version Concurrency Control - Postgres uses this to avoid read locks where possible; transactions are performed in virtual memory and committed in one consecutive operation
* Nadir - the lowest point
* Niantic - whaling vessel abandoned as part of the San Francisco gold rush
* Occultation - celestial bodies aligned, starlight can be used to look for evidence of atmosphere or plumes; stellar occultation when a star passes behind a moon or planet
* Origin of Life Reactor
* Pappy Van Winkle - bourbon
* Pattern Matching - [Postgres docs](https://www.postgresql.org/docs/9.3/functions-matching.html)
* PDS - Planetary Data Systems, NASA
* PK - primary key; don't create a table without a PK, even "just for the lulz"
* Push-Pull - the more work management gives you, the harder they make it for you to complete that work
* Quadrupole - four parallel metal rods, part of the INMS
* Ranges - tsrange keyword, supported closed `[]` and open `()` ranges; [see docs](https://wiki.postgresql.org/images/7/73/Range-types-pgopen-2012.pdf)
* Sargeable Query - Search ARGugment ABLE, query optimizer can take advantage of an index; non-sargeable is commonly caused by `where bar like '%foo'` (wildcard at start of search pattern) or `where func(* foo) = bar` (if possible, invert this as `where foo = inverse(bar)`)
* Serial Primary Key - convenience feature provided by Postgres; ANSI SQL would require separate `create sequence` statements with `set default nextval(sequence_name)` on the column
* SPASS - Science Planning Attitude Spreadsheet
* Spreading Ridges, Subduction Zones - tectonically active areas
* Star Schema - one fact table (measures) joined to by multiple lookup tables (dimensions)
* Sulcus - subparallel furrow or ridge; the "tiger stripes" on Enceladus are named Damascus, Baghdad, Cairo, and Alexandria and are the source of the plumes
* TechEd - SAP Conference
* The Master Schedule - table of every command sent to Cassini
* View - can specify commonly used joins to pretend that data is denormalized; `drop if exists` followed by `create view` script makes it easy to tweak; cannot create an index on a view, but can index a materialized view
* Window Functions - like an aggregate without a group-by; eg. `count(1) over (partition by my_table.category)` counts rows along with the category values; the partition can be empty, eg. `count(1) over ()` for a total

# Techs

* Amazon Snowball
* Apache Kafka - for when your ETL out-grows Python homebrew
* Cognito - AWS identity service
* Compose - IBM cloud data hosting
* Compose Infrared Spectrometer (CIRS) - FP3 is the mid-range focal plane, used to detect volcanism
* Cosmic Dust Analyzer (CDA)
* CSV data - typically unsanitary (invalid values, incomplete rows)
* csvkit - cli tools for working with csv
* csvsql - generate create table sql from csv, beware the column types though
* cut - bash command to extract part of each input line
* Google BigTable
* High Rate Detector (HRD)
* Imaging Science Subsystem (ISS)
* Impact Ionization Detector (IID)
* Ion and Neutral Mass Spectrometer (INMS)
* JSONB - Postgres binary json format, ridiculously fast
* Magnetometer (MAG)
* Marten - .NET lib by Jeremy Miller that provides a document store API using Postgres as a back-end
* MassiveJS - data access tool that mimics MongoDB
* Moebius - clone of MassiveJS for Elixir
* MongoDB BI Connector - uses Postgres
* Navicat
* Pandas
* PETL - Python ETL
* pg_docs_api - Postgres functions that provide document store functionality
* pg_dumpall
* PL/pgSQL  - Postgres lang
* PL/Python - Postgres SQL functions can be written in Python, Ruby, R, Perl, other langs
* plv8 - JavaScript V8 as a Postgres extension
* Postgres - might as well call it Postgres, not PostgreSQL; doesn't lend itself to trivial idiocy; works fine as a document db, see JSONB
* Postico
* psql - GUIs slow you down; "Every person has their own favourite way of working with data. Most of them that aren't plsql are horrible."
* Radio and Plasma Wave Science (RPWS)
* Radio Science Subsystem (RSS)
* SELFI - Submillimeter Enceladus Life Fundamentals Instrument
* SQLAlchemy
* SQLPro
* TAB files - another name for TSV
* Visible and Infrared Mass Spectrometer (VIMS)

# Names Dropped

* Dee Yan - author of the fictional Red:4 journal
* Red:4 - fictional aerospace start-up

# Publications

* [Postgres Docs](https://www.postgresql.org/docs/)
* The Hyperion Cantos - Dan Simmons book series
* The Martian - novel

# Code

* `COPY schema.table_name FROM file_path WITH DELIMITER ',' HEADER CSV;`
* `select my_col::timestampz from my_table;` -- test whether column is all valid dates
* `select '2001-01-01'timestampz;` -- can see the conversion to local timezone
* `select … at timezone 'UTC'` -- force a particular timezone
* `drop table if exists my_table cascade;` -- will also drop foreign_key references
* `psql \H \o <filename>` # outputs to file as an html table
* `cat ./**/*.csv >combined.csv` # will include all header rows, though