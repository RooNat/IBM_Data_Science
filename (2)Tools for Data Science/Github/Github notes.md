---
typora-copy-images-to: ./attachments
tags: Github
---

# Github - Branch

[toc]



- A branch is a snapshot of your repository

  - There is a main branch call master

  - Master branch is the official version of the project

  - It is advisable not to push any code that has not been tested in the master.

  - Tests are done to ensure quality before merging with the Master branch

    ![image-20230620201450868](https://raw.githubusercontent.com/RooNat/Myimages/main/2023/06/upgit_20230620_1687288493.png)

- Pull requests are a way of proposing changes to the main branch

  ![image-20230620202008030](https://raw.githubusercontent.com/RooNat/Myimages/main/2023/06/upgit_20230620_1687288809.png)

## Exercise 1: Create a new local 

1. Now let us create a new directory for our local repository.
   Create a `myrepo` directory by copying and pasting the `mkdir` command below into the terminal:

   ```shell
   mkdir myrepo
   ```

2. Go into the `myrepo` directory by copying and pasting the `cd` command below:

   ```shell
   cd myrepo
   ```

   

3. In this `myrepo` directory lets create a new local git repository using the `git init` command. Copy and paste the command below into the terminal:

   ```shell
   git init
   ```

   

4. A new local repository is now created, which you can verify by doing a directory listing by pasting the following command into the terminal window:

   ```shell
   ls -la .git
   ```

   The output shows the contents of the `.git` sub-directory which houses the local repo:

   ![image-20230620204100677](https://raw.githubusercontent.com/RooNat/Myimages/main/2023/06/upgit_20230620_1687290063.png)

## Exercise 2 : Create and Add a file to the local repo

1. Now lets create an empty file using the following `touch` command:

   ```shell
   touch newfile
   ```

   

2. Add the file to the repo using the following `git add` command:

   ```shell
   git add newfile
   ```



## Exercise 3: Commit changes

1. Before we can commit our changes, we need to tell git who we are. We can do this using the following commands (you can copy these commands as is, no need to enter your actual information):

   ```shell
   git config --global user.email "you@example.com"
   git config --global user.name "Your Name"
   ```

   

2. Once the repo has the `newfile` in it let’s commit our changes using the the following `git commit` command. Note that the commit requires a message which we include using the `-m` parameter:

   ```shell
   git commit -m "added newfile"
   ```



## Exercise 4: Create a branch

1. Our previous commit created a default main branch called `master`.

2. To make subsequent changes in our repo, lets create a new branch in our local repostitory. Copy and paste the following `git branch` command into the terminal to create a branch called `my1stbranch`:

   ```shell
   git branch mylstbranch
   ```



## Exercise 5: Get a list of branches and active branch

1. Let’s check which branches our repo contains by pasting the following `git branch` command into the terminal:

   ```shell
   git branch
   ```

   

2. Note the output lists two branches - the default `master` branch with an asterix `*` next to it indicating that it is the currently active branch, and the newly created `mys1stbranch`



## Exercise 6

## Exercise 7

## Exercise 8

## Exercise 9

