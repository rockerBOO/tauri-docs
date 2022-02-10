---
id: cli
title: CLI
---

import Command from '@theme/Command'
import Alert from '@theme/Alert'

The `cli.js` command line interface is composed in TypeScript and published as a JavaScript NPM. It offers the `deps` and the `icon` commands, and propagates other commands to `cli.rs`.

## `info`

<Command name="info" />

```
Command line interface for building Tauri apps

USAGE:
    cargo-tauri <SUBCOMMAND>

OPTIONS:
    -h, --help       Print help information
    -V, --version    Print version information

SUBCOMMANDS:
    build     Tauri build
    dev       Tauri dev
    help      Print this message or the help of the given subcommand(s)
    info      Shows information about Tauri dependencies and project configuration
    init      Initializes a Tauri project
    plugin    Manage Tauri plugins
    signer    Tauri updater signer
```

It shows a concise list of information about the environment, Rust, Node.js and their versions as well as some relevant configurations.

<Alert title="Note" icon="info-alt">
This command is pretty helpful when you need to have a quick overview of your application. When requesting some help, it can be useful that you share this report with us.
</Alert>

## `init`

<Command name="init" />

```
Command line interface for building Tauri apps

USAGE:
    cargo-tauri <SUBCOMMAND>

OPTIONS:
    -h, --help       Print help information
    -V, --version    Print version information

SUBCOMMANDS:
    build     Tauri build
    dev       Tauri dev
    help      Print this message or the help of the given subcommand(s)
    info      Shows information about Tauri dependencies and project configuration
    init      Initializes a Tauri project
    plugin    Manage Tauri plugins
    signer    Tauri updater signer
```

## `dev`

<Command name="dev" />

```
Command line interface for building Tauri apps

USAGE:
    cargo-tauri <SUBCOMMAND>

OPTIONS:
    -h, --help       Print help information
    -V, --version    Print version information

SUBCOMMANDS:
    build     Tauri build
    dev       Tauri dev
    help      Print this message or the help of the given subcommand(s)
    info      Shows information about Tauri dependencies and project configuration
    init      Initializes a Tauri project
    plugin    Manage Tauri plugins
    signer    Tauri updater signer
```

This command will open the WebView in development mode. It makes use of the `build.devPath` property from your `src-tauri/tauri.conf.json` file.

If you have entered a command to the `build.beforeDevCommand` property, this one will be executed before the `dev` command.

<a href="/docs/api/config#build">See more about the configuration.</a><br/><br/>

<Alert title="Troubleshooting" type="warning" icon="alert">

If you're not using `build.beforeDevCommand`, make sure your `build.devPath` is correct and, if using a development server, that it's started before using this command.
</Alert>

## `deps`

<Command name="deps" />

{deps}

## `build`

<Command name="build" />

```
Command line interface for building Tauri apps

USAGE:
    cargo-tauri <SUBCOMMAND>

OPTIONS:
    -h, --help       Print help information
    -V, --version    Print version information

SUBCOMMANDS:
    build     Tauri build
    dev       Tauri dev
    help      Print this message or the help of the given subcommand(s)
    info      Shows information about Tauri dependencies and project configuration
    init      Initializes a Tauri project
    plugin    Manage Tauri plugins
    signer    Tauri updater signer
```

This command will bundle your application, either in production mode or debug mode if you used the `--debug` flag. It makes use of the `build.distDir` property from your `src-tauri/tauri.conf.json` file.

If you have entered a command to the `build.beforeBuildCommand` property, this one will be executed before the `build` command.

<a href="/docs/api/config#build">See more about the configuration.</a>

## `icon`

<Command name="icon" />

```
  Description
    Create all the icons you need for your Tauri app.

  Usage
    $ tauri icon /path/to/icon.png

  Options
    --help, -h           Displays this message
    --log, -l            Logging [boolean]
    --target, -t         Target folder (default: 'src-tauri/icons')
    --compression, -c    Compression type [optipng|zopfli]
    --ci                 Runs the script in CI mode     
```

This command will generate a set of icons, based on the source icon you've entered. Note that the source icon must be 1240x1240 with transparency.

## `version`

<Command name="--version" />

```
  Description
    Returns the current version of tauri
```

This command will show the current version of Tauri.

## CLI usage

See more about the usage through this [complete guide](/docs/development/integration).
