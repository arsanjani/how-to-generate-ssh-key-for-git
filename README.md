# SSH key for Git
There are two ways of connecting to Git repositories. 
1. HTTPS: It needs to set appropriate username and password. 
2. SSH: It doesn't need username and password and works with SSH public key. Because of that it is much easier and convenient way to work with git. It gives you more freedom of dealing with your repositories.

# How to generate SSH key for Git
First, you should check to make sure you don’t already have a key. By default, a user’s SSH keys are stored in that user’s `~/.ssh` directory. You can easily check to see if you have a key already by going to that directory and listing the contents:

```bash
$ cd ~/.ssh
$ ls
authorized_keys2  id_dsa       known_hosts
config            id_dsa.pub
```

If you don’t have these files (or you don’t even have a `.ssh` directory), you can create them by running a program called ssh-keygen, which is provided with the SSH package on Linux/macOS systems and comes with Git for Windows:
```bash
$ ssh-keygen -o
```
First it confirms where you want to save the key (`.ssh/id_rsa`), and then it asks twice for a passphrase, which you can leave empty if you don’t want to type a password when you use the key. However, if you do use a password, make sure to add the -o option; it saves the private key in a format that is more resistant to brute-force password cracking than is the default format. You can also use the ssh-agent tool to prevent having to enter the password each time.
```bash
$ cat ~/.ssh/id_rsa.pub
```
It gives you a SSH key starting with `ssh-rsa`. Go to your Git account -> Settings -> SSH and GPG keys -> New SSH key -> Paste your entire key and set a title -> Add SSH key.
