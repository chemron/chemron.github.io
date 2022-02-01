---
layout: post
title: "Automatically adding bear notes to a website."
---

## The Problem
I take notes using the great markdown editor [Bear](https://bear.app/), and
would like these notes to be backed up, as well as for specific notes to be
displayed on my website. On my notetaking device, I have a git repo for the
backed up notes and a seperate one for the website.
## The solution
To extract the markdown notes from bear, I use
[backup-bear-notes](https://github.com/TehShrike/backup-bear-notes). This can be
installed via

```bash
npm i -g backup-bear-notes
```

Next, I define useful variables in my `.zshrc` file (`.bashrc` for linux)

```bash
echo 'export bear_path="/path/to/backup/repo"' >> .zshrc
echo 'export website_path="/path/to/website/repo"' >> .zshrc
```

With this set up, we can now automatically add bear notes to the website with
the following script.

<script src="https://gist.github.com/chemron/aca1be7b8708f9ecde63836d36f9c19e.js"></script>