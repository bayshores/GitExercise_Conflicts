MERGED EX1

# GitExercise_Conflicts

This exercise assumes you are using the COGS 108 Datahub setup.  But you can do everything here using your own computer if you set it up with the same tools (which is recent Jupyterlab with the git extension built on nbdime). If you are using git command line or VSCode, or something else entirely then you can still do this exercise, but the step by step insructions will need to be adapted to your tools.  There is always more than one way to get something done, just learn and use the tool that you prefer!

This repo contains two branches: main and ex1. There is a single line text conflict in one cell between the two branches. The goal of this exercise is 
two-fold; to learn how to stage and commit changes to a branch and then to learn how to merge the changes from one branch to another.

Below is a graph of the commit situation in the repo right now... the commits on each branch have produced a single line conflict you need to deal with before merging

```
----*----*[main]
     \
      \----*[ex1]
```

We will do two seperate git operations 
- [Part 1] add a new change to branch main, thus introducing a second difference with ex1 branch
- [Part 2] then we will merge the changes from branch ex1 into main

Thus after Part 1 the new graph will look like

```
----*----*----*[main]
     \
      \----*[ex1]
```

And after Part 2 the new graph will look like

```
----*----*----*----*[main]
     \             /
      \----*------/
```

To work on this exercise:
- Fork this repo by pressing the Fork button at the top of this webpage.  When you fork it MAKE SURE you **UNCHECK** the default option to "Copy the main branch only". You want all the branches!
-  Forking this repo made a copy of this repo on YOUR GitHub. You own this fork, you can change it however you like.
- The original repo was at `https://github.com/COGS108/GitExercise_Conflicts.git`, your forked copy will be located at `https://github.com/your_username/GitExercise_Conflicts.git` where you must replace `your_username` with your actual GitHub username.
- Note that the fork is a remote copy on GitHub... you will have to go to Datahub, login, and get a local copy of the fork (NOT the original) repo there.
- Let's get that local copy... login to Datahub.
- Use the Datahub file browser to make sure you are in a directory you are allowed to write new files to, e.g. the `private` directory inside your home directory.  Double click on the file browser to set your current working location to whatever is best for how you want to organize files.  Wherever you are in the file browser is where the new git repo will be created.
-  On the far left you will see a vertical stack of icons in a grey panel.  Click on the one that's a diamond with some lines inside it, that's the git panel.
-  Click the button "Clone a Repository" and set remote URL to `https://github.com/your_username/GitExercise_Conflicts.git` where you must replace `your_username` with your actual GitHub username. Click the button that says `Clone`
- Your new local copy of the repository will appear in the file browser... double click on the new folder `GitExercise_Conflicts` to go inside and view the files!

Part I - Make a local change on main
-  Open `Project.ipynb`
-  Just for fun, run both cells of the notebook to see the plot
-  Unfortunately running the notebook changes the metadata stored inside it.  The counter for how many times a cell was run, the binary data from the plot.  This is stuff we do NOT want to version control... its not important and it clogs up the system because notebook metadata for plots can be very big. Before we do any git operations it is a best practice to click on the pulldown menu item `Edit -> Clear Outputs of All Cells`
- Lets add a change: the last line of the notebook currently says `ax.grid()` which is bad Python form... yeah it works to turn on the grid lines of the plot implicitly, but it would be much more human readable if we used the more Pythonic `ax.grid('on')`.  Please make that change and don't forget to save the file when you are done!
-  On the far left you will see a vertical stack of icons in a grey panel.  Click on the one that's a diamond with some lines inside it, that's the git panel.