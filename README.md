# moonstone-ink.nl

Website for [Moonstone Ink](https://moonstone-ink.nl), using the very fast and flexible static site generator called Hugo

## Licenses

All code is licensed under GPLv3.

All photographs and artworks are licensed under the [Creative Commons attribution NonCommercial (CC BY-NC)](https://creativecommons.org/licenses/by-nc/4.0/):
*This license lets others remix, adapt, and build upon your work non-commercially, and although their new works must also acknowledge you and be non-commercial, they don’t have to license their derivative works on the same terms.*

## Getting Started

Start by cloning the repository:

```bash
git clone git@github.com:jbouter/moonstone-ink.nl.git
cd moonstone-ink.nl
```

### Initial set-up

This is only required for first setting up the repository.

Steps are based off of the [official documentation](https://gohugo.io/hosting-and-deployment/hosting-on-github/#preparations-for-gh-pages-branch)

Add the public directory to your gitignore

```bash
echo "public" >> .gitignore
```

Set up `gh-pages` as an empty orphan branch

```bash
git checkout --orphan gh-pages
git reset --hard
git commit --allow-empty -m "Initializing gh-pages branch"
git push upstream gh-pages
git checkout main
```


### Working with this setup

Check out the `gh-pages` branch into the `public` folder using git's [worktree feature](https://git-scm.com/docs/git-worktree). Essentially, the worktree allows you to have multiple branches on the same local repoistory to be checked out in different directories:

```bash
git worktree add -B gh-pages public origin/gh-pages
```

Regenerate the site using the `hugo` command and commit the generated files on the `gh-pages` branch:

```bash
hugo
cd public
git add --all
git commit -sm "Publishing to gh-pages"
```

If the changes on the local `gh-pages` branch look alright, push them to the remote repo:

```bash
git push origin gh-pages
```
