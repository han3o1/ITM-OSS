1. List all the branches in this repository and, for each branch, list the commits.
    Use git branch to list the branches in this repository.
    Use git checkout to explore each branch.
    Use git log --decorate to explore the structure of commits.
   
Branches:
```
* feature-msg
  master
```

Commits on master:
```
commit c146e374cd120f91c18ee97679cdb148d9bde6e9 (HEAD -> master)
Author: Josue Obregon <jobregon@seoultech.ac.kr>
Date:   Mon Aug 19 18:39:59 2024 +0900

    Adding class B skeleton and Main class

commit b487ec97a3f8626bf4b427df5bc73f00d334c7b9
Author: Josue Obregon <jobregon@seoultech.ac.kr>
Date:   Mon Aug 19 18:36:22 2024 +0900

    Adding class A skeleton

commit f6f58b7977bddf977c0fcc880113ef27a5740a8f
Author: Josue Obregon <jobregon@seoultech.ac.kr>
Date:   Mon Aug 19 18:35:11 2024 +0900

    Creating all files (all empty)
```

Commits on feature:
```
commit 71bcd3fc4b13ba0d4df2270259392a75025fdfa9 (HEAD -> feature-msg)
Author: Josue Obregon <jobregon@seoultech.ac.kr>
Date:   Mon Aug 19 18:38:06 2024 +0900

    Adding header of method printMessage()

commit b487ec97a3f8626bf4b427df5bc73f00d334c7b9
Author: Josue Obregon <jobregon@seoultech.ac.kr>
Date:   Mon Aug 19 18:36:22 2024 +0900

    Adding class A skeleton

commit f6f58b7977bddf977c0fcc880113ef27a5740a8f
Author: Josue Obregon <jobregon@seoultech.ac.kr>
Date:   Mon Aug 19 18:35:11 2024 +0900

    Creating all files (all empty)
```

---
2. Try git log --graph --all to see the commit tree. Paste the result here and write a paragraph to provide an interpretation of what you found.
```
* commit c146e374cd120f91c18ee97679cdb148d9bde6e9 (master)
| Author: Josue Obregon <jobregon@seoultech.ac.kr>
| Date:   Mon Aug 19 18:39:59 2024 +0900
|
|     Adding class B skeleton and Main class
|
| * commit 71bcd3fc4b13ba0d4df2270259392a75025fdfa9 (HEAD -> feature-msg)
|/  Author: Josue Obregon <jobregon@seoultech.ac.kr>
|   Date:   Mon Aug 19 18:38:06 2024 +0900
|
|       Adding header of method printMessage()
|
* commit b487ec97a3f8626bf4b427df5bc73f00d334c7b9
| Author: Josue Obregon <jobregon@seoultech.ac.kr>
| Date:   Mon Aug 19 18:36:22 2024 +0900
|
|     Adding class A skeleton
|
* commit f6f58b7977bddf977c0fcc880113ef27a5740a8f
  Author: Josue Obregon <jobregon@seoultech.ac.kr>
  Date:   Mon Aug 19 18:35:11 2024 +0900

      Creating all files (all empty)
```
This commit log displays the structure of two branches:

- The `master` branch contains the most recent commit (c146e374), where a skeleton for class `B` and the `Main` class were added.
- The `feature-msg` branch has the commit (71bcd3fc) just before `master`, where the header for the `printMessage()` method was added.
- The previous commit (b487ec9) introduced the skeleton of the `A` class.
- The very first commit (f6f58b7) initialized the project with all empty files.

---
3. Choose an already existing branch and use git diff BRANCH_NAME to view the differences between a branch and the current branch. Summarize the difference from master to the other branch.
```
diff --git a/A.java b/A.java
index d2906f7..96a276f 100644
--- a/A.java
+++ b/A.java
@@ -1,7 +1,3 @@
 public class A {
-
-    public void printMessage(){
-
-    }

 }
\ No newline at end of file
diff --git a/B.java b/B.java
index e69de29..b5952d8 100644
--- a/B.java
+++ b/B.java
@@ -0,0 +1,3 @@
+public class B {
+
+}
diff --git a/Main.java b/Main.java
index e69de29..3d84912 100644
--- a/Main.java
+++ b/Main.java
@@ -0,0 +1,6 @@
+public class Main {
+    public static void main(String[] args){
+        //write code here
+
+    }
+}
\ No newline at end of file
```
Differences between `master` and `feature-msg`:
1. A.java:
   - In the `feature-msg` branch, the `printMessage()` method has been removed.
2. B.java:
   - In the `feature-msg` branch, a new class `B` has been added, but it currently contains no methods or functionality.
3. Main.java:
   - In the `feature-msg` branch, a new class `Main` has been added. It contains a `main` method with a comment placeholder (`//write code here`), but no functional code is implemented yet.
In summary, the `feature-msg` branch introduces two new files (`B.java` and `Main.java`) and removes the implementation of the `printMessage()` method in `A.java`.

---
4. Write a command sequence to merge the branch that is not the master branch into master.
```
git merge feature-msg
```

---
5. Write a command (or sequence) to (i) create a new branch called print-msg (from the master) and (ii) change to this branch.
```
git branch print-msg
git checkout print-msg
```

---
6. Edit A.java adding the following implementation code for the printMessage() method.
        System.out.println("This is a new message.");
          System.out.println("Git is fun, isn't it?");
```
vi A.java
```
```
cat A.java
public class A {

    public void printMessage(){
        System.out.println("This is a new message.");
        System.out.println("Git is fun, isn't it?");
    }
```

---
7. Write a command (or sequence) to commit your changes.
```
git add A.java
git commit -m "Added new message"
```

---
8. Change back to the master branch and change A.java adding the following implementation code for the printMessage() method (commit your change to master):
        System.out.println("Hello opensource world!");
```
git checkout master
```
```
vi A.java
```
```
cat A.java
public class A {

    public void printMessage(){
        System.out.println("Hello opensource world!");
    }

}
```
```
git add A.java
git commit -m "Added hello message"
```

---
9. Write a command sequence to merge the print-msg branch into master and describe what happened.
```
git merge print-msg
Auto-merging A.java
CONFLICT (content): Merge conflict in A.java
Automatic merge failed; fix conflicts and then commit the result.
```
The message indicates that there is a merge conflict in the `A.java` file between the `master` branch and the `print-msg` branch. Both branches have made changes to the same part of the same file.

---
10. Write a set of commands to abort the merge.
```
git merge --abort
```

---
11. Now repeat item 9, but proceed with the manual merge (editing A.java). All implemented methods are needed. Explain your procedure.
```
git add A.java
git commit -m "Manual merge completed"
```
I performed a manual merge by resolving the conflicts(removing the conflict markers) directly in the file. This approach allowed to ensure that both sets of changes were retained and that the final implementation in A.java included the desired functionality.

---
12. Write a command (or set of commands) to proceed with the merge and make master branch up-to-date.
```
git merge print-msg
```
```
git add A.java
git commit -m "Manual merge completed"
```
```
git push origin master
```

---
13. Complete Part 2. Then, come back here and answer the following: Report your experience of submitting the Part 2. Please, include the steps you followed, the commands you used, and the problems you faced (within the file you created for the Part 1).
