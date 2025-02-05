
### What is git stash?
git stash ek Git command hai jo aapko apne unsaved changes (jo abhi tak commit nahi kiye hain) ko temporarily store karne ki suvidha deta hai. Matlab, agar aap kisi kaam mein busy hain, lekin aapko kuch aur karne ke liye apna working directory clean karna ho, toh aap apne changes ko stash kar sakte hain. Isse aap apne kaam ko safe rakh sakte hain bina commit kiye, aur baad mein usko dobara laake apply kar sakte hain.

### Why is git stash used?
git stash kai situations mein kaam aata hai, jaise:

1.  **Branch switch karte waqt**: Agar aap kisi branch par kaam kar rahe hain, par aapko kisi aur branch par switch karna ho, lekin aap apne current changes ko commit nahi karna chahte, toh aap unhe stash kar sakte hain.
    
2.  **Working directory clean karna**: Agar aapko test karna ho ya kisi kaam ko temporarily band karna ho, toh stash karke aap apne working directory ko clean kar sakte hain bina apne changes ko lose kiye.
    
3.  **Multiple tasks handle karna**: Agar aap ek task par kaam kar rahe hain, par urgent bug fix karni ho, toh aap apne changes stash kar sakte hain, bug fix kar sakte hain, aur baad mein apne changes ko dobara apply kar sakte hain.
    
4.  **Avoiding unnecessary commits**: Agar aapne changes kiye hain par abhi commit karne ke liye ready nahi hain, toh stashing se aap unnecessary ya incomplete commits se bach sakte hain. Aap apne commit history ko clean rakh sakte hain aur jab changes ready ho, tab unhe apply kar sakte hain.
    
### Git Stash Commands & Their Usage
---
#### 1. Stash Changes (git stash push or git stash)

-   **Command** : **`git stash push -m "message" -u`**
    
-   **Purpose**: Ye command aapke tracked changes (jo Git ke dwara track ho rahe hain) ko stash karta hai. Isse aapka working directory puri tarah se clean ho jata hai, jaise aapne kuch changes kiye hi nahi.
    
-   **Options**:
-   -u or --include-untracked**: Includes untracked files (files not yet added to Git).
    
-   -m "message": Adds a custom message to identify your stash later.

Example:  
  
**`git stash push -m "WIP: Feature X" -u`**
-   This command stashes both tracked changes and untracked files, labeling the stash with the message "WIP: Feature X".
    
---

#### 2. List All Stashes (git stash list)
-   **Command**: **`git stash list`**
    
-   **Purpose**: Ye command aapke stash ki list dikhaata hai. Har stash ka ek index hota hai (jaise stash@{0}, stash@{1}), aur uske sath hi wo kis branch pe kiya gaya tha aur message kya tha, ye sab info milti hai
    
**Example Output**:  
**`stash@{0}: WIP on feature-x: 45a7a0d Commit message`**
**`stash@{1}: WIP on main: 8c43f0a Another commit message`**

---

#### 3. Apply a Stash (git stash apply)

-   **Command**: **`git stash apply <stash-name>`**
-   **Purpose**: Ye command stash ko aapke working directory me apply karta hai, lekin stash ko delete nahi karta. Agar aap stash ka name specify nahi karte, toh Git most recent stash ko apply karega.
Example: git stash apply stash@{0}

---

#### 4. Pop a Stash (git stash pop)

-   **Command**: **`git stash pop`**
-   **Purpose**: Similar to git stash apply, but in addition to applying the changes, it also removes the stash from the list. This is useful when you’re done with the stash and no longer need it.
Example: git stash pop

----------

#### 5. Drop a Stash (git stash drop)

-   **Command**: git stash drop <stash-name>
-   **Purpose**: Deletes a specific stash from the list without applying it. This is useful if you no longer need a particular stash and want to clean up your stash list.
Example: **`git stash drop stash@{0}`**

----------

#### 6. Clear All Stashes (git stash clear)

-   **Command**: **`git stash clear`**
-   **Purpose**: Removes all stashes from the list. This is a complete cleanup of all your saved stashes.
Example: git stash clear

----------

#### 7. Show the Contents of a Stash (git stash show)

-   Command: git stash show <stash-name>
    
-   Purpose: Ye command stash me kiye gaye changes ko show karta hai. Agar aap diff dekhna chahte hain, toh -p flag laga sakte hain.
    

Example:  
git stash show stash@{0} # Shows a summary of the changes

git stash show -p stash@{0} # Shows the full diff of the changes

----------

#### 8. Stash Only Untracked Files (git stash push -u)

-   **Command**: **`git stash push -u`**
-   **Purpose**: Ye command sirf untracked files ko stash karta hai (wo files jo abhi Git se track nahi ho rahi hain). Tracked files ko change nahi karta..
Example: git stash push -u -m "Stash only untracked files"

----------

### When to Use git stash:

-   **Switching Branches**: If you’re working on a feature but need to switch to another branch (e.g., to fix a bug), you can stash your changes to avoid committing incomplete work.
    
-   **Clean Working Directory**: If you need to clean your working directory temporarily without losing your changes.
    
-   **Multiple Tasks**: If you're juggling multiple tasks and need to safely store unfinished work, git stash helps you keep things organized.
    
----------

### Best Practices:

-   Use descriptive messages with -m when stashing to help you remember what each stash contains.
    
-   After applying a stash with git stash pop, always clean up by dropping the stash if you’re done with it.
    
-   If you only need untracked files, use git stash push -u to avoid stashing tracked files.
    
By using git stash effectively, you can manage your workflow better, switch between tasks, and avoid committing incomplete or experimental changes. Let me know if you need further clarification on any command!

---

### Show Detailed Changes for a Specific Stash:

To show detailed changes for a particular stash, use: git stash show -p stash@{n}

Replace n with the stash index (e.g., stash@{0}). The -p option means "patch," and it will show the diff of the changes that were stashed.
