This repository contains binary standalone builds for tesseract_robotraconteur.

https://github.com/johnwason/tesseract_robotraconteur

All DLL files were extracted from ROS Windows. See individual source repositories for licenses.

This version of Tesseract does not use ros packages, and instead uses Robot Raconteur "buckets" to find resources. Buckets are essentially just directories, archives, or some other type of resource storage. Buckets are identified with a name and/or a UUID. Currently this version only works with directories and named buckets.

To specify the buckets, the environmental variable `ROBOTRACONTEUR_BUCKET_FILES` must point to a list of `bucket.yml` files. These `bucket.yml` files contain the names and directories of the buckets. An example `bucket.yml`:

    buckets:
      - name: sawyer_description
        directory: C:\rosws\src\sawyer_robot\sawyer_description
      - name: sawyer_moveit_config
        directory: C:\rosws\src\sawyer_moveit\sawyer_moveit_config
		
		
Command line options are:

Specify the URDF filename (Must be compiled if sources are xacro)

    --urdf-filename=<file>

Specify the SRDF filename (Must be compiled if sources are xacro)

    --srdf-filename=<file>
	
Specify the Robot Raconteur node name (optional, default "org.swri.tesseract")

    --robotraconteur-nodename=<node_name>
	
Specify the Robot Raconteur TCP port (option, default 63158)

    --robotraconteur-tcp-port=<port>
	
License: Apache 2.0