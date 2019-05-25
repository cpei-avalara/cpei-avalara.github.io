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

launch.json file 

```json
{
    // Use IntelliSense to learn about possible attributes.
    // Hover to view descriptions of existing attributes.
    // For more information, visit: https://go.microsoft.com/fwlink/?linkid=830387
    "version": "0.2.0",
    "configurations": [
        {
            "name": "g++ build and debug active file",
            "type": "cppdbg",
            "request": "launch",
            "program": "${fileDirname}/${fileBasenameNoExtension}",
            "args": [],
            "stopAtEntry": false,
            "cwd": "${workspaceFolder}",
            "environment": [],
            "externalConsole": false,
            "MIMode": "gdb",
            "setupCommands": [
                {
                    "description": "Enable pretty-printing for gdb",
                    "text": "-enable-pretty-printing",
                    "ignoreFailures": true
                }
            ],
            "preLaunchTask": "g++ build active file",
            "miDebuggerPath": "/usr/bin/gdb"
        }
    ]
}
```

Note that there is a `preLaunchTask`, that is a reference to the task defined by `tasks.json` file. 

```json
{
    "tasks": [
        {
            "type": "shell",
            "label": "g++ build active file",
            "command": "/usr/bin/g++",
            "args": [
                "-g",
                "${file}",
                "-std=c++11",
                "-o",
                "${fileDirname}/${fileBasenameNoExtension}"
            ],
            "options": {
                "cwd": "/usr/bin"
            }
        }
    ],
    "version": "2.0.0"
}
```
 
## Step 4, Happy debugging
Note that you need to make sure the current file opened by VS is the file you want to debug because the macros are defined in a way related to the current opened file.






----
****
