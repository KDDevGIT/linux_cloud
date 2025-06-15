# linux_cloud setup
rm -f ~/.ssh/id_ed25519 ~/.ssh/id_ed25519.pub #Override SSH key

ssh-add -D #Remove Identities

ssh-keygen -t ed25519 -C "kymasterbox@gmail.com" @generate new key
if exists: Overwrite (y/m)? >> y
Enter a passphrase or leave blank (not recommended)
Save in /home/kylinux/.ssh/id_ed25519
Output:
Your identification has been saved in /home/kylinux/.ssh/id_ed25519
Your public key has been saved in /home/kylinux/.ssh/id_ed25519.pub
The key fingerprint is:
SHA256:oKoY/F5YqrLTx2kpQ4F/34AVggkf3XyFwq/9v4n1uI0 kymasterbox@gmail.com
The key's randomart image is:
+--[ED25519 256]--+
|...+ +   o.      |
| .o.o * o        |
| ..  ..=         |
|. .  ....        |
| . ..+ oS        |
|. o.* o .        |
|.+.= = o .  .    |
|+o* B . . .o *   |
|=+.B      ..Eoo  |
+----[SHA256]-----+

cat ~/.ssh/id_ed25519.pub #create and copy private key
Paste PubKey to Github >> settings >> SSH and GPG Keys

eval "$(ssh-agent -s)" #Eval SSH Agent

ssh-add ~/.ssh/id_ed25519 #Add SSH Agent >> Enter passhrase
Output: Identity added: /home/kylinux/.ssh/id_ed25519 (kymasterbox@gmail.com)

ssh -T git@github.com 
Output: Hi KDDevGIT! You've successfully authenticated, but GitHub does not provide shell access

git clone git@github.com:KDdevGIT/linux_cloud.git
Make sure repo exists on GitHub!
Output: Cloning into 'linux_cloud'...
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
Receiving objects: 100% (3/3), done.
cd <repo_name>

git add .
git commit -m "commit"
git push

