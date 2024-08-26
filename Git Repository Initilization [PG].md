# INITIALIZE SSH FOR GIT - CONNECT TO REPOSITORY

# Step 1 — Installing Git

Go ahead and open https://git-scm.com/. Download the application.


# Step 2 — Configuring Git

Before we move forward, adapt the following commands with your name and email.
```
git config --global user.name "First name Last name"
git config --global user.email “you@example.com”
```

# Step 3 — Generating an SSH key

### | On Windows |

Check the directory listing to see if you already have a public SSH key. By default, the filenames of supported public keys for GitHub are one of the following. `id_rsa.pub` - `id_ecdsa.pub` - `id_ed25519.pub`

**TiP**: If you receive an error that ~/.ssh doesn't exist, you do not have an existing SSH key pair in the default location. You can create a new SSH key pair.

Run the command:
```
type ~\.ssh\id_rsa.pub
```
To copy the SSH public key on Windows:
```
type ~\.ssh\id_rsa.pub | clip
```


## Setup SSH key for GitLab

Run:
```
ssh-keygen
```
First, you will be asked about the location where the keys should be stored. By default, your user folder will contain a folder called .ssh. Leave it as it is and hit the Enter key.

![enter image description here](https://miro.medium.com/v2/resize:fit:720/format:webp/1*TV6O372OLqtal3fxjqH3Jw.png)

Next, you will be asked to set a password to protect your private key.
While it is a good practice to set a password, it is very hard in Windows to store that password in a way that you don’t have to type it every time you run a command in Git. For that reason, leave it empty for now and simply hit Enter two times.


![enter image description here](https://miro.medium.com/v2/resize:fit:720/format:webp/1*MJbrGMyQ21ZRWMeirL7JJA.png)

Congrats! Your public/private key pair has been generated.

![enter image description here](https://miro.medium.com/v2/resize:fit:720/format:webp/1*Y25YT4UFfTftgwMItYmfLA.png)

**Let’s recap what you now have:**

![enter image description here](https://miro.medium.com/v2/resize:fit:720/format:webp/1*0_PVysIfm_oPIoYlysFcBg.png)


- `id_rsa` — this is your **PRIVATE** key. DO NOT SHARE this with anyone else. This is your secret.
- `id_rsa.pub` — this is your **PUBLIC** key. This contains no secrets. You can share it with others.


# Step 4 — Adding your SSH key to GitLab

With your favorite text editor, open your public key. I will use the terminal and the `cat` command to view the contents of the file.

![enter image description here](https://miro.medium.com/v2/resize:fit:720/format:webp/1*48SAz7lZ7eHVi5UEZCpcqQ.png)

If you are not using Git bash, you may want to use type and pipe it to clip, like:

```
type id_rsa.pub | clip
```

Copy the entire contents of the file.
In GitLab, go to your profile > Preferences >  SSH Keys.

Paste your **Public Key** in the big text box you see on the screen and finally click Add key. Optionally, you may also give your key a name so that you can easily identify it later.

![enter image description here](https://miro.medium.com/v2/resize:fit:720/format:webp/1*LEaZsv_7gTW1IQHdocXgZA.png)


# Step 5 — Cloning a GitLab repository

Log in to your GitLab account and go to the repository you want to clone.

![enter image description here](https://miro.medium.com/v2/resize:fit:720/format:webp/1*vi2YDtYbATdoEnla2x10rg.png)

Click on the Clone button and the address under Clone with SSH.

Run the command:
```
git clone (PASTE HERE YOUR ADDRESS)
```

![enter image description here](https://miro.medium.com/v2/resize:fit:720/format:webp/1*RbTv0K__g1X9PvWMRZ9_eQ.png)
