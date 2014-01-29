junk
=========




If your work environment sits behind a proxy/firewall, there are a couple step you will likely need to follow to clone:
(these steps assume a linux environment)

1. ensure your github ssh keys are uptodate.
    1. your current keys are stored here: https://github.com/settings/ssh
    2. generate an ssh key if you don't alreay have one: ssh-keygen2 -t rsa -o id_rsa_2048_a
    3. add a new key by pasting to "Add SSH Key" under "Key" the result of this cmd: ssh-keygen2 -H ~/.ssh2/id_rsa_2048_a.pub -o /dev/stdout

2. if you're behind a firewall, you'll need something like this in your ~/.ssh2/ssh2_config file:

```
    github.com:
        ProxyCommand  socat - socks4a:proxy-socks.fm.intel.com:%h:%p
```

3) test that your basic setup is ok:

    ssh git@github.com
    -> Hi mmccoo! You've successfully authenticated, but GitHub does not provide shell access.

4) clone

    git clone ssh://git@github.com/mmccoo/junk.git

