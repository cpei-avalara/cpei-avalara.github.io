---
layout: post
title: Visual Studio Code Remote Debug (C++) Quick Guide
---

![an image alt text](https://img.icons8.com/color/96/000000/visual-studio.png "an image title") 


## Step 1, Follow previous ![post](https://cpei-avalara.github.io/VS-Code/) to setup the environment
This also include installing VS Code Insider version. (you have to wait until sometime in June to use the official version which has this remote support).



## Step 2, Connect to the remote linux box
Open VS Code Insider version and connect to the linux box and wait for it sets up everything, which may take a few minutes depending on the connection.
Then make sure you reinstall the plugin named C/C++ which has IntelliSense, debugging, and code browsing support.



## Step 3, Open a remote source code folder
After the files are shown from that folder, you can click on `Debug` from the menu. If this is the first time, it will prompt you that you need to setup the `launch.json` file. You can choose the `g++ build and debug active file` template and start editing.

Insert code here 

```bash
Host a_name_for_host
    HostName hostname
    User login_name
```

Note that there is a `preLaunchTask`, that is a reference to the task defined by `tasks.json` file. Insert the source code for that here

 
## Step 4, Happy debugging
 





----
****
