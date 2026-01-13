# Rocker

Rocker is a docker explorer script.\
Tired of messing with docker cli? Rocker is here to help you.
Inspired by [Macho](https://hiphish.github.io/blog/2020/05/31/macho-man-command-on-steroids/).

![rocker](https://github.com/yell0w4x/assets/raw/main/rocker.gif)

## Prerequisites

- docker
- [fzf](https://github.com/junegunn/fzf)
- bat (optional, if installed preview will be colored)

## Installation

```bash
sudo wget https://raw.githubusercontent.com/yell0w4x/rocker/refs/heads/main/rocker -O /usr/local/bin/rocker && \
    sudo chmod +x /usr/local/bin/rocker
```

## Usage

```
$ rocker --help
Rocker is a docker explorer script.
Tired of messing with docker cli? Rocker is here to help you.

Usage:
    rocker [OPTIONS] [COMMAND] [SUBCOMMAND] -- [DOCKER_OPTIONS]

Prerequisites:
    - docker
    - fzf
    - bat (optional, if installed preview will be colored)

Commands:
    ps               List and optionally stop/start/remove containers (default command)
    images           List and optionally remove images
    volumes          List and optionally remove volumes
    networks         List and optionally remove networks

Subcommands:
    rm               Remove containers, images, volumes and networks. 
                     Default for images, volumes and networks.
    start            Start stopped containers.
                     For starting --assume-yes is implied.
    stop             Stop running containers. Default for containers.
                     For stopping --assume-yes is implied.

Options:
    -y,--assume-yes  Do not prompt for confirmation on executing 
                     underlying docker commands.

Keybindings:
    Tab/Shift-Tab  Select/deselect item
    Esc/Ctrl-Q     Exit
    Enter          Confirm selection

Notes:
    Override BAT_THEME environment variable to change the theme of bat.
    Docker options are passed to the underlying docker command.

Examples:
    List containers and stop selected ones.

        rocker ps

    List containers and remove selected ones.

        rocker ps rm

    List images and remove selected ones.

        rocker images

    List images and remove selected ones without prompting.

        rocker images -y

    List images and remove selected ones passing --force to docker.

        rocker images -- --force
```
