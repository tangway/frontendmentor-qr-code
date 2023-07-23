# Frontend Mentor - QR code component solution

## Table of contents

- [Overview](#overview)
  - [Screenshot](#screenshot)
  - [Links](#links)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
  - [Useful resources](#useful-resources)
- [Author](#author)


## Overview

This is a solution to the [QR code component challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/qr-code-component-iux_sIO_H). Frontend Mentor challenges help to improve your coding skills by building realistic projects. 

### Screenshot

![](./screenshot.png)


### Links

- Solution URL: [Github Repo](https://github.com/tangwwwei/frontendmentor-qr-code)
- Live Site URL: [Github Pages](https://tangwwwei.github.io/frontendmentor-qr-code/)

### Built with

- Semantic HTML5 markup
- Flexbox
- Mobile-first workflow

### What I learned

- This challenge was just right for me in terms of difficulty as I came from Odin project fundamentals, it gave me just the right amount of frustration and subsequent satisfaction from learning to solve it :D
  - Starting from an almost blank css page was daunting but looking at what I've built from there feels good.
- The whole process from the start where: 
  - you are given a design to replicate 
  - have to push your work to github 
  - review what you've done and write (this) documentation on findings 
  - presenting to your team (in this case the frontendmentor community at large) 
- All of the above mimic what a developer would do on a team in the real world. 
  - On first impression I thought it was an overly long process ("yoo i just wanna do the exercise and get feedback!")

- Learnings from the more technical side of things:
  - To center a container that is a direct child of the body element:
  ```css
  html, body {
    height: 100%;
  }
  
  body {
    display:flex;
    align-items: center;
    justify-content: center;
  }
  ```
	- `height:100%` vs `height:100vh`
		- `height:100%` means 100% of the parent element's height
			- To use it to have the same effect as `body {height:100vh}` you need to set its parent's height too since by default it is not defined, so `html, body {height:100%}` will work
			- However, it's important to note that `vh` might not always behave as expected, especially on mobile devices. For instance, some mobile browsers calculate the viewport height once, including the space taken by the URL bar at the top of the screen. When the user scrolls and the URL bar disappears, the viewport height changes, but the `vh` unit does not get updated, leading to unexpected results. In this case, using `height: 100%` might be more reliable, but only if you set `height: 100%` on both the `html` and `body` tags
		- `height:100vh`
			- `vh` stands for viewport height. It is a relative unit of measure, which means it's relative to the viewport.
			- `100vh` therefore means 100% of the viewport height.
  - I had a big problem with linking my local repo to the empty repo I created on github. This was how I fixed it:
    - `git init` your directory, `git add .` all files to staging and make your first commit if you havn't already
    - create new totally empty repo on github
    - copy the SSH link
    - link local to remote using `git remote add origin (SSH link)`
      - you can check the list of remote repos linked using `git remote -v`. you can also set a new remote using `git remote set-url origin (SSH link)`
    - `git branch -M main`
      - optional as later versions of git all initialize with `main` branch rather than `master`
      - The `-M` option is a combination of `--move --force` as per the Git documentation. This command allows the renaming of the branch even if the new branch name already exists
      - This could be useful in situations such as changing the default branch name from `master` to `main` in line with recent changes in naming conventions within the developer community.
    - `git push --set-upstream origin main` or the more common `git push -u origin main`
      - the `-u` option tells Git to set the upstream for the local branch to `origin/<branch name>`, which means that future `git pull` commands without arguments will fetch and merge changes from `origin/<branch name>` into the current local branch. it is the same as `--set-upstream`
      - the term `origin` refers to the default name given to the remote repository from which you cloned. This is part of Git's concept of "remotes", which are essentially nicknames for a repository's full URL, allowing you to refer to another repository without having to input its full URL each time. When you clone a repository for the first time using `git clone`, Git will automatically set up a remote called `origin` to refer to the URL that you cloned from. when you use `git remote -v` you will see the remote referred to as `origin`
    - if you encounter error `failed to push some refs to (your repo) Updates were rejected because the remote contains work that you do not have locally` and it recommends to use `git pull`...
      - `git config pull.rebase true` since the remote origin is empty. This will apply your local changes on top of the remote changes (which don't exist since the repository is empty).
      - then `git pull origin main` to pull the changes from the remote repository (which won't have any effect since it's empty)
      - and finally `git push origin main`
  - Got reminded of how easy it is to import fonts into css using `@import url("https://fonts.googleapis.com/css2?family=Outfit:wght@400;700&display=swap");`

### Continued development

- Still unsure about when to use `em` or `rem`. I've stuck to using `em` for all non-font dimensions.
- Unsure about `max-width: 20rem;` for the main component. Using it is the only way i know how to keep the size same for small and wide width screens

### Useful resources

- [What does it mean to "make a site responsive"? - FED Mentor](https://fedmentor.dev/posts/responsive-meaning/) - This helped me to build from mobile-first and to switched to using relative units for everything.
- [Why font-size must NEVER be in pixels - FED Mentor](https://fedmentor.dev/posts/font-size-px/) - Learnt to use `rem` units for font sizing

## Author

- Frontend Mentor - [@tangwwwei](https://www.frontendmentor.io/profile/tangwwwei)


