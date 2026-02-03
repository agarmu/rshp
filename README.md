# rshp

`rshp` stands for **R**emote **Sh**ell **P**printer. Given a `hostname` and a `file`,
`rshp` transforms the file using `ghostscript` to make it more receptinve to printing,
sends it via `sftp` to a host, and then allows you to print the file.

Currently, the printers on the host are supposed to follow the scheme `[BUILDING][NAME][CAP]`,
where `[BUILDING]` is a 4-character building code, `[NAME]` is a generic name, and `[CAP]` is either
`bw` or `co` depending on the printing capabilities of the printer (black & white/color respectively).
This is due to the fact that the printers I use have this schema; I will probably be adding some ability
for users to modify this.

## Usage

```sh
$ rshp [host] [filename]
```
Here `host` is a ssh host (should be configured in `~/.ssh/config`/with ssh key if necessary; you should be able to run `ssh host` and get terminal access), and `[filename]` is the path to a pdf file.

## Installation

Install with rust/cargo.

## Dependencies

Depends on `ssh/sftp` and `ghostscript`.
