# Streamlining SSH configuration

## Show your .ssh/config file, and how you edited it (with VScode, another program, etc)

![](ssh_config_screenshot.PNG)

I edited it in the default wsl vim installation.

## Show the ssh command logging you into your account using just the alias you chose.

![](ssh_ieng6.png)

## Show an scp command copying a file to your account using just the alias you chose.

![](scp_r_demonstration.png)

This is the `scp -r` demonstration. It shows a working usage of `scp`, however, so I chose to use it here.

# Setup Github Access from ieng6

## Show where the public key you made is stored on Github and in your user account (screenshot).

![](ssh_config_screenshot.PNG)

## Show where the private key you made is stored on your user account (but not its contents) as a screenshot.

![](ssh_private_key_storage.PNG)

## Show running git commands to commit and push a change to Github while logged into your ieng6 account.

![](ssh_git_push.PNG)

This took me so long to troubleshoot! I did the following things to get it to work (this is for myself):

1. `eval $(ssh-agent)` to enable the next command
2. `ssh-add ~/.ssh/id_rsa_git` to add the key
4. `ssh -T git@github.com` to verify the key
3. `git remote set-url origin git@github.com:<Username>/<Project>.git` to make sure it leads to the right place

30 minutes of work!

## Show a link for the resulting commit.

[Link for the resulting commit](https://github.com/YoavGutmanUCSD/markdown-parser-2/commit/a0fbdca24ddb21c5cb9559a7150e24fe840d2efc)


# Copy whole directories using `scp -r`

## Show copying your whole markdown-parse directory to your ieng6 account.

![](scp_r_run_mdparse.PNG)

## Show logging into your ieng6 account after doing this and compiling and running the tests for your repository.

![](run_tests_ieng6.PNG)

## Show (like in the last step of the first lab) combining scp, ;, and ssh to copy the whole directory and run the tests in one line.

![](scp_r_demonstration.png)

This is the `scp -r` demonstration from the lab. I have used this before but it applies here perfectly.