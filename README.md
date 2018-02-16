## How to create a new blog page

To create a new blog you will need to create a new ```.md``` file in the folder ```_posts```. This file will then need to be save using the following name format ```YYYY-MM-DD-post-name.md```. Where the file has been created you will then need to use markup to create the content. You can find a guide for markdown language [**here**](https://guides.github.com/features/mastering-markdown/)

## Setup to allow you to install Jekyll locally
To install Jekyll locally you will need to update ruby on rails to do this you will need to do the following.

1. Setup your console to use zsh instead of bash
```bash
chsh -s /usr/local/bin/zsh
```

2. Update brew and install rbenv
```bash
brew update
brew install rbenv
rbenv init
```

3. You need to copy this onto your ```.zshrc``` file
```bash
export PATH="$HOME/.rbenv/shims:${PATH}"
export RBENV_SHELL=zsh
export NVM_DIR="$HOME/.nvm"
[ -s "/usr/local/opt/nvm/nvm.sh" ] && . "/usr/local/opt/nvm/nvm.sh" # This loads nvm
eval "$(rbenv init -)"
command rbenv rehash 2>/dev/null
rbenv() {
  local command
  command="$1"
  if [ "$#" -gt 0 ]; then
    shift
  fi

  case "$command" in
  rehash|shell)
    eval "$(rbenv "sh-$command" "$@")";;
  *)
    command rbenv "$command" "$@";;
  esac
}
```

4. And then run the following code in you console
```bash
brew update && brew upgrade ruby-build
rbenv install 2.4.2
rbenv global 2.4.2
```

## Local Development

1. Install Jekyll and plug-ins in one fell swoop. `gem install github-pages` This mirrors the plug-ins used by GitHub Pages on your local machine including Jekyll, Sass, etc.
2. Clone down your fork `git@github.com:nearmap/nearmap.github.io.git` this will link to you ssh keys
3. Serve the site and watch for markup/sass changes `jekyll serve`
4. View your website at http://127.0.0.1:4000/
5. Commit any changes and push everything to the master branch of your GitHub user repository. GitHub Pages will then rebuild and serve your website.

## Moar!

If you are interested you can find a more detailed walkthrough, [**Build A Blog With Jekyll And GitHub Pages**](http://www.smashingmagazine.com/2014/08/01/build-blog-jekyll-github-pages/) over at the Smashing Magazine website. Check it out if you'd like a more detailed walkthrough and some background on Jekyll. :metal:

It covers:

- A more detailed walkthrough of setting up your Jekyll blog
- Common issues that you might encounter while using Jekyll
- Importing from Wordpress, using your own domain name, and blogging in your favorite editor
- Theming in Jekyll, with Liquid templating examples
- A quick look at Jekyll 2.0’s new features, including Sass/Coffeescript support and Collections