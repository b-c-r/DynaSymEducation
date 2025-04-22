Installation and Setup of R, RStudio and Git and how to connect all to
GitHub
================
2025-04-22

# Install R

You can install R by downloading the installer from the Comprehensive R
Archive Network or by including it into your software management system
(e.g. in Linux). Please follow the instructions on the following pages:

- Windows: <https://cran.r-project.org/bin/windows/> or
  <https://cran.r-project.org/bin/windows/base/> directly
- Mac: <https://cran.r-project.org/bin/macosx/>
- Linux:
  - Ubuntu:
    <https://cran.r-project.org/bin/linux/ubuntu/fullREADME.html> (you
    should start here:
    <https://cran.r-project.org/bin/linux/ubuntu/fullREADME.html#secure-apt>)
  - Debian: <https://cran.r-project.org/bin/linux/debian/>
  - Find information on Fedora/Suse/Redhat here:
    <https://cran.r-project.org/bin/linux/>
- Further reading:
  - <https://rstudio-education.github.io/hopr/starting.html>

# Install RStudio

RStudio is an integrated development interface (IDE) for the statistics
programming language “R”. You can download RStudio form the companies
homepage for free. You should use the desktop version
(<https://posit.co/download/rstudio-desktop/>) that fits your operating
system (e.g. Windows 11).

- Further reading:
  - <https://rstudio-education.github.io/hopr/starting.html>

# Install Git

Git is a version control software that was developed to track the
evolution of a software project over time and across many co-workers.
Please follow the installation guides:

- Windows (<https://git-scm.com/downloads/win>)

- Mac (<https://git-scm.com/downloads/mac>)

- Linux (<https://git-scm.com/downloads/linux>)

- Full Guide:
  <https://git-scm.com/book/en/v2/Getting-Started-Installing-Git>

- Alternative: <https://github.com/git-guides/install-git>

- Specific for R-Users: <https://happygitwithr.com/install-git>

# Register on GitHub / GitLab

To make full use of Git, you should also have a remote server to save
your project data on. You could either work on a self-hosted GitLab
server (e.g. from your university like
<https://uol.de/itdienste/services/datenhaltung/gitlab> or
<https://www.uni-potsdam.de/de/elis/technische-entwicklung/gitup>), or a
commercial service like GitHub (<https://github.com/>).

In DynaSym we already use GitHub for creating an R package
([dynafit](https://github.com/b-c-r/dynafit)) and to distribute
educational material (<https://github.com/b-c-r/DynaSymEducation>).
Moreover, many R packages are distributed via GitHub within their
development phase (e.g. <https://github.com/mrc-ide/odin>).

Basic GitHub accounts are for free, and you can register here:
<https://github.com/signup>.

Further reading:

- <https://docs.github.com/en/get-started/start-your-journey/creating-an-account-on-github>

- <https://happygitwithr.com/github-acct>

# Setup RStudio and R

After installing, there is basically not much to do. You can open
RStudio, and it will automatically detect your R installation. For our
workshop, however, we need more than the basic R installation. As R is a
free and open-source software
([FOSS](https://en.wikipedia.org/wiki/Free_and_open-source_software)), a
large community of developers contributed very specific R packages that
complement the basic installation of R, you can find a list of these
packages in [CRAN](https://cran.r-project.org/), but also packages on
[Bioconductor](https://www.bioconductor.org/) or on
e.g. [GitHub](https://github.com/).

RStudio has for window panes
(<https://docs.posit.co/ide/user/ide/guide/ui/ui-panes.html>), the
default setting is:

- upper left: **source file(s)**.

- upper right: **environment** (all the objects you’re using currently),
  and other tabs, including a Git tab (if you are using Git in your
  current project).

- lower left: the **console**, here you’re interacting with R!

- lower right: more information, including your file system, installed
  packages, displaying help files, displaying graphical outputs, and
  others.

For our workshop we need more than the base R installation. To install
new packages, you can type use one of the following methods:

1.  typing `install.packages("packageName")` into the console
    (e.g. <https://bookdown.org/nana/intror/install-and-load-packages.html>).

2.  move to the lower-right pane and open the tap “packages”, click on
    “Install” and search for your package (and install it, of course
    ;-)).

## Required packages

- `bbmle`
- `bookdown`
- `devtools` (Windows user may require
  [RTools](https://cran.r-project.org/bin/windows/Rtools/), but I am not
  sure)
- `doParallel`
- `dplyr`
- `emdbook`
- `foreach`
- `here`
- `kableExtra`
- `knitr`
- `odin`
- `pak`
- `tinytex` (for creating PDF reports via LaTeX, not required if you are
  using other LaTeX distributions)
  - Please follow the instructions on <https://yihui.org/tinytex/>.

Some additional packages that we possibly need:

- `frair`
- `lhs`
- `MASS`
- `png`
- `purrr`
- `RCurl`
- `sessioninfo`
- `supportR`

# Setup Git

Before you use Git, you have to run two commands letting Git know who
you are, and what email address you are using. This is important as it
will identify you with changes you do to your (or a shared) project. For
example, here is the (commit) history of this project:
<https://github.com/b-c-r/DynaSymEducation/commits/main/>.

First, open a terminal/console/shell (your command line tool) of your
operating system. Then, you should run the following commands:

- `git config --global user.name "John Doe"` e.g. your GitHub nickname

- `git config --global user.email johndoe@example.com` best it would be
  to use your GitHub email address (but find
  [here](https://docs.github.com/en/account-and-profile/setting-up-and-managing-your-personal-account-on-github/managing-email-preferences/setting-your-commit-email-address)
  how to use anonymous mail addresses in GitHub)

- Find here an R specific view: <https://happygitwithr.com/hello-git>

- And here about what is a shell: <https://happygitwithr.com/shell>

# Connect GitHub with your local Git and RStudio

Next, you need to assure that your local computer can communicate with
GitHub (or GitLab). We will only briefly cover this topic in the online
sessions of the workshop:

## HTTPS vs. SSH

The two main ways to connect your local computer with GitHub is either
via a HTTPS protocol or via a ssh protocol. As I am not a computer
scientist, I can’t tell you anything about the technical background and
will focus on some practical advises I found online and experienced
using both methods.

Connecting your computer via ***HTTPS is the recommended method for all
starters*** (see <https://happygitwithr.com/https-pat#https-vs-ssh> and
<https://www.geeksforgeeks.org/how-to-use-https-or-ssh-for-git/>).
However, there are also benefits of using the SSH connection including
speed and security. Moreover, while for Windows and Mac users, all
credentials and passwords can be easily saved by the OS, you normally
have to retype them all the time when you are a Linux user. You should
read the articles on HTTPS and SSH and their setup before you decide.

## Setup HTTPS

Please follow the instructions you find here:

- <https://happygitwithr.com/https-pat>

## Setup SSH

1.  Create a SSH key on your system, e.g. via RStudio:

    1.  Choose “Tools -\> Global Options” from the pull-down menu

    2.  Open the “Git/SVN” tab and click on create SSH key

    3.  You can/should secure this key with a password (you should use a
        password manager for it!!!)

2.  Add the key to the SSH agent of your system:

    1.  Open the terminal (see also above)

    2.  Type the commands for your operating systems (see link below)

    3.  <https://happygitwithr.com/ssh-keys#add-key-to-ssh-agent>

    4.  You need to enter you key-password!

3.  Give GitHub your public key

    1.  Got to GitHub in your browser

    2.  Move to Settings (at your profile pic) -\> SSH and GPG Keys

    3.  Copy the public key from RStudio (pull down menu “Tools-\>Global
        Options-\>Git/SVN-\>Show Public Key”)

    4.  Create a new authentication key (give it a name you can
        remember, like “SSH key for University Desktop”)

4.  Test connection

    1.  Open the Terminal (or Git Bash on Windows)

    2.  Type in the commands you find here:

    3.  <https://docs.github.com/en/authentication/connecting-to-github-with-ssh/testing-your-ssh-connection?>
        (note that this is also OS specific)

    4.  The so-called “fingerprint” that will be displayed is not the
        fingerprint of your specific SSH key, but a GitHub SSH key
        fingerprint.

    5.  As RStudio will create a `Ed25519` key, the fingerprint should
        be: `SHA256:+DiY3wvvV6TuJJhbpZisF/zLDA0zPMSvHdkr4UvCOqU`
        (<https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/githubs-ssh-key-fingerprints>)

Now you should be ready to go to create GitHub repositories and work
with them form RStudio on any of your computers.

# Further Reading:

- <https://happygitwithr.com/>

- <https://git-scm.com/book/en/v2>
