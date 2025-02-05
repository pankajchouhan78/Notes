# Git!

## What is Git?

Git ek software hai jo developers ke liye code version control aur collaboration ke liye use hota hai. Isse aap code ke changes track kar sakte hain aur multiple logon ke saath code share kar sakte hain. Git ka upayog code management me hota hai.

## What do you understand by the term ‘Version Control System’ Git?

"Version Control System" ek aisa system hai jo developers ko allow karta hai unke code ke alag-alag versions ko track karna aur manage karna. Isse code ki har modification ya change ko save kiya jata hai, jisse aap pichli states par vapas ja sakte hain agar kuch gadbad ho jaati hai.
  

## What is GitHub?

GitHub ek popular web-based platform hai jahan par developers code repositories create kar sakte hain aur un repositories me apna code store kar sakte hain. Yeh ek Git-based hosting service hai, jiski madad se aap apne projects ko online store kar sakte hain. GitHub ke through aap apne code ko publicly share kar sakte hain ya privately apne team ke saath collaborate kar sakte hain.


## Mention some popular Git hosting services.

1.  **GitHub**: GitHub ek bahut popular Git hosting service hai jahan aap public aur private repositories create kar sakte hain. Yeh wide community aur integration tools ke liye jana jata hai.
    
2.  **GitLab**: GitLab ek aur prasiddh Git hosting platform hai jo open-source aur self-hosted options bhi provide karta hai. Isme CI/CD (Continuous Integration/Continuous Deployment) features bhi built-in hote hain.
    
3.  Bitbucket
4.  SourceForge
5.  Azure DevOps
6.  AWS CodeCommit
    
## Different types of version control systems

 List of Version Control Systems:

1.  Centralized Version Control System (CVCS)
2.  Distributed Version Control System (DVCS)
3.  File-based Version Control System
4.  Repository-based Version Control System
5.  Branching and Merging Version Control System
6.  Proprietary Version Control System
7.  Open-Source Version Control System
---
1. **Centralized Version Control System (CVCS)**
**Definition**: CVCS me ek central server hota hai jahan par sabhi code repositories store kiye jaate hain.

**Functionality**: Developers apne local systems se code checkout aur update karte hain. Jab koi developer changes karta hai, unhe server par update karna padta hai.
Example: Apache Subversion (SVN).

2. **Distributed Version Control System (DVCS)**

  **Definition**: DVCS me har developer ka apna local copy hota hai, jise woh independently manage kar sakta hai.

**Functionality**: Changes commit karne se pehle, developers apne local copy me modifications test kar sakte hain. Ye system offline work karne ki suvidha bhi deta hai.
Example: Git, Mercurial.

3. **File-based Version Control System**

**Definition**: Isme version control individual files ka hota hai, instead of whole project.
**Functionality**: Developers file-level history aur changes ko track kar sakte hain, par ye puri project ki history nahi rakhta.
Example: RCS (Revision Control System).

4. **Repository-based Version Control System**

  **Definition**: Isme complete repositories ka version control hota hai, jahan par sabhi related files aur directories ek repository me store hote hain.
  
**Functionality**: Changes repository level par manage kiye jaate hain, jisse poora project ek saath track hota hai.
Example: Git, Subversion.

5. **Branching and Merging Version Control System**

Definition: Isme alag-alag branches create karke development ki progress manage ki jaati hai.
**Functionality**: Changes ko alag branches me test kiya jata hai aur fir integrate kiya jata hai, jisse main branch par stable code hota hai.
Example: Git, Mercurial.

6. **Proprietary Version Control System**

**Definition**: Kuch organizations apne specific needs ko address karne ke liye khud ke internal VCS develop karte hain.

**Functionality**: Yeh systems organization ki specific requirements ke liye customize kiye jaate hain aur public nahi hote.

7. **Open-Source Version Control System**

