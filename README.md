# Oh Shit!

This app was heavily inspired by [nvbn/thefuck](https://github.com/nvbn/thefuck), so credit where credit is due. That being said, Oh Shit! aims to be an even more powerful, fast, and gratifying way to correct your shell mistakes. Since Oh Shit! is written in Crystal you should see a significant speed increse, and you don't need to worry about any Python!

**Note:** This is still in development. The below instructions do not work yet.

## Installation

For now, installation will require cloning this repo and building yourself. Binaries will be available in the future.

```shell
cd /opt
git clone https://github.com/watzon/ohshit
cd ohshit
crystal build --release
sudo ln -ls /opt/ohshit/bin/ohshit /usr/local/bin/ohshit
ohshit set-aliases
```

The `set-aliases` command will set an alias in your `.bashrc` and `.zshrc` files, allowing you to run Oh Shit! with the `shit` command instead of `ohshit`. To do this manually add the following to your shell configuration files.

```shell
alias shit='ohshit'
```

Don't forget to reload your configuration any time you make a change.

```shell
source ~/.zshrc
```

## Usage

Whenever you run an incorrect command on your terminal just follow it up with `shit` to have your mistake instantly corrected.

### Examples

```shell
➜ pacman -S vim
error: you cannot perform this operation unless you are root.

➜ shit
sudo pacman -S vim [enter/↑/↓/ctrl+c]
[sudo] password for watzon:
resolving dependencies...
...
```

```shell
➜ git push
fatal: The current branch master has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin master


➜ shit
git push --set-upstream origin master [enter/↑/↓/ctrl+c]
Counting objects: 2, done.
...
```

```shell
➜ git brnch
git: 'brnch' is not a git command. See 'git --help'.

The most similar command is
	branch

➜ shit
git branch [enter/↑/↓/ctrl+c]
* master
```

## Development

Feel free to help with issue tracking by [submitting an issue](https://github.com/watzon/ohshit/issues/new) if you run into one. Do remember that this is alpha software and comes with no assurances that it will work correctly.

Alternatively you can always fork this repo and do some coding yourself. I open all contributions and appreciate the effort.

## Contributing

1. Fork it (<https://github.com/watzon/ohshit/fork>)
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create a new Pull Request

## Contributors

- [Chris Watson](https://github.com/watzon) - creator and maintainer
