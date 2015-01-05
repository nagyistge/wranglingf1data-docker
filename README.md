wranglingf1data-docker
======================

Dockerfile for virtual machine to support Wrangling F1 Data projects.

This project will configure a virtual machine with a variety of tools to support the  [Wrangling F1 Data With R](https://leanpub.com/wranglingf1datawithr/) book.

The virtual machine contains:

* R/RStudio
* some helper R routines (eg for accessing the ergast API)
* some example datafiles

Once you have started the container, you should be able to see RStudio in your browser.

## Installation

In order to create the virtual machine, you should:

* install [boot2docker](http://boot2docker.io/)
* run *boot2docker*
* in the *boot2docker* terminal, enter the command `docker run -d -p 8787:8787 --name f1dj psychemedia/wranglingf1data`
	* the *port number* you will be able to find RStudio on is given by the first number set in the flag *-p NNNN:8787*. To access RStudio via port 8800, use  *-p 8800:8787* etc.
* in the  *boot2docker* terminal, enter the command `boot2docker ip`
	* the returned IP address (eg *192.168.59.103*) is the IP address you can find RStudio on
* point your browser to the appropriate IP address and port combination, for example: *http://192.168.59.103:8787*
* login to RStudio with username *rstudio* and password *rstudio*
* *on the first run*, create a new project: ![RStudio - open new project](https://farm8.staticflickr.com/7547/16017885150_b38d0d338f_o.png)

* use the folder *wranglingf1data* as the existing project directory

When you have finished working in RStudio, save the project and then stop the container it is running in from the *boot2docker* command line with the command `docker stop f1dj`

Any work you have been doing in RStudio, and any files you have saved within the container, will be retained within the container.

To restart the container, from the *boot2docker* command line, use the command `docker start f1dj`.

	
