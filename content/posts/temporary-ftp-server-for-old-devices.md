+++
date = '2026-05-18T21:44:55+02:00'
draft = true
title = 'Temporary Ftp Server for Old Devices'
+++

If you're dealing with old hardware, it's not uncommon to either have no USB port at all,
or just a USB 1.x, which is painfully slow.

To overcome the speed limitation, two options are available.

## Option 1: PCMCIA USB 2.0

One workaround is to use a PCMCIA USB 2.0 card, which dramatically improves transfer
speeds from USB 1.x levels. 12 Mbps (~1.5 MB/s) vs 480 Mbps (~60.0 MB/s).

That said, finding proper drivers for legacy operating systems like Windows 95 or 98 can be a challenge on its own.

## Option 2: FTP over Ethernet

If the PCMCIA route isn't an option, the most compatible alternative is to spin up a
temporary FTP server and transfer files over Ethernet. It gives you at minimum 100 Mbps (~12.5 MB/s) for most the NICs produced in late 90s and beyond which is already way faster than USB 1.x still.

The other big advantage: you can find an FTP client for virtually any platform.

### FTP clients

For **Windows 98SE**, I use FileZilla 2.2.22, or better 2.2.18, which reportedly
supports even Windows 95C. You can grab it from the
[Old Version](https://www.oldversion.com.de/software/filezilla/) website.

For any **Unix-based OS** (Linux or Mac) you can just use the built-in
[`ftp`](https://linux.die.net/man/1/ftp) command. I've tested this on
[SUSE 9.2](https://en.opensuse.org/Archive:SUSE_Linux_9.2) and newer Linux distros,
as well as on [Mac OS X Panther (10.3)](https://en.wikipedia.org/wiki/Mac_OS_X_Panther)
and later. Everything worked exactly as expected.

## Setting up the Server

The easiest way to get a server running is with the Python library
[pyftpdlib](https://github.com/giampaolo/pyftpdlib). A few commands and you're up without
any complicated authentication.

```bash
$ python3 -m venv env
$ source env/bin/activate
$ pip3 install --user pyftpdlib
$ python3 -m pyftpdlib --directory=[DIRECTORY] --port=2121 --write
```

Your FTP server will be up and running on port 2121 with no authentication required.

## Connecting to the Server

**From the command line:**

```bash
$ ftp [ip] 2121
```

When prompted for a username, type `anonymous` and just press Enter for the password.

**From FileZilla:** enter the server's IP address and port 2121, and leave the username
and password fields blank.

When you're done, hit `Ctrl + C` on the server side to shut it down.

## ⚠️ Security Warning

**Do not** use this setup to expose an FTP server publicly. This approach is intentionally
insecure and should only be used on a local network, for a short period of time. Its
strengths are broad compatibility with retro operating systems and ease of setup. Not security.
