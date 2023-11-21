Container image is a binary package that encapsulate all of the files necessary to run a program inside of an OS container.
- The image isn't a single file but rather a specification for a manifest file that points to other files.
- Container images are constructed with a series of file system layers where each layer inherits and modifies the layers that came before it.

  -Container A: a base operating system only, such as Debian
    -Container B: built upon A, by adding Ruby v2.1.10
         -Container D: built upon B, by adding Rails v4.2.6
         -Container E: built upon B, by adding Rails v3.2.x
    -Container C: built upon A, by adding Golang v1.6

 - Containers fall into two main categories
	 - System Container: seek to mimic virtual machine and often run a full boot process. It has come to be seen as poor practice and Application Containers have gained favor.
	 - Application Container: differ from System Containers in that they commonly run a single program.