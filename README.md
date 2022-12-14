# `clif`

### A lightweight and effective Command-Line Interface Framework.

## Overview

Arguments are learned as-they-go: the cli parsing framework learns each argument upon checking it. For this reason, in order to maximize effectiveness of the parsing __it is recommended to parse arguments in the following order__:
1. flags
2. options
3. positionals
4. subcommands

> __Note:__ For a type to be accepted by the command-line it must implement the `std::str::FromStr` trait.

## Features

- long options (flags/options)): `--verbose`

- short options (switches): `-v`

- positional value placement: `--output a.out`, `-o a.out`

- attached value placement: `--output=a.out`, `-o=a.out`

- combine switches: `-rf`

- capture variable flag calls: `--inc --inc --inc...`

- capture variable option calls: `--op 10 --op 20 --op 30`

- capture variable positional calls: `10 20 30`

- capture variable limited user-defined caps for flag and option calls: `--verbose --verbose --verbose` (ex: up to 3)

- combine switches and give value to final switch: `-rfo=a.out`

- ability to prioritize help over any other error

- ability to enable/disable a help flag with custom long/short flag names

- subcommand support: `calc add 10 20`, `calc mult 10 20`

- arguments can be reused in both structs for overall command and nested subcommand

- zero dependencies (use the `color` feature for coloring)

- uses dynamic programming sequence alignment algorithm to detect misspelled arguments (with configurable `threshold` for string comparison)

- ability to set user-defined help text before parsing

- ability to verify there are no unused arguments passed in the cli

- verifies all argument type conversions are accepted during parsing

- preserves unprocessed arguments found after an empty flag `--` symbol

## Examples

See the [examples/](./examples/) folder for practical implementations.