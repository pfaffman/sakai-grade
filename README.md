# sakai-grade
Automate grading from a Sakai bulk_downloads.zip file


## NOTE

This code was last known to work in March 2016. It probably doesn't work anymore. If you have a budget, or can make a case that I should help you for free, please feel free to contact me. I can't promise that I'll be able to help, but it
won't hurt to ask.

## What was once true

This works pretty well under Ubuntu Linux and MacOS. I have started
trying to make it work under Windows with gitbash installed, but it
has a long way to go. As of 2015-09-01 the big problem was that there
is no unzip in Windows.

If you use this code, please feel free to email me with problems and
to submit changes via git or email.

# How it is supposed to work

In Sakai you 

1. click the "Download All" link, 
- click the "All" checkbox (you can choose subsets, but I don't see
  any real advantage)
- run this script

At that point, it

1. unzips the zip file
- creates an html file with names of the students, the contents of
  their submission text, and links to files they submitted.
- Opens the grading.html file in your default browser
- opens the grades.csv file in $EDITOR

At this point, you look at the students' work and enter grades into
the grades.csv file. You can enter comments in the comments.txt files
in each student's folder. When you are done (see $EDITOR notes below)
it creates a zip file called ASSIGNMENT.zip (where ASSIGNMENT is the
assignment name). You then upload the zip file to Sakai and all of
your grades and comments.txt files are entered into the system.

# Notes

The script assumes that bulk_download.zip is in ~/Downloads (these can
be changed in variables at the beginning of the script). 

$EDITOR can also be customized at the beginning of the script. I use
emacsclient because I am a hopeless zealot and emacsclient will pause
the script until the grading is done. The obvious tool would be a
spreadsheet, but you will need to edit the WAIT variable to have the
script pause until you finish grading and press enter in the terminal
window. 


Jay Pfaffman
<jay@pfaffman.com>
