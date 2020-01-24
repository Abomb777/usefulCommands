#Install python 3.6 on centos 7 

```sh
yum install zlib-devel
```
Step 1: Install the development tools needed for compilation.
First, we will need the tools in order to be able to compile and install programs from their source code. To do this, we will install the 

group “Development Tools” through Yum itself:
```sh
sudo yum groupinstall -y "Development Tools"
```

Once this is done, move on to step 2.

Step 2: Download the Python source files.
First, we need to create a directory in which our install will take place. Make a directory with a name of your choosing, then enter the directory. Once you are in your new directory, enter the following command to download the compressed Python source file.
```sh
wget https://www.python.org/ftp/python/3.6.4/Python-3.6.4.tar.xz
```

Once the file is finished downloading, uncompress the file by using tar, then enter into the new directory that was just created:
```sh
tar -xJf Python-3.6.4.tar.xz
cd Python-3.6.4
```

Step 3: Run the configuration script.
Use the following command to have the installation software check your system before actually starting the installation process.
```sh
./configure
```

This command ensures that the install will work, along with creating a special ‘makefile’ that is unique to your system. This makefile is what you will use to install Python onto your system.

Step 4: Install Python.
Now we can finally execute the makefile. Run the following command to install Python onto your system. Note: This will take a few minutes. The speed of the compilation and install will depend on the speed of your processor.

First, we run the ‘make’ command which compiles the program.
```sh
make
```

Then, once that is finished, we can run the installation command.
```sh
make install
```

```sh
python3.6
```
