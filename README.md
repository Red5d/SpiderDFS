SpiderDFS
=========

This is a type of Distributed File System I've been experimenting with.

Dependencies: AuFS, sshfs (if you plan to use it)

=========

At the moment, the script that sets up and mounts the DFS (SpiderDFS) is written in Bash. I will probably eventually convert it to Python so I can add additional features and make it more like a normal FUSE filesystem.

This will connect to and mount the external (or local) filesystems defined in the config file and aggregate them into one folder (/media/DFS by default) with the AuFS layered filesystem. File writes will be done round-robin, so the first file you write to the DFS will transparently be saved to the first defined DFS source, the second written file will go to the second DFS source, etc.

The dfsconfig.example file shows the config format for defining filesystems to add to the DFS. The name of the config file to use (/media/.dfsconfig by default) can be set in the SpiderDFS script.
