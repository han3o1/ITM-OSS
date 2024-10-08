1. List all the branches in this repository and, for each branch, list the commits.
    Use git branch to list the branches in this repository.
    Use git checkout to explore each branch.
    Use git log --decorate to explore the structure of commits.

    Branches:
      - master
      - feature
    Commits on master:
      - commit 123abc: Initial commit
      - commit 456def: Added new feature
    Commits on feature:
      - commit 789ghi: Working on feature branch

2. Try git log --graph --all to see the commit tree. Paste the result here and write a paragraph to provide an interpretation of what you found.


   
4. Choose an already existing branch and use git diff BRANCH_NAME to view the differences between a branch and the current branch. Summarize the difference from master to the other branch.
5. Write a command sequence to merge the branch that is not the master branch into master.
6. Write a command (or sequence) to (i) create a new branch called print-msg (from the master) and (ii) change to this branch.

10. Edit A.java adding the following implementation code for the printMessage() method.
        System.out.println("This is a new message.");
          System.out.println("Git is fun, isn't it?");

11. Write a command (or sequence) to commit your changes.

12. Change back to the master branch and change A.java adding the following implementation code for the printMessage() method (commit your change to master):
        System.out.println("Hello opensource world!");

13. Write a command sequence to merge the print-msg branch into master and describe what happened.

14. Write a set of commands to abort the merge.

15. Now repeat item 9, but proceed with the manual merge (editing A.java). All implemented methods are needed. Explain your procedure.

16. Write a command (or set of commands) to proceed with the merge and make master branch up-to-date.

17. Complete Part 2. Then, come back here and answer the following: Report your experience of submitting the Part 2. Please, include the steps you followed, the commands you used, and the problems you faced (within the file you created for the Part 1).
