### Clone Git Fork using SSH URL
![git clone](lab4_img1.png)

I coped the SSH url in my Github fork, then I typed `git clone ` in the terminal and pasted in `git@github.com:katelynpdn/lab7.git` after that.

### Run JUnit Tests
![Run JUnit Tests](lab4_img2.png)

I typed `cd lab7` and `<Enter` to change to the directory. I typed `javac -cp lib/junit-4.13.2.jar:lib/hamcrest-core-1.3.jar:.` then I typed in `L` and pressed `<Tab>` to fill in `ListExamples` then I typed in `T` and `<Tab>`to fill in `ListExamplesTests`, then I typed `.j` and `<Tab>` to fill in `ListExamplesTests.java`. After `<Enter` I typed `java -cp lib/junit-4.13.2.jar:lib/hamcrest-core-1.3.jar:. org.junit.runner.JUnitCore ` then the same process as before to fill in `ListExamplesTests`.

### Editing File with Vim
![Run vim](lab4_img3.png)

I typed in `vim ` then typed `L` and pressed `<Tab>` to fill in `ListExamples` then I typed in `.j` and `<Tab>` to fill in `ListExamples.java`. I pressed `<Enter`.

![Editing in vim](lab4_img4.png)

Keypresses: `43j e r2 :wq <Enter>`

### Run Tests Again
![Run Tests](lab4_img5.png)

I typed `javac ` then typed `L` and pressed `<Tab>` to fill in `ListExamples` then I typed in `.j` and `<Tab>` to fill in `ListExamples.java`. I pressed `<Enter`. This recompiles my newly changed ListExamples.java. I pressed `<up><up><up>` to go back in Bash history and get the command `java -cp lib/junit-4.13.2.jar:lib/hamcrest-core-1.3.jar:. org.junit.runner.JUnitCore ListExamplesTests`, then I hit `<Enter>` to run the JUnit Tests.

### Commit and push to Git
![Git commit and push](lab4_img6.png)
I typed `git add ` then typed `L` and pressed `<Tab>` to fill in `ListExamples` then I typed in `.j` and `<Tab>` to fill in `ListExamples.java`. This stages my changes.
I typed `git commit -m "Update ListExamples"` to commit with my message.
I typed `git push origin main`. This pushes my changes to Git.
