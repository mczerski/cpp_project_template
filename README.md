# cpp_project_template
Simple C++ project template using cmake and vim as ide

to use vim as ide set a bash alias in your ~/.bashrc like this:
```
alias ccvim='vim -u .vim/cc.vimrc'
```
and then run ccvim from the project root directory.

Template assumes this project structure:
```
root/
   \
    src/ <- here gose main code
    test/ <- here goes test code
    main.cpp
```
