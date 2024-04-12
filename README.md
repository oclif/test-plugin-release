@oclif/test-plugin-release
=================

Plugin for testing GHA for oclif templates

[![oclif](https://img.shields.io/badge/cli-oclif-brightgreen.svg)](https://oclif.io)
[![GitHub license](https://img.shields.io/github/license/oclif/plugin-test-release)](https://github.com/oclif/plugin-test-release/blob/main/LICENSE)

<!-- toc -->
* [Usage](#usage)
* [Commands](#commands)
<!-- tocstop -->
# Usage
<!-- usage -->
```sh-session
$ npm install -g @oclif/test-plugin-release
$ oex COMMAND
running command...
$ oex (--version)
@oclif/test-plugin-release/v5.0.7 linux-x64 node-v18.20.1
$ oex --help [COMMAND]
USAGE
  $ oex COMMAND
...
```
<!-- usagestop -->
# Commands
<!-- commands -->
* [`oex hello PERSON`](#oex-hello-person)
* [`oex hello world`](#oex-hello-world)
* [`oex help [COMMAND]`](#oex-help-command)
* [`oex plugins`](#oex-plugins)
* [`oex plugins add PLUGIN`](#oex-plugins-add-plugin)
* [`oex plugins:inspect PLUGIN...`](#oex-pluginsinspect-plugin)
* [`oex plugins install PLUGIN`](#oex-plugins-install-plugin)
* [`oex plugins link PATH`](#oex-plugins-link-path)
* [`oex plugins remove [PLUGIN]`](#oex-plugins-remove-plugin)
* [`oex plugins reset`](#oex-plugins-reset)
* [`oex plugins uninstall [PLUGIN]`](#oex-plugins-uninstall-plugin)
* [`oex plugins unlink [PLUGIN]`](#oex-plugins-unlink-plugin)
* [`oex plugins update`](#oex-plugins-update)

## `oex hello PERSON`

Say hello

```
USAGE
  $ oex hello PERSON -f <value>

ARGUMENTS
  PERSON  Person to say hello to

FLAGS
  -f, --from=<value>  (required) Who is saying hello

DESCRIPTION
  Say hello

EXAMPLES
  $ oex hello friend --from oclif
  hello friend from oclif! (./src/commands/hello/index.ts)
```

_See code: [src/commands/hello/index.ts](https://github.com/oclif/test-plugin-release/blob/vv5.0.7/src/commands/hello/index.ts)_

## `oex hello world`

Say hello world

```
USAGE
  $ oex hello world

DESCRIPTION
  Say hello world

EXAMPLES
  $ oex hello world
  hello world! (./src/commands/hello/world.ts)
```

_See code: [src/commands/hello/world.ts](https://github.com/oclif/test-plugin-release/blob/vv5.0.7/src/commands/hello/world.ts)_

## `oex help [COMMAND]`

Display help for oex.

```
USAGE
  $ oex help [COMMAND...] [-n]

ARGUMENTS
  COMMAND...  Command to show help for.

FLAGS
  -n, --nested-commands  Include all nested commands in the output.

DESCRIPTION
  Display help for oex.
```

_See code: [@oclif/plugin-help](https://github.com/oclif/plugin-help/blob/v6.0.20/src/commands/help.ts)_

## `oex plugins`

List installed plugins.

```
USAGE
  $ oex plugins [--json] [--core]

FLAGS
  --core  Show core plugins.

GLOBAL FLAGS
  --json  Format output as json.

DESCRIPTION
  List installed plugins.

EXAMPLES
  $ oex plugins
```

_See code: [@oclif/plugin-plugins](https://github.com/oclif/plugin-plugins/blob/v5.0.7/src/commands/plugins/index.ts)_

## `oex plugins add PLUGIN`

Installs a plugin into oex.

```
USAGE
  $ oex plugins add PLUGIN... [--json] [-f] [-h] [-s | -v]

ARGUMENTS
  PLUGIN...  Plugin to install.

FLAGS
  -f, --force    Force npm to fetch remote resources even if a local copy exists on disk.
  -h, --help     Show CLI help.
  -s, --silent   Silences npm output.
  -v, --verbose  Show verbose npm output.

GLOBAL FLAGS
  --json  Format output as json.

DESCRIPTION
  Installs a plugin into oex.

  Uses bundled npm executable to install plugins into /home/runner/.local/share/oex

  Installation of a user-installed plugin will override a core plugin.

  Use the OEX_NPM_LOG_LEVEL environment variable to set the npm loglevel.
  Use the OEX_NPM_REGISTRY environment variable to set the npm registry.

ALIASES
  $ oex plugins add

EXAMPLES
  Install a plugin from npm registry.

    $ oex plugins add myplugin

  Install a plugin from a github url.

    $ oex plugins add https://github.com/someuser/someplugin

  Install a plugin from a github slug.

    $ oex plugins add someuser/someplugin
```

## `oex plugins:inspect PLUGIN...`

Displays installation properties of a plugin.

```
USAGE
  $ oex plugins inspect PLUGIN...

ARGUMENTS
  PLUGIN...  [default: .] Plugin to inspect.

FLAGS
  -h, --help     Show CLI help.
  -v, --verbose

GLOBAL FLAGS
  --json  Format output as json.

DESCRIPTION
  Displays installation properties of a plugin.

EXAMPLES
  $ oex plugins inspect myplugin
```

_See code: [@oclif/plugin-plugins](https://github.com/oclif/plugin-plugins/blob/v5.0.7/src/commands/plugins/inspect.ts)_

## `oex plugins install PLUGIN`

Installs a plugin into oex.

```
USAGE
  $ oex plugins install PLUGIN... [--json] [-f] [-h] [-s | -v]

ARGUMENTS
  PLUGIN...  Plugin to install.

FLAGS
  -f, --force    Force npm to fetch remote resources even if a local copy exists on disk.
  -h, --help     Show CLI help.
  -s, --silent   Silences npm output.
  -v, --verbose  Show verbose npm output.

GLOBAL FLAGS
  --json  Format output as json.

DESCRIPTION
  Installs a plugin into oex.

  Uses bundled npm executable to install plugins into /home/runner/.local/share/oex

  Installation of a user-installed plugin will override a core plugin.

  Use the OEX_NPM_LOG_LEVEL environment variable to set the npm loglevel.
  Use the OEX_NPM_REGISTRY environment variable to set the npm registry.

ALIASES
  $ oex plugins add

EXAMPLES
  Install a plugin from npm registry.

    $ oex plugins install myplugin

  Install a plugin from a github url.

    $ oex plugins install https://github.com/someuser/someplugin

  Install a plugin from a github slug.

    $ oex plugins install someuser/someplugin
```

_See code: [@oclif/plugin-plugins](https://github.com/oclif/plugin-plugins/blob/v5.0.7/src/commands/plugins/install.ts)_

## `oex plugins link PATH`

Links a plugin into the CLI for development.

```
USAGE
  $ oex plugins link PATH [-h] [--install] [-v]

ARGUMENTS
  PATH  [default: .] path to plugin

FLAGS
  -h, --help          Show CLI help.
  -v, --verbose
      --[no-]install  Install dependencies after linking the plugin.

DESCRIPTION
  Links a plugin into the CLI for development.
  Installation of a linked plugin will override a user-installed or core plugin.

  e.g. If you have a user-installed or core plugin that has a 'hello' command, installing a linked plugin with a 'hello'
  command will override the user-installed or core plugin implementation. This is useful for development work.


EXAMPLES
  $ oex plugins link myplugin
```

_See code: [@oclif/plugin-plugins](https://github.com/oclif/plugin-plugins/blob/v5.0.7/src/commands/plugins/link.ts)_

## `oex plugins remove [PLUGIN]`

Removes a plugin from the CLI.

```
USAGE
  $ oex plugins remove [PLUGIN...] [-h] [-v]

ARGUMENTS
  PLUGIN...  plugin to uninstall

FLAGS
  -h, --help     Show CLI help.
  -v, --verbose

DESCRIPTION
  Removes a plugin from the CLI.

ALIASES
  $ oex plugins unlink
  $ oex plugins remove

EXAMPLES
  $ oex plugins remove myplugin
```

## `oex plugins reset`

Remove all user-installed and linked plugins.

```
USAGE
  $ oex plugins reset [--hard] [--reinstall]

FLAGS
  --hard       Delete node_modules and package manager related files in addition to uninstalling plugins.
  --reinstall  Reinstall all plugins after uninstalling.
```

_See code: [@oclif/plugin-plugins](https://github.com/oclif/plugin-plugins/blob/v5.0.7/src/commands/plugins/reset.ts)_

## `oex plugins uninstall [PLUGIN]`

Removes a plugin from the CLI.

```
USAGE
  $ oex plugins uninstall [PLUGIN...] [-h] [-v]

ARGUMENTS
  PLUGIN...  plugin to uninstall

FLAGS
  -h, --help     Show CLI help.
  -v, --verbose

DESCRIPTION
  Removes a plugin from the CLI.

ALIASES
  $ oex plugins unlink
  $ oex plugins remove

EXAMPLES
  $ oex plugins uninstall myplugin
```

_See code: [@oclif/plugin-plugins](https://github.com/oclif/plugin-plugins/blob/v5.0.7/src/commands/plugins/uninstall.ts)_

## `oex plugins unlink [PLUGIN]`

Removes a plugin from the CLI.

```
USAGE
  $ oex plugins unlink [PLUGIN...] [-h] [-v]

ARGUMENTS
  PLUGIN...  plugin to uninstall

FLAGS
  -h, --help     Show CLI help.
  -v, --verbose

DESCRIPTION
  Removes a plugin from the CLI.

ALIASES
  $ oex plugins unlink
  $ oex plugins remove

EXAMPLES
  $ oex plugins unlink myplugin
```

## `oex plugins update`

Update installed plugins.

```
USAGE
  $ oex plugins update [-h] [-v]

FLAGS
  -h, --help     Show CLI help.
  -v, --verbose

DESCRIPTION
  Update installed plugins.
```

_See code: [@oclif/plugin-plugins](https://github.com/oclif/plugin-plugins/blob/v5.0.7/src/commands/plugins/update.ts)_
<!-- commandsstop -->
