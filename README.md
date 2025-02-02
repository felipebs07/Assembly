INSTALL ASSEMBLY - VERSION WINDOWSX64

Download:

    MinGW-w64 -> from https://www.mingw-w64.org/
    NASM -> https://www.nasm.us/

Create in variables windows system 2 PATH, example:

    MinGW-w64 -> C:\Program Files\mingw64\bin
    NASM -> C:\Users\<USER>\AppData\Local\bin\NASM

Verify installation:

    gcc --version
    nasm --version

Compiler File:

    1.  nasm -f win64 [NAME_FILE_ASM].asm -o [NAME_FILE_OBJ].obj
    2.  gcc [NAME_FILE_OBJ].obj -o [NAME_FILE_EXE].exe
    3.  .\[NAME_FILE_EXE].exe    