---
layout: post
title: Visual Studio Code Remote Development Quick Guide
---

## Step 1, install VS Code Insider version
For now, this is still an experimental feature and rumor says it will be available in June in official release. You can follow this [Link](https://code.visualstudio.com/insiders/) to download the insider version.

![an image alt text](https://github.com/vscode-icons/vscode-icons/blob/master/images/logo.png "an image title") 


## Step 2, ssh passwordless login (authentication with key)
You can use different methods to generate a pair of ssh keys and save them in 

> C:\users\yourusername\\.ssh

as id_dsa and id_dsa.pub. Then find a way to insert the content of id_dsa.pub into authorized_keys file on the remote server which can be found at

> /home/yourname/.ssh/authorized_keys


## Step 3, configure the ssh session in VS Code
You can either press F1 then select "Remote-SSH: connect to Host" then configure or you can just edit C:\users\yourusername\\.ssh\config file with the following content

```bash
Host a_name_for_host
    HostName hostname
    User login_name
```

Note that you can configure multiple hosts inside this file.
 
## Step 4, Connect to Host
 Press F1 in VS Code and connect to Remote Host and it will automatically install VS Code server. Then you can open the folder on the host start editing code!
 
 Note that only bash is supported. 
 
    

Reference:

[VS Code Remote Development](https://code.visualstudio.com/docs/remote/ssh)



----
****
