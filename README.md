###  
- O (ORIGNAL COMMIT) is original sort order (unicode SORT order) [sample_0]
- A (OUR COMMIT) is O in new sort order (unicode code point order) 
- B (OTHER COMMIT) copies of O in original sort orter (unicode SORT order) with 
      different edits in an attempt to create commit conflicts on merge


### Goal of experiment is to to create commit conflicts during merge A into B
O, A, & B will be dressed out with code to make comflicts more likely

### sample_0 -- cp A to src 

### result_0 -- no conflicts
merge sample_0 into master_0
```
> checkout master_0
> git merge sample_0 --no-commit
Automatic merge went well; stopped before committing as requested
> git checkout -b result_0
> git commit 
```
### result_1 -- conflicts !!!
merge sample_0 into master_1
```
> checkout master_1
> git merge sample_0 --no-commit
Auto-merging src/RowanGitMergeTool-Core/RowanSample9V3Class1.class.st
CONFLICT (content): Merge conflict in src/RowanGitMergeTool-Core/RowanSample9V3Class1.class.st
Automatic merge failed; fix conflicts and then commit the result.
bosch:RowanGitMergeTool>git status
On branch master_1
You have unmerged paths.
  (fix conflicts and run "git commit")
  (use "git merge --abort" to abort the merge)

Unmerged paths:
  (use "git add <file>..." to mark resolution)
        both modified:   src/RowanGitMergeTool-Core/RowanSample9V3Class1.class.st

no changes added to commit (use "git add" and/or "git commit -a")
bosch:RowanGitMergeTool>git diff
─────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
modified: src/RowanGitMergeTool-Core/RowanSample9V3Class1.class.st
─────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
@ src/RowanGitMergeTool-Core/RowanSample9V3Class1.class.st:14 @ Class 
}

{ #category : 'accessing' }
<<<<<<< HEAD
RowanSample9V3Class1 >> _123Abc [ 
    "comment"
    ^1
=======
RowanSample9V3Class1 >> A_bc123 [ ^1
>>>>>>> sample_0
]

{ #category : 'accessing' }
@ src/RowanGitMergeTool-Core/RowanSample9V3Class1.class.st:32 @ RowanSample9V3Class1 >> _123Abc [ ^
]

{ #category : 'accessing' }
<<<<<<< HEAD
RowanSample9V3Class1 >> A_bc123 [
    "comment"
    | x |
    x := 1 + 1.
    ^"comment"1
=======
RowanSample9V3Class1 >> _ABC123 [ ^1
>>>>>>> sample_0
]

{ #category : 'accessing' }
```

