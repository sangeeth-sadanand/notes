- Linux follows tree structure
- `~` represents home directory of the users.
-  `..` represent parent directory
- `.` represent current directory

### Permission structure
![[linux_file_permission.svg]]

r - read (4)
w - write(2)
x - execute(1)

| command | description                                                                                     |
| ------- | ----------------------------------------------------------------------------------------------- |
| pwd     | prints present corking directory                                                                |
| whoami  | print current username                                                                          |
| clear   | clears terminal screen                                                                          |
| cd      | change directory                                                                                |
| cd -    | change to previous directory                                                                    |
| cd ~    | change to home                                                                                  |
| cd ..   | go one directory up                                                                             |
| ls      | list directory content <br>**blue** color indicates directory<br>**green** indicates executable |
| ls -l   | long list                                                                                       |
| ls -lt  | list content with long list order with latest modified date                                     |
| Is -Itr | list content with long list order with oldest file first                                        |
| Is -IR  | Recursively list all the files in a directory                                                   |
| Is -a   |  list all files including hidden files                                                          |
