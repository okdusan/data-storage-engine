Write a program to store information as and when requested by API functions and read information as and when requested by QRY functions. 

Project structure:

	- ./api.c 
		- functions in these files api/qry can be imported by other programs and be called to store and read information efficiently
		- has below functions 
			- create(string tablename)
			- insert(string tablename, obj info)
			- update(string tablename, dbid id, obj info)
			- delete(string tablename, dbid id)
	- ./qry.c
		- has below functions
			- find()
			- project()
			- filter()
			- group()
	- ./core/database.c
		- core functionalities to support the above functions
		- define string -> char[n], dbid char[10], obj { keyval[] }, keyval {key:char[20], val char[20]}
		- serialize(){ convert obj to a plain text representation }
		- deserialize(){ reverse of serlz }
		- more core functionalities we will add here
	- ./data/db.txt
		- actual data will be stored in this file, program will automatically create this file if doesn't exist

