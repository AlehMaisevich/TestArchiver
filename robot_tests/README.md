# Basic usage with Robot Framework

## With output parser

The robot output.xml files can be imported using `testarchiver`.

```
testarchiver --format robot --database test_archive.db output.xml
```
This should create a SQLite database file named `test_archive.db` that contains the results.

See main README.md for more details.

## With Robot listener

The project includes a listener that allows archiving the results using Robot Frameworks [Listener interface](https://robotframework.org/robotframework/latest/RobotFrameworkUserGuide.html#listener-interface)

```
robot --listener test_archiver.ArchiverRobotListener:test_archive.db:sqlite3 my_tests.robot
```

This should create a SQLite database file named `test_archive.db` that contains the results.

Arguments for ArchiverRobotListener:
`test_archiver.ArchiverRobotListener:DBNAME_OR_CONFIG:DBNEGINE[:DBUSER[:DBPASSWORD[:DBHOST:[DBPORT]]]]`

## Fixture tests

The tests in this folder are simple ones demonstrating some features of Robot Framework. They can be used to generate data for TestArchiver.

### Usage

With windows, run `run.bat` from command line.

```
-n should-fail
```

Tells the Robot to pass suites even tests fail with tag "should-fail".

```
--pythonpath ./libraries:./resources
```

Tells where Robot can find needed files for some tests.
