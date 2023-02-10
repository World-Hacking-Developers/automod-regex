# World Hacking automod regex
## Description
You can copy this regular expressions to configure the automod settings in a Discord server.
Note that Discord uses Rustexp, so there are some features you cannot use, such as `lookaround` in general.

## Usage
Just go to the server settings > automod. There, you can create a custom rule and put the desired expression from this list under the `regex` section of the configuration.

## Expressions
### Avoid scammers
#### Discord links
Mostly for invites, but this will block all Discord and Discord~ish links. Note that static links to images or files under the `cdn.discordapp.com`, `media.discordapp.com` or similar will not be affected by this.
```regex
d[1il][5s]c[o0]rd(\.(gg|com))
```

#### Phone numbers
As there are lots of scammers that try to get you into a Whatsapp link or something similar, I decided to just avoid any phone-like strings in the chat.
```regex
\+[\d ()-]{9,}
```

#### Crypto or investment spam
These block the *"earn up to $10k monthly"*, *"my clients are making 15k per week"*, *"get up to $8k profit"* types of messages. Probably more useful for non-English-speaking servers. But you can tune the expressions for English-speaking servers as well.
```regex
(earn|mak).*?[\d.,]+?k
[\d.,]+?k.*?profit
```

### Avoid general spam or dangerous links
Not being able to know where the links take you is dangerous. If the link is benign, but it's filled with ads, that's uncomfortable for the users.
I have put the most normal url shorteners here. But as I didn't want to configure each separately, I just combined them into a single expression. Feel free to modify the regex to your liking.
```regex
https?://(bit|adf|ow|goo|tinyurl|tiny|cutt|destyy|short|zz|shrt)\.(ly|gl|cc|do|to|gd|st|com)
```

## Contribution
If you find that these expressions can be further improved or I have missed something, feel free to make a pull request!

## Join us
Don't forget to [join us on Discord](http://discord.gg/tJa66GNhej).
