# Setup Github SSH for windows 11

Setting up **SSH** for Windows 11 is very similar to Windows 10 (Sometimes it gets complicated). But let's get a simplt method to do it.

## Prerequisites

1. Download and Install [*Git Bash*](https://git-scm.com/downloads).
2. Git Bash can also be setup from *PowerShell*. Just run the following command into PowerShell:

```
choco install git -Y

```

3. Once you done installing the Git Bash, open the Git Bash and Setup *Global username* and *Global email*

```
git config --global user.name "your-github-username"
git config --global user.email "your-github-email"

```

### Step-1: Generate new SSH key

Open the Git bash and type in:

```
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"

```

* Hit enter when it asks for a file name


### Step-2: Start SSH agent

```
eval $(ssh-agent -s)

```

then

```
ssh-add ~/.ssh/id_rsa

```


### Step-3: Copy the public key

After step 2, We need to copy the ssh key to integrate with GitHub. The easiest way is to use ``clip`` option:

```
clip < ~/.ssh/id_rsa.pub

```

### Step-4: Add ssh key to Github

We have our ``ssh`` key now. The next step is to add this to GitHub. Follow step by step:

1. Open up github go click on your profile picture and go to ``settings``
2. Under the settings, go to ``SSH and GPG Keys``
3. Create a new ``ssh Key``
4. Give it a name
5. On the ``Key`` option just paste the ssh key you just copied.
6. Finally click ``add ssh key``

voilà! You have added the SSH key for Github and your Windows 11. If you want to test the SSH key, Simply clone a repository using ``ssh`` option and push some changes using Git Bash.

