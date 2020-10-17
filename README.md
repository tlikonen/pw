PW - A Password Manager
=======================

Pw is a command-line password manager program for GNU/Linux systems. Pw
is designed to be quick and simple to use and it is similar to [pass][]
but with different command-line interface. Each password is stored as
separate encrypted file under user's home directory.

[pass]: https://www.passwordstore.org/


## Requirements and Installation

Install the required programs (see below) and copy the `pw` executable
program somewhere in your system's `$PATH`, for example in
`/usr/local/bin` or `~/bin`.

  * A GNU/Linux system with [Bash][] shell and GNU [Coreutils][]. Normal
    GNU/Linux distributions install these by default.
  * [GnuPG][] (gpg): Should be installed by default on GNU/Linux
    systems.
  * [xsel][]: You probably need to use your package manager to install
    this.

[Bash]:      https://www.gnu.org/software/bash/
[Coreutils]: https://www.gnu.org/software/coreutils/coreutils.html
[GnuPG]:     https://gnupg.org/
[xsel]:      http://www.vergenet.net/~conrad/software/xsel/


## Usage

    Usage: pw [options] [--] [arguments]
           pw PATTERN

      The default operation lists all password names that match the PATTERN
      that is given as argument. User is asked to choose one password and
      the first line of the chosen password is then copied to the clipboard
      (see also "-s"). The clipboard is cleared after 15 seconds. Shell
      wildcards *, ? and [] are supported in PATTERN.

    Command options

      -l [PATTERN]
            List all password names that match PATTERN (or all passwords if
            PATTERN is not given).

      -a NAME
            Add new password NAME and edit it with the default text editor
            ($EDITOR).

      -e PATTERN
            Edit an existing password with the default text editor
            ($EDITOR). First list all password names that match PATTERN.
            Then ask user to choose one password to be edited.

      -g NAME [LENGTH]
            Generate and store a random password named NAME. The optional
            LENGTH argument sets the password length (default 16). The
            password is also copied to the clipboard for 15 seconds (see
            also "-s").

      -d NAME
            Delete password NAME.

      -r OLD NEW
            Rename password from OLD name to NEW name.

      -i KEY
            Initialize the password storage to be used with KEY. The KEY
            argument can be any valid reference to a gpg key in the default
            public keyring. You can use this option again later to change
            the KEY and reencrypt all password files for the new key.

      -h    Print this help text.

    Other options

      -s    Show password. Instead of copying password to the clipboard
            print it to the stardard output.

      -f    Force overwrite existing password. Don't ask for confirmation.

    Storage directory:  ~/.config/pw
    Configuration file: ~/.config/pw/config
    Key id file:        ~/.config/pw/key

## The Source Code Repository

GitHub repository: <https://github.com/tlikonen/pw>


## Copyright and License

Copyright (C) 2016-2020 Teemu Likonen <<tlikonen@iki.fi>>

OpenPGP key: [4E10 55DC 84E9 DFF6 13D7 8557 719D 69D3 2453 9450][PGP]

This program is free software: you can redistribute it and/or modify it
under the terms of the GNU General Public License as published by the
Free Software Foundation, either version 3 of the License, or (at your
option) any later version.

This program is distributed in the hope that it will be useful, but
WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General
Public License for more details.

The license text: <http://www.gnu.org/licenses/gpl-3.0.html>

[PGP]: http://www.iki.fi/tlikonen/pgp-key.asc
