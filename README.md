# Shi Li's Personal Homepage

Source for [xemcerk.github.io](https://xemcerk.github.io). Built with Jekyll and the [Minimal Mistakes](https://mmistakes.github.io/minimal-mistakes/) theme.

## Local Development (macOS)

The system Ruby bundled with macOS is too old. Use [rbenv](https://github.com/rbenv/rbenv) for a modern Ruby version.

**1. Install rbenv and Ruby 3.3**

```bash
brew install rbenv ruby-build
rbenv install 3.3.0
rbenv local 3.3.0
```

**2. Add rbenv to your shell** — add to `~/.zshrc` if not already present, then restart the terminal:

```bash
eval "$(rbenv init - zsh)"
```

**3. Install dependencies and serve**

```bash
gem install bundler
bundle install
bundle exec jekyll serve
```

Site runs at **http://localhost:4000**. Use `--livereload` to auto-refresh on changes.

# Changelog -- bugfixes and enhancements

There is one logistical issue with a ready-to-fork template theme like academic pages that makes it a little tricky to get bug fixes and updates to the core theme. If you fork this repository, customize it, then pull again, you'll probably get merge conflicts. If you want to save your various .yml configuration files and markdown files, you can delete the repository and fork it again. Or you can manually patch. 

To support this, all changes to the underlying code appear as a closed issue with the tag 'code change' -- get the list [here](https://github.com/academicpages/academicpages.github.io/issues?q=is%3Aclosed%20is%3Aissue%20label%3A%22code%20change%22%20). Each issue thread includes a comment linking to the single commit or a diff across multiple commits, so those with forked repositories can easily identify what they need to patch.
