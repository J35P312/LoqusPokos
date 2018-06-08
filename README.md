# LoqusPokos
Singularity image for loqusdb. The image contains the SV branch of loqusdb and mongodb.

# Usage:
Download the container:

	 singularity pull shub://J35P312/LoqusPokos

you may run mongodb through the singularity container:

	mkdir dbfolder
	singularity exec loqusdb.img mongod --dbpath dbfolder > /dev/null 2>&1 & 

You can create separate fodlers to launch multiple databases.

Running LoqusDB:
	
	singularity exec loqusdb.img loqusdb

Visit  the loqusdb website for more  information

	https://github.com/moonso/loqusdb/tree/add-sv

