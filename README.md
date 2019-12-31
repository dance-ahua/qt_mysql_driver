Since the Qt Company currently doesn't give a crap on providing qsqlmysql.dll in binary form, you have to build it on your own. Here is a build for Qt 5.12.3 / 5.13.1 / 5.14.0 for MSVC 2017 64-Bit and MinGW-w64 7.3. Download precompiled qsqlmysql.dll from https://github.com/thecodemonkey86/qt_mysql_driver/releases

Deployment

1) in application subdirectory "sqldrivers" qsqlmysql.dll (Release) / qsqlmysqld.dll (Debug)
2) the MySQL library itself libmysql.dll

 
Building hints
- See branches by Qt version for source code
- Make sure you link against the official MySQL C Connector v6.1 (not C++): https://downloads.mysql.com/archives/c-c/?version=6.1.2&amp;os=src
- The .pro file from this repository by default expects the contents of the zip file from mysql.com to be in the same base directory as the sql driver project
	e.g. D:\qt\src\sqldrivers is the sql driver project dir and D:\qt\src\mysql-connector-c-6.1.2-win32 is the MySQL connector library directory, so that there are D:\qt\src\mysql-connector-c-6.1.2-win32\include and \lib subdirs
