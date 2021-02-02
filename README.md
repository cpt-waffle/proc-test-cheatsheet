### Test Proctor Training Cheat Sheet

These are the instructions that will be given sent out during the allocated time to do the test (snippet):

## ----------------

Please accept our GitHub invite via email or from here: https://github.com/lighthouse-labs/.
You will then be able to access the assessment test repo here: [link to test repo](https://github.com/lighthouse-labs/assessment-exam-student).

While you are only allocated 2h today for the Mock test, we strongly suggest that you spend more time as needed to achieve 100% over the weekend. The goal of this mock test is to help you revisit and become more comfortable with automated tests while also becoming comfortable with our assessment test workflow.

## ----------------

### Happy Path

Student Visits [link to test repo](https://github.com/lighthouse-labs/assessment-exam-student). Student follows the get started proccedure:

![procedure](https://github.com/vasiliy-klimkin/proc-test-cheatsheet/blob/master/images/1-procedure.gif)


#### 1. Clone the repository

```
git clone git@github.com:lighthouse-labs/assessment-exam-student.git
cd assessment-exam-student
```

#### 2. Installing Required Packages

Either by running __one__ of these 3 commands:

 - `npm install --no-bin-links`
 
 - `npm install sqlite3@4.0.9 && npm install --no-bin-links`

 - `npm install`

 _NOTE_: `WARNINGS ARE OK`, just watch out for actual errors during installation.

#### 3. Open the entire project in Visual Studio Code

![code](https://github.com/vasiliy-klimkin/proc-test-cheatsheet/blob/master/images/2-code.png)

#### 4. Open a terminal window ( in same env that you cloned the repo )

To start the test run:

`npm run start-exam [EXAM-TOKEN]`

You should see an output that looks like this  ( this can vary depending on the test):

```
> node start-exam.js "exam-id-here"

Contacting Server to Start Exam "exam-id-here"

Server Response: 5 Questions:
  Creating Question 00  (30 Points) Answer file: answers/00.js
  Creating Question 01  (30 Points) Answer file: answers/01.js
  Creating Question 02  (20 Points) Answer file: answers/02.js
  Creating Question 03  (20 Points) Answer file: answers/03.js
  Creating Question 04  (20 Points) Answer file: answers/04.js

```

## Answering Questions

Open up `answers/` directory and look into each file. Each of those file is a question for the test. A question can contain multiple parts to it so be sure to remember to scroll down to see if all functions are completed. To run the tests to see if the answer is correct, run the following command:

`npm run question 0`



## Troubleshooting 



#### 404 - Cannot reach Repo (no access)

![404](https://github.com/vasiliy-klimkin/proc-test-cheatsheet/blob/master/images/3-404.png)

This means the student has not accepted their github invitation from Lighthouse Labs Organization. 

First, ask the student to check their email for the github invitation. If they cannot find it ask them what email they are using for their github. Then, send that email out to education cordinator (Chetna, Bradley, Janelle, Emma) and ask them to re-add them into the organization. 

### Cannot `git clone` repo

![git-issue](https://github.com/vasiliy-klimkin/proc-test-cheatsheet/blob/master/images/4-git-issue.png)

This is most likely due to `git` not set up properly. First thing is check if the account is most likely assigned. run the commands:

`git config user.name`

`git config user.email`

Check if the output matches the correct github account. If it doesn't match then use [these instructions from compass to resetup the correct account](https://web.compass.lighthouselabs.ca/activities/289)

If they do match follow the [same instructions](https://web.compass.lighthouselabs.ca/activities/289) and check if public key was added to github. 

If this all has been done, and it still does not work, erase the public key from github and follow the [same instructions](https://web.compass.lighthouselabs.ca/activities/289) to completely reset your github on the machine. 

### `npm install` fails - errors

![npm-err](https://github.com/vasiliy-klimkin/proc-test-cheatsheet/blob/master/images/5-npm-err.png)

This can be caused by many things. 

#### VERSION

First thing check the version of node:

`node -v`

It should be running either:

 `10.20.1` - for linux/vagrant/mac(non-m1)

 `15.3.0`  - for mac M1

If that is not the case run this command to install it:

`nvm install 10.20.1` - for linux/vagrant/mac(non-m1)

`nvm install 15.3.0`  - for mac M1

After this change delete `node_modules` and `npm install` again.

#### STILL ERROR VERSION IS CORRECT

Try running one of these commands until only warnings remain:

`npm install --no-bin-links`

`npm install sqlite3@4.0.9 && npm install --no-bin-links`

`npm i`

#### STILL ERROR (SPECIFICALLY TO `node-pre-gyp`)

Try installing it globally:

`npm install -g node-pre-gyp` 

then re-run the commands above. Chances this will fix the issue.

### Cannot find `exam-token`

![test-code](https://github.com/vasiliy-klimkin/proc-test-cheatsheet/blob/master/images/6-test-code.png)

The test `exam-token` is located on todays activity for the test.

### When I run `start-exam` it fails

Do not add quotes around exam token.  Sample of how the command should be used correctly:

`npm run start-exam  a45f4stfg-fsd5wfs-545sfg`


### `npm run question 0` Does not work

Usually thats an issue with not being in the right directory. Make sure person is in the root directory of the test repo.