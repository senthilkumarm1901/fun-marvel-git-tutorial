# fun-marvel-git-tutorial

> A Marvel-inspired Git Tutorial to help you transition from a beginner to an advanced Git User

---

## I. Team and Responsibilities

> A Team of 4 Writers are collaborating in Git to create amazing comic stories in the Marvel Universe

### About the Team 
- A Lead Script Writer at Marvel is tasked with creation of several comics. 
- He delegates the work to 3 writers with the following responsibilities


### Responsibilities

```mermaid
flowchart LR
    subgraph A[👤 Lead Script Writer]
        direction LR
        B[Oversee and Manage <br>the Development of Overall <br>Marvel Universe of <br>Comic Stories]
    end

    A --> C[👤 Writer 1]
    C --> D[Create individual story arcs<br> for Main Avengers]
    A --> E[👤 Writer 2]
    E --> F[Create story arcs <br>about Other Marvel Heroes]
    A --> G[👤 Writer 3]
    G --> H[Write about the Multi-hero Plots]
```

> Where do they Collaborate  - In `GitHub`

---

## II. Lead Script Writer's Initial Efforts

- Create a repo locally and in remote. 
- Push his initial ground work to the `main` branch

```bash
LeadScriptWriter@terminal lead_script_writer % mkdir -p fun-marvel-git-tutorial
LeadScriptWriter@terminal lead_script_writer % cd fun-marvel-git-tutorial 
LeadScriptWriter@terminal fun-marvel-git-tutorial % touch README.md marvel_heroes.md
LeadScriptWriter@terminal fun-marvel-git-tutorial % pwd
/Users/senthilkumar.m/my_learnings/udemy_courses/writers_place/lead_script_writer/fun-marvel-git-tutorial
LeadScriptWriter@terminal fun-marvel-git-tutorial % ls   
README.md		marvel_heroes.md
LeadScriptWriter@terminal fun-marvel-git-tutorial % cat marvel_heroes.md
> This is the file where all stories of different heroes converge
LeadScriptWriter@terminal fun-marvel-git-tutorial % git init                 
Initialized empty Git repository in /Users/senthilkumar.m/Library/CloudStorage/OneDrive-TOYOTAConnectedIndia/Learnings/udemy_courses/writers_place/lead_script_writer/fun-marvel-git-tutorial/.git/
LeadScriptWriter@terminal fun-marvel-git-tutorial % git config user.email "senthilkumar.m@gmail.com"
LeadScriptWriter@terminal fun-marvel-git-tutorial % git config user.name "senthilkumarm1901"
LeadScriptWriter@terminal fun-marvel-git-tutorial % git remote add origin git@github.com-personal:senthilkumarm1901/fun-marvel-git-tutorial-.git
LeadScriptWriter@terminal fun-marvel-git-tutorial % git remote add origin git@github.com-personal:senthilkumarm1901/fun-marvel-git-tutorial.git
LeadScriptWriter@terminal fun-marvel-git-tutorial % git status
On branch main

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	README.md
	marvel_heroes.md

nothing added to commit but untracked files present (use "git add" to track)
LeadScriptWriter@terminal fun-marvel-git-tutorial % git add README.md && git commit -m "LeadScriptWriter: set initial context to the other 3 writers"
[main (root-commit) 8c3d5c5] LeadScriptWriter: set initial context to the other 3 writers
 1 file changed, 40 insertions(+)
 create mode 100644 README.md
LeadScriptWriter@terminal fun-marvel-git-tutorial % git add marvel_heroes.md && git commit -m "LeadScriptWriter: create a file to collate all stories"
[main 6e20a67] LeadScriptWriter: create a file to collate all stories
 1 file changed, 1 insertion(+)
 create mode 100644 marvel_heroes.md
LeadScriptWriter@terminal fun-marvel-git-tutorial % git push -u origin main
Enumerating objects: 6, done.
Counting objects: 100% (6/6), done.
Delta compression using up to 8 threads
Compressing objects: 100% (5/5), done.
Writing objects: 100% (6/6), 1.10 KiB | 1.10 MiB/s, done.
Total 6 (delta 0), reused 0 (delta 0), pack-reused 0
To github.com-personal:senthilkumarm1901/fun-marvel-git-tutorial.git
 * [new branch]      main -> main
branch 'main' set up to track 'origin/main'.

# remote branches
LeadScriptWriter@terminal fun-marvel-git-tutorial % git branch -r                           
  origin/main

# local branches
LeadScriptWriter@terminal fun-marvel-git-tutorial % git branch
* main
```

---

## III. Writer 1's Efforts

