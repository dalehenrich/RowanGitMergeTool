###  
- O (ORIGNAL COMMIT) is original sort order (unicode SORT order) [sample_0]
- A (OUR COMMIT) is O in new sort order (unicode code point order) 
- B (OTHER COMMIT) copies of O in original sort orter (unicode SORT order) with 
      different edits in an attempt to create commit conflicts on merge


### Goal of experiment is to to create commit conflicts during merge A into B
O, A, & B will be dressed out with code to make comflicts more likely

### result_0 -- no conflicts
merge sample_0 into master_0
Automatic merge went well; stopped before committing as requested
```
checkout master_0
git merge sample_0 --no-commit
git checkout -b result_0
```
