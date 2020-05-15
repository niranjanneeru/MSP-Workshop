# MSP - Workshop


## DAY - 2
---

## Git and Github

### Mentor: 
<table>
  <tr>
    <td align="center"><a href="https://github.com/thameemk612"><img src="https://avatars0.githubusercontent.com/u/33159840?s=400&u=4b94857eac651dcfaa0db2797cc381bb4ab34a99&v=4" width="100px" alt=""/><br /><sub><b>Thameem Karakkoth</b></sub></a></td>
  </tr>
</table>

---

## Contents

<ul style="list-style-type:circle">
   <li>Version Control System</li>
   <ol>
   <li>System keeps Track of Changes</li>
   <li>Track of Changes over time</li>
   <li>Collaborative development</li>
   </ol>
   <li>Version Control Systems</li>
   <ol>
   <li>Git</li>
   <li>Perforce</li>
   <li>Subversion</li>
   <li>Mercurial</li>
   </ol>
   <li>Git Working</li>
   <ol>
   <li>Snapshot(Changes at a point of time)Commit is the act of creating Snapshots</li>
   <li>Files Stored as Repo</li>
   <li>Cloning :Act of Copying Repo from remote server</li>
   <li>Pull: Downloading commits that don’t exist on
your machine</li>
<li>Push:  The process of adding your local changes to the remote
repository</li>
<li>Branch wise division and merging</li>
      </ol> 
</ul>


### Steps:-


Create a Repo with some name in github say "MSP"


Open git client or Terminal

```bash
$ git init
Initialized empty Git repository in <Some Location>

$ echo "# New Project " > README.md

$ echo "New LICENSE " > LICENSE

$ git add .
warning: LF will be replaced by CRLF in README.md.
The file will have its original line endings in your working directory

$ git status
On branch master
Your branch is up to date with 'origin/master'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   README.md
        modified:   LICENSE


$ git commit -m "initial commit"
[master 8fa8d6e] first commit
 1 file changed, 53 insertions(+), 1 deletion(-)


$ git remote add origin https://github.com/Niranjanprof/MSP.git

$ git remote
origin


$ git push -u origin master
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 12 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (4/4), 284 bytes | 94.00 KiB/s, done.
Total 4 (delta 0), reused 0 (delta 0)
To https://github.com/Niranjanprof/MSP.git
 * [new branch]      master -> master
Branch 'master' set up to track remote branch 'master' from 'origin'.




```

