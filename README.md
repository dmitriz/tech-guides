# tech-guides
Technical Guides for basic setups

# Code management

## SSH keys

To avoid using passwords that are generally insecure, you can instead use [SSH](https://en.wikipedia.org/wiki/Secure_Shell) based [Public Key authentication](https://www.ssh.com/ssh/public-key-authentication) for easy password-less code transfer between your computer and remote repositories on Github/Gitlab/Bitbucket.

To set up, you need two simple steps:
1. Generate `ssh` key on your computer.
2. Add your `ssh` key to Github/Gitlab/Bitbucket.

### Step 1: Generate ssh key

1. Open Terminal (On macOS click Applications/Utilities/Terminal).
2. (Optional) Check your current `ssh` key if present: `ls -l ~/.ssh/id_rsa.pub`. If not present or too old, generate new key. Otherwise skip step 3 below.
3. (Skip this step if you want to keep your old `ssh` key): enter `ssh-keygen` in your Terminal:
```sh
$ ssh-keygen 
Generating public/private rsa key pair.
Enter file in which to save the key (/Users/dmitrizaitsev/.ssh/id_rsa):
```
Just hit return, choose `y` to overwrite and return twice to set no passphrase (or set one if you prefer):
```sh
Overwrite (y/n)? y
Enter passphrase (empty for no passphrase): 
Enter same passphrase again: 
Your identification has been saved in test.
Your public key has been saved in test.pub.
The key fingerprint is:
...
```

If the command `ssh-keygen` is not found, you need to install it, e.g. the `openssh` package with [MacPorts](https://ports.macports.org/port/openssh/summary) (my preference).


### Add your ssh key to your Github/Gitlab/Bitbucket account
0. Copy your `ssh` key to clipboard (in terminal): `cat ~/.ssh/id_rsa.pub | pbcopy`

#### Github
1. Go to your `SSH and GPG keys` settings: https://github.com/settings/keys.
2. Click on green button `New SSH key` at the top on the right.
3. Type any title for your reference and paste your key (Cmd-V) into the Key window.
4. Click the green button `Add SSH Key` and done!

### More detailed instructions
- [Github](https://help.github.com/en/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)

