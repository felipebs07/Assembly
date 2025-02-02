# ASSEMBLY - VERSION WINDOWSX64

## Download:

    MinGW-w64 -> from https://www.mingw-w64.org/
    NASM -> https://www.nasm.us/

## Create in variables windows system 2 PATH, example:

    MinGW-w64 -> C:\Program Files\mingw64\bin
    NASM -> C:\Users\<USER>\AppData\Local\bin\NASM

## Verify installation:

    gcc --version
    nasm --version

## Compiler File:

    1.  nasm -f win64 [NAME_FILE_ASM].asm -o [NAME_FILE_OBJ].obj
    2.  gcc [NAME_FILE_OBJ].obj -o [NAME_FILE_EXE].exe
    3.  .\[NAME_FILE_EXE].exe    


### Vscode - CONFIGURE
   1. Download 2 extensions: [NASM](https://marketplace.visualstudio.com/items?itemName=doinkythederp.nasm-language-support) AND [X86_64 Assembly](https://marketplace.visualstudio.com/items?itemName=13xforever.language-x86-64-assembly).
    2. Create task.json
```
    {
        "version": "2.0.0",
        "tasks": [
            {
                "label": "NASM Compile",
                "type": "shell",
                "command": "nasm",
                "args": [
                    "-f",
                    "win64",
                    "${file}",
                    "-o",
                    "${fileBasenameNoExtension}.obj"
                ],
                "group": "build"
            },
            {
                "label": "GCC Link",
                "type": "shell",
                "command": "gcc",
                "args": [
                    "${fileBasenameNoExtension}.obj",
                    "-o",
                    "${fileBasenameNoExtension}.exe"
                ],
                "group": "build",
                "dependsOn": ["NASM Compile"]
            },
            {
                "label": "Run",
                "type": "shell",
                "command": "./${fileBasenameNoExtension}.exe",
                "group": "test"
            },
            {
                "label": "Build and Run",
                "type": "shell",
                "dependsOrder": "sequence",
                "dependsOn": [
                    "NASM Compile",
                    "GCC Link",
                    "Run"
                ],
                "group": {
                    "kind": "build",
                    "isDefault": true
                }
            }
        ]
    }
    ```
    3.  now test running command in vscode CTRL + Shift + B
    4.  if using win64, add in vscode settings with : "nasm.outputFormat": "win64"