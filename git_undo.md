

### Undoing Git Add
Agar aapne accidentally git add kar diya hai aur ab usse undo karna hai, toh Git mein kuch simple commands hain jo aapko staging area ko reset karne mein madad kar sakte hain. Yaha pe kuch methods diye gaye hain:

### 1. Unstage Changes (Undo git add)
Agar aapne git add command se changes ko stage kar diya hai (matlab files ko commit ke liye ready kar diya hai), aur ab aap chahte hain ki wo changes unstage ho jaayein, toh aap git reset ka use kar sakte hain. Isse aapki changes staged state se wapas working directory mein chali jaayengi, lekin aapka code waisa hi rahega, bas wo commit ke liye ready nahi rahega.

#### Example 1: Unstage a specific file

Agar aapne koi specific file git add ki thi, aur ab aap usko unstage karna chahte hain:
**`git reset <file_path>`**

Yeh command file ko staging area se hata dega, lekin file ke changes working directory mein rahenge.

#### Example 2: Unstage all files
Agar aapne multiple files ko stage kiya hai aur ab sabko unstage karna chahte hain, toh aap yeh command use kar sakte hain:

**`git reset`**

Isse sabhi staged files unstage ho jaayengi, lekin unke changes working directory mein rahenge.

----------

### 2. Unstage and Discard Changes (Undo both git add and changes)

Agar aapne file ko stage kar diya hai aur uske baad jo changes kiye hain unhe completely discard karna chahte hain (matlab, unstage karna aur changes bhi hata dena), toh aap git checkout ka use kar sakte hain.

#### Example: Discard changes in a specific file
**`git checkout -- <file_path>`**

Yeh command us file ke changes ko pichle commit ke version se replace kar dega, aur staging area se bhi unstage kar dega. Dhyaan rahe, isse aapka kaam loss ho sakta hai, kyunki yeh changes permanently discard ho jaate hain.

----------

### 3. Undo git add without Losing Your Changes (Staging Area Reset)

Agar aapko staging area se changes ko remove karna hai, lekin aapke working directory ke changes ko safe rakhna hai (aapko bas stage karna remove karna hai), toh git reset ka simple use best hai.

#### Example: Unstage all files (but keep changes)
**`git reset`**

Isse aapki files unstaged ho jaayengi, par working directory mein jo bhi aapne changes kiye hain wo unchanged rahenge.

----------

### 4. Check Staged Files

Agar aapko yeh dekhna hai ki kaunsi files abhi stage ho rahi hain (ready for commit), toh aap git status command ka use kar sakte hain. Isse aapko pata chal jaayega ki kaunse files staged hain aur kaunse nahi.  

**`git status`**

Yeh command aapko ek clear view degi ki aapne kaunse files add ki hain aur kaunse changes pending hain.

----------


### To remove the untracked files from your Git status, you have two main options:

### Option 1: Remove the files from your working directory

If you want to completely delete these files from your working directory and also have them not show up in git status, use:
**`git clean -f`**  

This will remove all untracked files (including ez_care_updated.png and user_management.png) from your working directory.

### Option 2: Ignore the files without deleting them

If you want to keep these files in your working directory but stop them from being tracked by Git (i.e., prevent them from appearing in git status), you can add them to the .gitignore file:

1.  Open or create a .gitignore file in your repository's root directory.
Add the names of the files you want to ignore:  
ez_care_updated.png
user_management.png

2.    After editing .gitignore, run the following command to remove the files from Git's index (staging area):  
bash  
**`git rm --cached ez_care_updated.png user_management.png`**

3.    This will stop Git from tracking the files but will leave them in your local directory.

### Option 3: Stop showing untracked files temporarily

If you just want to hide untracked files from the git status output (without actually removing them or adding them to .gitignore), you can use the git status command with the -u flag:

bash
**`git status -u no`**

