# Kingdom-Splitter

Description coming soon!

## License
This program is licensed under the GNU Lesser General Public License.
See License.txt for more information.

## Prerequisites
In order to install this gem you need to have several programs
installed:

 * Ruby either in version 1.8.7 or 1.9.2. The use of [JRuby](http://www.jruby.org/) (a Java implementation of Ruby) is recommended.
 * Git
 * cURL
 
In the following, the installation procedure is given for **Mac OS X** and **Ubuntu Linux 10.10**. The commands for Ubuntu also have been tested to work for **Debian Squeeze** although you should substitute apt-get by aptitude.

If you already installed Kingdom-Assignment, you can jump right to the section "Using Kingdom-Splitter"

### Installing Git
An installer for Mac OS X can be obtained from the [official website](http://git-scm.com/). For any Linux distribution it is recommended that you use your system's package manager to install Git. Look for a package called git or git-core. For Ubuntu 10.10 the command is:

    sudo apt-get install git
    
### Installing cURL
Mac OS X comes with curl by default, on a Linux system, cURL can be obtained via the system's package manager. For Ubuntu 10.10 the command is:

    sudo apt-get install curl
    
### Installing JRuby
Very few distributions offer packages for the most recent version of JRuby.
The easiest way to install the most recent version of JRuby is via the [Ruby Version Manager](http://rvm.beginrescueend.com/) by Wayne E. Seguin.

Before you install RVM, make sure you have git and curl installed on your system.

RVM can be installed by calling:

    bash < <( curl http://rvm.beginrescueend.com/releases/rvm-install-head )

This will install RVM to .rvm in your home folder and print several instructions specific to your platform on how to finish the installation. Please pay close attention to the "dependencies" section and look for the part where it says something like this:

    # For Ruby (MRI & ree)  you should install the following OS dependencies:
    ruby: /usr/bin/apt-get install build-essential bison openssl libreadline6 libreadline6-dev curl git-core zlib1g zlib1g-dev libssl-dev libyaml-dev libsqlite3-0 libsqlite3-dev sqlite3 libxml2-dev libxslt-dev autoconf libc6-dev ncurses-dev

These are the requirements for building the normal C version of Ruby. However, many of those tools are also required for building the Java version of Ruby so it is advisable that you install all of these prerequisites. Please do not copy the commands from this file, look at the output of the RVM installer.

    sudo apt-get install build-essential bison openssl libreadline6 libreadline6-dev curl git-core zlib1g zlib1g-dev libssl-dev libyaml-dev libsqlite3-0 libsqlite3-dev sqlite3 libxml2-dev libxslt-dev autoconf libc6-dev ncurses-dev

If installing any of these packages gives you an error, consider updating your packages by using your system's update manager.

Next you need to install the tools that are specifically required for installing JRuby. The output of RVM might look like this:

    # For JRuby (if you wish to use it) you will need:
      jruby: /usr/bin/apt-get install curl g++ openjdk-6-jre-headless
      jruby-head: /usr/bin/apt-get install ant openjdk-6-jdk

It is recommended that you use the latest stable version of JRuby, not jruby-head. Accordingly, on Ubuntu 10.10 you have to install the following packages in order to use JRuby with RVM:

    apt-get install curl g++ openjdk-6-jre-headless
    
Next, you have to make sure that RVM is loaded when you start a new shell. Look for the part where it says: "You m

## Installing Kingdom-Splitter
This gem is distributed in source form for the time being, so you must build it yourself in order to use it. Don't worry, it's not hard:

First you must download the source code of this gem by going to a folder of your choice and typing:

    git clone git@github.com:PalMuc/Kingdom-Splitter.git

This will will clone a copy of this repository in a folder named Kingdom-Assignment. Go to this folder by typing:

    cd Kingdom-Splitter

Kingdom assignment is delivered as a Ruby gem. In order to build and install it, you first have to install another gem called bundler. Type:

    rvm jruby gem install bundler

In order to install the other gems Kingdom Assignment depends on, first switch to JRuby:
    
    rvm use jruby

Now go to the folder called kingdom-assignment and type:

    bundle install

Before you build an updated version of Kingdom Assignment, you should
delete previous builds by typing:

    rm pkg/kingdom-splitter-*.gem

After that, create a new Ruby gem by typing:

    rake install
    
Finally you can install the gem by typing:

    rvm jruby gem install pkg/kingdom-splitter*.gem
    
Kingdom Assignment is now in your global path, meaning that from any point in the system you can use it by typing

    kingdom-splitter
    
on the command line. Please note that in order to do that you have to switch to JRuby as mentioned before.

## Using Kingdom-Splitter

    kingdom-splitter input.csv"

This will automatically create input\_clean.csv and input\_contaminated.csv in the same directory.

# Acknowledgements
Development of this program was supported by the [Molecular Geo- and Palaeobiology Lab](http://www.mol-palaeo.de/) of the Department of Earth and Environmental Sciences and the initiative "[Gleichstellung in Forschung und Lehre](http://www.frauenbeauftragte.uni-muenchen.de/foerdermoegl/lmu1/tg73/index.html)" of the Ludwig-Maximilians-University Munich (LMU).
