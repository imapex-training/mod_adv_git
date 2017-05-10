
* When a merge conflict occurs, git uses these indicators to surround the conflict
    * `<<<<<<< HEAD` 
        * Inserted a line before the point of the conflict
        * What follows is the version of the source file
    * `=======`
        * Inserted at the end of the point of conflict 
        * *A conflict could be 1 or more lines of code/text*
        * What follows is the version being **merged** into the source file
    * `>>>>>>> example `
        * Inserted after the point of the conflict
        * After the `>>>>>>>` the name of the branch is listed 

