This week covers:

  * An intro to Git and Github for sharing code
  * Command line tools
  * Exploratory data analysis with R

# Setup

Install git, R, and RStudio:

  * Install git: ``sudo apt-get install git``
  * In the terminal, type ``sudo gedit``
  * Create a new document containing a [CRAN mirror](http://cran.r-project.org/mirrors.html): ``deb http://lib.stat.cmu.edu/R/CRAN/bin/linux/ubuntu trusty/``
  * Save it as ``/etc/apt/sources.list.d/cran.list`` and close gedit
  * In the terminal, type ``sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 51716619E084DAB9`` to authorize a server with the latest R packages
  * Then ``sudo apt-get update`` to update the package list
  * Install R with  ``sudo apt-get install r-base``
  * Download the [latest RStudio .deb](http://www.rstudio.com/products/rstudio/download/) package: ``wget http://download1.rstudio.org/rstudio-0.99.442-amd64.deb``
  * Install a dependency for RStudio: ``sudo apt-get install libjpeg62``
  * Install the package: ``sudo dpkg -i rstudio-0.99.442-amd64.deb``
  * Start RStudio, either with ``rstudio`` from the command line or through the Ubuntu launcher
  * Follow Rstudio's [initial set up](http://r-pkgs.had.co.nz/git.html#git-init) to create an RSA key and upload the public portion to Github

# Intro to Git(Hub)

## Your first pull request
  * [Sign up](https://github.com/join) for a free GitHub account
  * Then [fork your own copy](https://guides.github.com/activities/forking/) of the course repository
  * See these [screenshots](http://www.princeton.edu/~mjs3/soc504_s2015/submitting_homework.shtml) for details, with one modification: use the *ssh clone URL* in the repository URL field, which should read ``git@github.com:yourusername/ds3-2015.git``
  * Once that's done, edit the ``week1/students.txt`` file and add your first name
  * Commit and push your changes to your copy of the repository through RStudio
  * Then issue a [pull request](https://guides.github.com/activities/forking/#making-a-pull-request) to send the changes back to the original repository
  * Finally, [configure a remote repository](https://help.github.com/articles/configuring-a-remote-for-a-fork/) called ``upstream`` to point here: ``git remote add upstream git@github.com:jhofman/ds3-2015``
  * This will allow you to [sync future changes](https://help.github.com/articles/syncing-a-fork/) to your fork by issuing ``get fetch upstream`` followed by ``git merge upstream/master``

## Learn more
  * Complete this [free online git course](https://try.github.io) and watch this [introductory video](https://www.youtube.com/watch?v=U8GBXvdmHT4)
  * More resources are available [here](https://help.github.com/articles/good-resources-for-learning-git-and-github/)
  * And here's a handy [cheatsheet](https://training.github.com/kit/downloads/github-git-cheat-sheet.pdf)

# Command line

  * Review [intro.sh](week1/shell/intro.sh) for an introduction to the command line
  * Download one month of the Citibike data: ``wget https://s3.amazonaws.com/tripdata/201402-citibike-tripdata.zip``
  * Decompress it: ``unzip 201402-citibike-tripdata.zip``
  * Rename the resulting file to get rid of ugly spaces: ``mv 2014-02*.csv 201402-citibike-tripdata.csv``
  * Go through the one-liners in the [explore_trips.sh](week1/citibike/explore_trips.sh) file
  * Fill in solutions of your own under each comment in [exercises.sh](week1/citibike/exercises.sh)