# User Personas

This repo is still in development and is not yet ready for use as a reference.

*Changes and Updates* that need to be completed are logged under 'issues'.

## Changing Persona Details

Install Node.js and npm (Node Package Manager) if you don't have it already 
[npm-docs: installing node and npm](https://docs.npmjs.com/getting-started/installing-node)

Install harp (optionally with the global flag)
```
$ sudo npm install -g harp
```
---

**Start the server** to see the output in your browser

```
$ harp server _personas
```
which should generate:
```
------------
Harp v0.15.2 – Chloi Inc. 2012–2015
Your server is listening at http://localhost:9000/
Press Ctl+C to stop the server
------------
```
---

**Update the profiles** by editing the data stored in
```
_data.json
```
---
**Commit you changes** and **make a pull request.**

## Production

As a [harpjs](https://github.com/sintaxi/harp) project served through gh-pages there is a *very strict* process for production.
The **master** branch is the main branch for editing and updating the code.
The **gh-pages** branch is compiled and has no `README.md`. This is because harp compiles all pre-processors and clears the destination folder, which for github pages' purposes, is the root. 

For production please follow these steps:

1. fetch the gh-pages branch / pull for updates to the branch.
2. pull and merge the updated master branch (after any pull requests have been resolved) into the gh-pages branch
  2.1. If, when you run `git merge master` you receive the following message:
```
CONFLICT (modify/delete): README.md deleted in HEAD and modified in master. Version master of README.md left in tree.
Automatic merge failed; fix conflicts and then commit the result.
```
then simply remove the readme with `rm README.md` 
stage the removal for commit with `git add README.md`
and commit all changes.
3. from the root run 
    `$ harp compile _personas ./`
4. commit and push to the remote gh-pages branch

**NEVER run the `compile` command on master**. The command must be treated as a final step before publishing. 
