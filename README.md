# My dotfiles

This directory contains the dotfiles for my system. 

## Requirements

Ensure you have the following installed on your system:

### Git, Stow & Make (optional)

On Arch and Debian:

```bash
sudo pacman -S git
sudo pacman -S stow
sudo pacman -S make
```

On Ubuntu:

```bash
sudo apt install git
sudo apt install stow
sudo apt install make
```

On RHEL-based systems (RedHat Enterprise Linux, Fedora, CentOS, Oracle Linux, Rocky, etc.)

```bash
sudo dnf install git
sudo dnf install stow
sudo dnf install make
```


## Installation

First, check out the dotfiles repo in your $HOME directory using git:

```bash
git clone git@github.com:101br03k/dotfiles.git ~/.dotfiles 
cd dotfiles
```

Then use GNU stow to create symlinks (-v makes stow tell us what it's doing while it's doing it):

```bash
stow -v .
```

You can also watch the video from [Dreams of Autonomy](https://www.youtube.com/@dreamsofautonomy) about Stow: [Stow has forever changed the way I manage my dotfiles](https://www.youtube.com/watch?v=y6XCebnB9gs) and the [git repo](https://github.com/dreamsofautonomy/dotfiles) where this one is inspired by, together with the Makefile from [rmonin](https://github.com/rmonin/dotfles/blob/main/Makefile) on GitHub.


## Makefile usage

## Usage

The `make` command provides several targets for managing the dotfiles run `make help` to know usage:

```
USAGE

  make [target]

TARGETS

  stow    - Create symlinks for all packages (default)
  restow  - Reapply symlinks for all packages
  unstow  - Remove symlinks for all packages (caution)
  help    - Show this help message
```

> **Notice**
> Please use caution when applying or removing symlinks, especially when using the `unstow` target, as it can potentially overwrite existing configurations. Always review the changes before proceeding.
> See https://github.com/aspiers/stow/issues/33

### Structure

You can organize each content like below and launch `PACKAGES="configs" make`

```
.dotfiles/
├─ bash/
│  ├─ .bashrc
│  ├─ .bash_profile
│  ╰─ .bash_logout
├─ uzbl/
│  ├─ .config/
│  │  ╰─ uzbl/
│  │     ╰─ [...some files]
│  ╰─ .local/
│     ╰─ share/
│        ╰─ uzbl/
│           ╰─ [...some files]
╰─ vim/
   ├─ .vim/
   │  ╰─ [...some files]
   ╰─ .vimrc
```

<details><summary><b>Other way</b></summary>

You can alternatively put everything messy on a configs _package_ (or whatever you want)

```
.dotfiles/
╰─ configs/
   ├─ .bashrc
   ├─ .bash_profile
   ├─ .bash_logout
   ├─ uzbl/
   │  ╰─ [...some files]
   ├─ .local/
   │  ╰─ share/
   │     ╰─ uzbl/
   │        ╰─ [...some files]
   ├─ .vim/
   │  ╰─ [...some files]
   ╰─ .vimrc
```

> **NOT WORKING**
> According to Stow documentation, the Makefile manage also `--dotfiles` option, so you can also use _dot-_ prefix if you do not want hidden content on your project :
>
> ```
> dotfles/
> ╰─ configs/
>    ├─ dot-bashrc
>    ├─ dot-bash_profile
>    ├─ dot-bash_logout
>    ├─ uzbl/
>    │  ╰─ [...some files]
>    ├─ dot-local/
>    │  ╰─ share/
>    │     ╰─ uzbl/
>    │        ╰─ [...some files]
>    ├─ dot-vim/
>    │  ╰─ [...some files]
>    ╰─ dot-vimrc
> ```

</details>
