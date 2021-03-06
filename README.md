# Crumbs

Crumbs is a command line utility for the shell, for storing commands under a meaningful name in a hierarchy

## Motivation

For web service tests I am used to sending a lot of HTTP Requests via `curl`. The command line invocation can be quite complex and long and I wanted to be able to organize them in a directory like structure. Also I wanted to have a context sensitive auto completion for the different command invocations.

## Why not us aliases?

Aliases do not allow a user to use foward slashes in the alias name in order to create complex hierarchies and therefore no context sensitive auto completion.

## Installation

1. Checkout the sources from github:
```bash
git clone https://github.com/fasseg/crumbs.git
```
2. Run the configure script
```bash
cd crumbs
./configure
```
3. Compile the program
```bash
make
```
4. Install the binaries and the man pages
```bash
sudo make install
```

For a more comprehensive installation documentation check the file INSTALL in the root directory

### Configuration file

The default configuration file is `/etc/crumbs.conf`. It contains the following settings:

`path`
>The path to use for storing data. If the path starts with a forward slash crumbs uses an absolute path to the configuration file. If the path is not starting with a forward slash the current user's home directory is prepended to the path.

A different configuration file can be used by invoking crumbs with the `--config` option
### Auto Completion

An auto completion file for the bash shell is included and installed in `/usr/local/share/crumbs/crumbs-completion.bash`. In order to enable the completion you can copy the file `crumbs-completion.bash` to e.g. `/usr/local/share/crumbs/` and source in your `.bashrc` file:
```bash
echo "source /usr/local/share/crumbs/crumbs-completion.bash" >> ~/.bashrc

```

### Usage

You can check the help dialog of the program or the man page for usage documentation and some examples:
```bash
crumbs --help 
man crumbs

```
