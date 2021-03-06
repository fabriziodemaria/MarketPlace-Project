# Marketplace (RMI and JPA)

NOTE: to run this project on NetBeans you need to creade a proper Java DB as indicated in the "persistance" file.

##PROJECT SPECIFICATIONS

A RMI-based file catalog with a database.
Develop a client-server distributed application in Java that allows storing, retrieving and removing files to/from a file catalog that serves as a backup storage.  Clients and a server communicate via RMI (Java RMI or Java IDL). A client is controlled by a user and provides a (G)UI for the user. A server represents a file catalog and provides a remote interface that allows clients to perform the actions listed below. The server uses a database to keep track of users and files at the catalog as described below. The files in the catalog are stored on the server's file system under a special directory on the server site. The server remote interface allows clients to perform the following actions:
To (un)register at the catalog, and to login (logout) with a user name and password. To be allowed to upload/download files on the file catalog, a user must be registered at the file catalog and login to the file catalog with a username and a password. The user can specify the username and the password when s/he registers at the file catalog server; the user provides the username and the password when s/he logs on to the server.
On registration, the server should verify whether the name and the password specified by the user fulfill the following requirements: the name should be unique and the password length should be at least 8 characters. If the username or/and the password do not fulfill the requirements, the user is asked to provide another username or/and password.
When the user logs on to the server, the server verifies the username and the password, and allows the user to continue as appropriate.
The server maintains a table in its database to keep records on each user  (user name, password and activity indicator). 
To upload (store) user's local file to the catalog; and to download (retrieve) files from the catalog to the user's local file system. A file at the catalog is identified by its name, and has the following attributes: name; size; owner; public/private access permission that indicates whether it's a public or private file; last-modified time; write and read permissions for the public file. Private files can be retrieved, deleted or updated only their owners. Public files can be accessed by any user registered at the file catalog. The write and read permissions for a public file indicates whether the file is read-only (write permission is false) for any user or it can be modified, i.e. deleted or updated,  by any user (write permission is true). The owner has all permissions for his/her files.
To inspect what files are available in the file catalog, i.e. list the files at the catalog. Note that if a file is marked as private, it can be listed only for its owner.
The server uses a database to keep records on each user  (user name, password and activity indicator) and on each file at the catalog (name, size, owner, public/private access permission, last-modified time, write/read permissions). The user's activity indicator shows the total number of files uploaded by the user, and the total number of files downloaded by the user.

The database is implemented using Java Persistence API.
