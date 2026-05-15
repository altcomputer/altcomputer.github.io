# Alt Computer

This repository host the contents of **Alt Computer** blog. It's using [Hugo](https://gohugo.io/) and [Terminal](https://github.com/panr/hugo-theme-terminal) theme.

## Run in `dev` machine

To run this repository in local, first run `setup.sh` script to get the Terminal theme sub module and then run the Hugo server as follow,

```bash
$ hugo server
```

To see the changes on a draft blog post run,

```bash
$ ./watch.sh
```

## Build the blog

To generate the static content, just run:

```bash
$ hugo
```

## Add a new post

To add a new post use `hugo` command like below,

```bash
$ hugo new post/[name-of-the-post.md]
```

## Add a new page

To add a new page:

```bash
$ hugo new [about.md]
```

Then edit:

```bash
$ vim content/about.md
```

## Add a new menu

Menu should be added manually in `hugo.toml`, under `[languages.en.menu]`
section.

## Contact
* kasra@madadipouya.com

