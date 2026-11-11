# block_privmsg for irssi

`block_privmsg.pl` blocks private messages in irssi before anything else sees them, irssiproxy included. Messages to channels pass as usual.

## Features

- Drops private messages at the raw server level, so proxied clients never get them either.
- Lets chosen people through by nick, or by a full `nick!user@host` mask with `*` and `?`.
- Skips whole networks, such as BitlBee.

## Installation

1. Put the script in your irssi scripts directory:

   ```bash
   mkdir -p ~/.irssi/scripts/autorun
   wget -O ~/.irssi/scripts/block_privmsg.pl https://raw.githubusercontent.com/rollecode/irssi-block-privmsg/main/block_privmsg.pl
   ln -s ../block_privmsg.pl ~/.irssi/scripts/autorun/block_privmsg.pl
   ```

2. Load it:

   ```irssi
   /script load block_privmsg
   ```

## Settings

Let people through, by nick or by full mask. A mask is safer, since anyone can take a nick:

```irssi
/set block_privmsg_whitelist friend helperbot!~helper@*.example.org
```

Networks where nothing is blocked, by their irssi tag:

```irssi
/set block_privmsg_exempt_servers BitlBee
```

## Author

- **Rolle Laukkarinen**
- **Contact**: [rolle@dude.fi](mailto:rolle@dude.fi)

## License

Public domain.
