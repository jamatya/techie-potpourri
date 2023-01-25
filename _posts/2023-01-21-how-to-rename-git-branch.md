---
title:  "How to rename a git branch"
date: 2023-02-21 12:00:00
categories: [git]
tags: [git, how-to]
author: jamatya
---
1. Go to the current current

     ```javascript
     git branch <old_branch_name>
     ```

2. Rename the branch
    ```javascript
    git branch -m <new_branch_name>
    ```

3. Push the local branch (with new name) and reset the upstream branch
    ```javascript
    git push origin -u <new_branch_name>
    ```

4. Delete the remote branch with old name
    ```javascript
    git push origin --delete <old_branch_name>
    ```
