# Zulu

Zulu is a total environment manager for ZSH.

## Features

* No need to modify config files or reload ZSH when installing packages, creating aliases or modifying your `$PATH`.
* Any git repository can be a package, check out [the index](//github.com/zulu-zsh/index) and [contribute](//github.com/zulu-zsh/zulu/blob/master/CONTRIBUTING.md).

## Installation

### One-liner

```sh
curl https://raw.githubusercontent.com/zulu-zsh/install/master/install | zsh && zsh
```

### For the cautious

```sh
git clone https://github.com/zulu-zsh/install zulu-install
chmod u+x zulu-install/install
. ./zulu-install/install
```

## Usage

### Managing packages

Packages are found in the [index](//github.com/zulu-zsh/index). Each package defines its own list of executables (which are symlinked into `$PATH`), shared files (which are symlinked to `$fpath`) and files which should be loaded during environment initialisation. Unlike other package managers, zulu handles everything for you, so things should work as soon as the package finishes installing.

```sh
# Install a package
zulu install autosuggestions

# Disable a package
zulu unlink autosuggestions

# Link (enable) a package
zulu link autosuggestions

# Uninstall a package
zulu uninstall autosuggestions

# List installed packages
zulu list
```

Zulu intelligently autocompletes package names for you when using any of the above commands

### Managing `$PATH` and `$fpath`

Zulu can manage the list of directories in `$PATH` and `$fpath` for you, negating the need for modifying init files and reloading the environment.

```sh
# Add a directory to $PATH
zulu path add /path/to/dir

# Remove a directory from $fpath
zulu fpath rm /path/to/dir

# List all directories in $PATH
zulu path
```

### Managing aliases

Zulu can also manage your aliases.

```sh
# Add an alias
zulu alias add l 'k -ha'

# Remove an alias
zulu alias rm l

# List aliases
zulu alias
```

### Choosing a theme

Zulu can switch themes for you, and will load the chosen theme on next login.

```sh
zulu install filthy
zulu theme filthy
```

### Updating Zulu

```sh
# Update zulu's core
zulu self-update

# Update the package index
zulu update
```

## Contributing

All contributions are welcome, and encouraged. Please read our [contribution guidelines] and [code of conduct] for more information.

## License

Copyright (c) 2016 James Dinsdale <hi@molovo.co> (molovo.co)

Zulu is licensed under The MIT License (MIT)

## Team

* [James Dinsdale](http://molovo.co)