- Cloned the repo and created branch `writer1/avengers`
- Made following 3 commits

```bash
Writer1@terminal fun-marvel-git-tutorial % git log --oneline --all | head -n 4
2341887 Writer1: add DeadPool story arc
f67079b Writer1: add stories about other main avengers
a5d8353 Writer1: add stories about main avengers
df27d59 LeadScriptWriter: push all local efforts to main
```

```bash
Writer1@terminal fun-marvel-git-tutorial % cat marvel_heroes.md 
> This is the file where all stories of different heroes converge

## About the Main Avengers
- **Iron Man:** Created the Iron Man suit and saved himself from captivity.
- **Captain America:** Led the charge against Hydra during WWII and became a symbol of hope.
- **Thor:** Defended Asgard and Earth, wielding Mjolnir with unshakable valor.

## Other Main Avengers
- **Hulk:** Balanced a life of science with his uncontrollable strength to smash enemies.
- **Hawkeye:** The marksman with unerring aim, standing tall against gods and monsters armed with nothing but a bow and arrow.
- **Black Widow:** The spy turned Avenger, weaving through shadows with unmatched skill and unwavering loyalty.

- **DeadPool**: The superhero who cannot die and can be a formidable foe to any villain
```

- Push the changes to remote.

```bash
Writer1@terminal fun-marvel-git-tutorial % git push origin writer1/avengers
Enumerating objects: 11, done.
Counting objects: 100% (11/11), done.
Delta compression using up to 8 threads
Compressing objects: 100% (9/9), done.
Writing objects: 100% (9/9), 1.32 KiB | 1.32 MiB/s, done.
Total 9 (delta 2), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (2/2), done.
To github.com-personal:senthilkumarm1901/fun-marvel-git-tutorial.git
   df27d59..2341887  writer1/avengers -> writer1/avengers
```

- Raise a Pull Request

![](ready_for_PR.png)
![alt text](PR_page.png)


- LeadScriptWriter in the PR suggested `git reset --hard HEAD~1` which the Writer 1 followed  

```
LeadScriptWriter:

- Please remove Deadpool commit and changes from your branch.
- Since you are the only one using your branch do git reset --hard f67079b (which ignores 2341887) and then force push the changes to you branch
- Then I will merge with main
```

```bash
Writer1@terminal fun-marvel-git-tutorial % git reset --hard f67079b
HEAD is now at f67079b Writer1: add stories about other main avengers
Writer1@terminal fun-marvel-git-tutorial % git log --oneline --all 
836bda1 (refs/stash) WIP on writer1/avengers: f67079b Writer1: add stories about other main avengers
876a01f index on writer1/avengers: f67079b Writer1: add stories about other main avengers
2341887 (origin/writer1/avengers) Writer1: add DeadPool story arc
f67079b (HEAD -> writer1/avengers) Writer1: add stories about other main avengers
a5d8353 Writer1: add stories about main avengers
df27d59 (origin/writer3/endgame, origin/writer2/others, origin/main, origin/HEAD, main) LeadScriptWriter: push all local efforts to main
6e20a67 LeadScriptWriter: create a file to collate all stories
8c3d5c5 LeadScriptWriter: set initial context to the other 3 writers
Writer1@terminal fun-marvel-git-tutorial % git push --force 
Total 0 (delta 0), reused 0 (delta 0), pack-reused 0
To github.com-personal:senthilkumarm1901/fun-marvel-git-tutorial.git
 + 2341887...f67079b writer1/avengers -> writer1/avengers (forced update)
```

![alt text](3_commits_reduced_to_2.png)


> Pull Request accepted
> The branch is not deleted (that is just a preference by the LeadScriptWriter, incase more is needed in future). 


---

- How does it look for `LeadScriptWriter` when he `git fetch origin` and `git pull` in his `main` branch

```bash
LeadScriptWriter@terminal fun-marvel-git-tutorial % git log --oneline --all --decorate --graph
*   9729c21 (origin/main) Merge pull request #1 from senthilkumarm1901/writer1/avengers
|\  
| * 4759971 (origin/writer1/avengers) Writer1: Efforts of 1 are pushed to the writer1 branch
| * f67079b Writer1: add stories about other main avengers
| * a5d8353 Writer1: add stories about main avengers
|/  
* df27d59 (HEAD -> main, origin/writer3/endgame, origin/writer2/others) LeadScriptWriter: push all local efforts to main
* 6e20a67 LeadScriptWriter: create a file to collate all stories
* 8c3d5c5 LeadScriptWriter: set initial context to the other 3 writers
```

---