**Definition**: Yeh VCS open-source hote hain, jinka use kisi bhi developer dwara free me kiya ja sakta hai.
**Functionality**: Developers in tools ka use kar ke community-driven projects par kaam kar sakte hain.
Example: Git, Mercurial, SVN.


## Advantages of Git:
1.  **Version Control**: Git aapke code ke alag-alag versions ko manage karta hai, jisse aap pichle versions par vapas ja sakte hain aur code ki history dekh sakte hain.
2.  **Collaboration**: Multiple developers ke liye Git par ek hi project par kaam karna aasaan hota hai. Yeh changes ko merge karne me madad karta hai.
3.  **Branching**: Git me branches create karke alag-alag features develop kiye ja sakte hain bina existing code ko affect kiye, jisse experimentation aur organized development ka mauka milta hai.
4.  **Local Development**: Developers apne local systems par code changes test kar sakte hain.
5.  **Security**: Git repositories ko secure rakha ja sakta hai. Aap specific access permissions set kar sakte hain, jisse code ki security maintain hoti hai.
6.  **Backup**: Git distributed backup provide karta hai, kyunki har developer ke paas apni local copy hoti hai, isliye data loss ka khatra kam hota hai.
7.  **Open Source**: Git open-source hai, jisse koi bhi developer free me use kar sakta hai.
8.  **Integration**: Git ko various tools aur services ke sath integrate kiya ja sakta hai.
9.  **Speed and Efficiency**: Git efficient algorithms ka use karta hai, jo code commits, branching, aur merging ko fast aur smooth banata hai.
 

## Difference between Git and GitHub ?
| **Git**                                    | **GitHub**                                 |
--------------------------------------------|--------------------------------------------|
|Git ek version control system hai, jo aapko code ke changes ko track aur manage karne ki suvidha deta hai. Yeh aapke local computer par kaam karta hai aur internet ki zarurat nahi hoti. Isse aap code repositories banate hain, changes commit karte hain, aur branches create karte hain. | Dusri taraf, GitHub ek web-based platform hai jo Git ke upar bana hai. Yeh Git repositories ko cloud me host karta hai, jisse aap apne code ko aasani se share kar sakte hain aur dusron ke sath collaborate kar sakte hain. GitHub ek graphical interface offer karta hai aur isme issue tracking aur project management tools bhi hote hain.|



## What is a Git repository?
A Git repository is a place where your project's code and its complete version history are stored. It contains all the files and folders of your project, along with a record of all the changes you have made.

## How can you initialize a repository in Git?
To initialize Git repository follow the below steps:
1.  **Command Line Use Kare**:
    -  Terminal ya Command Prompt Open Kare
    -  Directory Me Pahunche
    -  Git Init Command Ka Use Kare
2.  **Git GUI Tools Use Kare**:
3.  **GitHub ya GitLab Use Kare**:
      - Web-Based Services: Agar aap GitHub ya GitLab jaise platforms use karte hain, to aap wahan online repository create kar sakte hain.
      - Uske baad, aap apne local system par us repository ko clone kar sakte hain, jisse aap apne code ke sath kaam kar sakte hain.

## What language is used in Git?
Git ke code me mainly C programming language ka use hota hai. Git ka core part C me likha gaya hai, jisse iska performance aur portability maintain hota hai.

## Which command is used to create an empty Git repository?
An empty Git repository can be created using the git init command.

## What does git pull origin master do?
git pull origin master ek Git command hai jo remote repository se latest changes ko local repository me update karta hai. Yeh command karne se aapke local repository me "origin" (remote repository) ke "master" branch ke latest changes ko download aur merge kiya jata hai.

  Isse aapke local repository aur remote repository ke "master" branches me agar koi differences hain, to woh merge ho jate hain, jisse aapka local code updated hota hai. Yadi kisi aur branch ko update karna ho to aap "master" ki jagah us branch ka naam bhi use kar sakte hain.

## What does the git push command do?
git push ek Git command hai jo aapke local Git repository me kiye gaye code changes ko remote repository me upload karta hai. Iska matlab hai ki aapke local system par ki gayi code changes ab online remote repository par available ho jati hain, jisse dusre developers us code ke sath kaam kar sakte hain.

| **Feature**          | **git fetch**                                | **git pull**                                |
|----------------------|----------------------------------------------|--------------------------------------------|
| **Function**         | Remote repository se latest changes download karta hai, lekin local branch me merge nahi karta. | Remote repository se latest changes download karke local branch me merge kar leta hai. |
| **Safety**           | Safe operation hai, kyunki local branch me koi immediate changes nahi hote hain. Aap changes dekh sakte hain aur decide kar sakte hain ki kab aur kaise merge karna hai. | Remote repository ke changes ko directly local branch me merge kar deta hai. Isliye careful rehna padta hai. |


## GitHub, GitLab and Bitbucket are examples of git repository _______ function?
GitHub, GitLab, and Bitbucket are examples of Git repository hosting services. These platforms provide a place to host and manage Git repositories, making it easy for developers and teams to collaborate on code, track changes, and share their projects. They offer additional features like issue tracking, project management tools, and integrations, making them valuable for code hosting and collaboration.

## What do you understand about the Git merge conflict?
Git merge conflict ek sthiti hai jab Git me do branches ko merge karne ki koshish karta hai, lekin woh branches ke beech me conflict (takrar) paya jata hai. Conflict tab hota hai jab dono branches me ek hi file ke ek hi hisse me alag-alag changes hote hain, aur Git nahi jaanta ki kaunsa code use karna chahiye.

Is sthiti me, developers ko conflict resolution karni hoti hai, matlab unhe manually decide karna hota hai ki konsa code behatar hai. Git aapko confliction file me dikhata hai, aur aapko code me changes karne aur firse commit karke conflict ko resolve karna hota hai. Ye process collaboration me jaroori hoti hai jab multiple log ek hi codebase par kaam kar rahe hain.

## How do you resolve conflicts in Git?
Git merge conflicts ko resolve karne ke liye neeche diye gaye kadam follow kar sakte hain:
1.  Check for Conflicts: Jab aap merge karte hain aur conflict hota hai, to Git aapko conflicted file ke andar conflict markers (<<<<<, ====, >>>>) ke saath dikhayega.
    
2.  Open the Conflicted File: Open karein us conflicted file ko ek text editor me.
    
3.  Manually Resolve: Ab aapko decide karna hoga ki kaunsa code keep karna hai. Aap conflict markers (<<<<<, ====, >>>>) ke beech me code ko edit karke changes ko manually resolve kar sakte hain.
    
4.  Remove Conflict Markers: Once you have resolved the conflict, remove the conflict markers (<<<<<, ====, >>>>) from the file.
    
5.  Save the File: Save the file with the resolved changes.
6.  Stage the Resolved File: Use git add command to stage the resolved file.
  
7.  Commit the Resolved Changes: Commit the changes with a commit message that indicates the conflict resolution.
  
8.  Continue the Merge: If there are more conflicts, repeat the process for each conflicted file.
  
9.  Complete the Merge: Once all conflicts are resolved, complete the merge with git commit.
  
10.  Push the Changes: If you were merging changes from a remote repository, push the resolved changes back to the remote repository using git push.
  
These steps will help you resolve merge conflicts in Git. It's important to carefully review and test your changes after resolving conflicts to ensure your code works as expected.

 ## What is the process to revert a commit that has already been pushed and made public?

Ek commit ko revert karna jo pehle se pushed ho chuka hai aur public ho gaya hai, yeh process:

1.  New Revert Commit Create Karein: Pehla kadam yeh hai ki aap ek naya commit create karein jo aapke pehle commit ko undo kare. Is commit me aap pehle wale commit ko undo karne wale changes ko include karenge.
    
2.  Git Revert Use Karein: Revert commit create karne ke liye git revert command ka upayog karein. Aap git revert ke sath -n option use karke commit message ke sath ek revert commit create kar sakte hain, jisse pehle wale commit ke changes undo ho jayenge.
Example: git revert -n <commit_sha>

3.  Changes Review Karein: Ab aap changes ko review karein aur confirm karein ki aapko revert commit me sahi changes shamil kiye gaye hain.
    
4.  Revert Commit Ko Commit Karein: Changes ko confirm karne ke baad, revert commit ko commit karein. Commit message me aap indicate kar sakte hain ki yeh commit kis commit ko undo kar raha hai.
    
5.  Push Karein: Revert commit ko push karein tak ki woh public repository me bhi available ho jaye.
    
Is process se aap ek pehle se pushed commit ko undo kar sakte hain aur public repository me changes ko update kar sakte hain. Yeh dhyan rahe ki is process se aapke codebase me ek revert commit add ho jayega, lekin pehle commit ka history bhi preserve rahega.



## What does git clone do?
git clone is a command that makes a copy of an existing Git repository on your computer. It downloads all the files and history from a remote repository so you can work on it locally.

## What exactly is forking in Git?
Forking ek Git me common practice hai, jisse aap ek existing repository ko clone karke uska independent copy create karte hain. Yani ki, aap kisi aur ke repository ko fork karke uske codebase ka ek copy apne GitHub (ya GitLab, Bitbucket, etc.) account me store kar sakte hain. Forking ka main uddeshya dusre ke codebase me contribute karne ya us codebase par khud ki development start karne ka hai.

Yahan fork karte samay aapka original repository (jise aap clone kar rahe hain) se koi prabhav nahi padta. Aap forked repository me koi bhi changes kar sakte hain, naye features add kar sakte hain, aur fir apne forked repository me apne changes ko commit aur push kar sakte hain.

Forking ka use open-source projects me contribute karne me bhi hota hai. Aap ek project ko fork karke usme apne improvements ya bug fixes add karke, original project owner ke liye ek "pull request" bhej sakte hain, jisse aapke changes original project me merge kiye ja sakte hain.

Overall, forking Git me collaboration aur codebase contribution ko aasan banata hai, aur isse aapko flexibility milti hai apne project me changes karne ke liye bina original repository ko affect kiye.

## How does Git work?
Git ek distributed version control system (DVCS) hai jo code management aur collaboration ko aasan banata hai. Git kaam kaise karta hai, yeh samajhne ke liye neeche diye gaye kuch mukhya concepts hain:

Repository (Repo):
Git me har project ka ek repository hota hai. Isme aapka code, files, aur commit history store hota hai.

Local Repository:
Har developer apne local system par ek copy (clone) banata hai, jise local repository kehte hain.
Isme aap code changes karte hain, testing karte hain, aur commit karte hain.

Remote Repository:
Aapka project ek remote repository par bhi hota hai, jaise GitHub, GitLab, ya Bitbucket.
Isme sab developers ka code ekatrit hota hai aur collaboration hoti hai.

Commits:
Code changes ko Git me "commits" ke roop me store kiya jata hai.
Har commit ek unique SHA-1 hash se label kiya jata hai.

Branching:
Git me aap alag-alag branches create kar sakte hain, jisse aap code ka alag-alag versions develop kar sakte hain.
Branching aapko experimentation aur isolation me madad karta hai.

Merging:
Jab code development complete ho jata hai, aap branches ko merge kar sakte hain, jisse codebase me changes integrate ho jate hain.

Pull and Push:
Developers apne local changes ko remote repository me "push" karke share karte hain.
Remote changes ko local repository me "pull" karke download kiya ja sakta hai.

### Conflict Resolution:
Jab do log ek hi file ke ek hi hisse me alag-alag changes karte hain, to Git me "merge conflict" hota hai. Developers ko manually resolve karna hota hai.
Git ek decentralized system hai, iska matlab ki har developer apne local repository me code ko manage karta hai aur remote repository ke sath collaboration karta hai. Git ki mukhya bhumika code versioning, collaboration, aur history tracking me hoti hai, jo software development me kafi mahatvapurna hoti hai.

## What are some of the most important features of Git?
1.  Distributed Version Control: Har developer apne local system par full copy (clone) of the repository rakhta hai, jisse offline kaam kiya ja sakta hai.
  
2.  Fast Performance: Git efficient algorithms ka use karta hai, jisse code commit, branching, aur merging fast hoti hai.

3.  Branching and Merging: Git me branching aur merging aasan hota hai, jisse alag features develop kar sakte hain aur unhe main code se integrate kar sakte hain.

4.  Data Integrity: Git aapke code ke versions ko SHA-1 hash se label karta hai, jisse data integrity maintain hoti hai.

5.  History Tracking: Git code ki puri history track karta hai, jisse aap changes aur issues ka pata laga sakte hain.
    
6.  Open Source: Git open-source hai, iska matlab hai ki aap ise freely use kar sakte hain.

7.  Security: Git repositories secure hote hain aur specific access permissions set kiya ja sakta hai, jisse code ki security maintain hoti hai.
    
8.  Collaboration: Multiple developers asani se ek hi project par kaam kar sakte hain, aur unke code changes ko merge kar sakte hain.

9.  Staging Area: Git me staging area hoti hai jahan par aap code changes ko review karke commit kar sakte hain, jisse aapko control milta hai kaise aur kya commit karna hai.

## What is the difference between git remote and git clone?

| **Feature**          | **git remote**                               | **git clone**                               |
|----------------------|----------------------------------------------|---------------------------------------------|
| **Function**         | Remote repositories ki list dikhata hai jo local Git repository ke saath judi hoti hain. | Ek remote Git repository ko apne local system par clone (copy) karne ke liye use hota hai. |
| **Usage**            | Remote repositories ke URLs aur unke short names (jaise "origin") ko dikhata hai. | Existing project ko local system me copy karne ke liye use hota hai, taki aap us par kaam kar sakein. |
| **Purpose**          | Remote repositories ke saath connection ko manage karne ke liye use hota hai. | Ek remote repository ka exact copy create karne ke liye use hota hai. |

## Difference between git pull and git fetch?
| **Aspect**           | **git pull**                                             | **git fetch**                                      |
|----------------------|---------------------------------------------------------|----------------------------------------------------|
| **Function**         | Downloads the latest changes from the remote repository and merges them into the local branch. | Downloads the latest changes from the remote repository but does not merge them into the local branch. |
| **Safety**           | Directly merges remote changes into your local branch, which might overwrite your local changes. | A safer operation as it only downloads the changes, allowing you to review and merge them manually. |
| **Use Case**         | When you want to update your local branch with the latest remote changes immediately. | When you want to check for updates in the remote repository without affecting your local branch. |


## Is Git and GitHub the same thing?
Nahi, Git aur GitHub alag-alag cheezen hain:
**Git**:
- Git ek distributed version control system (DVCS) hai. Yeh ek software tool hai jo code versioning aur code management me use hota hai.
- Git aapke local system par code ke versions ko track karta hai, code changes ko commit karta hai, branching aur merging ki suvidha deta hai, aur code collaboration aur history tracking ke liye upayogi hai.

**GitHub**:
- GitHub ek online platform hai jo Git repositories hosting ke liye upayog hota hai. GitHub aapko remote Git repositories host karne aur code sharing ke liye madad karta hai.
- Developers GitHub par apne Git repositories create kar sakte hain, code share kar sakte hain, collaboration kar sakte hain, aur issues track kar sakte hain.
- GitHub Git repositories ko remote server par store karta hai, jisse aap unhe kahin se bhi access kar sakte hain.

