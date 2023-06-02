# Using the `find` command

The purpose of this command allows the user the pinpoint the location data within the directory given a set of inputs.

## Using the `-name` command-line option

[The source that I used for this option.](https://adamtheautomator.com/bash-find/#Finding_Files_by_File_or_Directory_Name)

```
[cs15lsp23rk@ieng6-203]:stringsearch-data:403$ find technical -name "chapter-1.txt"
technical/911report/chapter-1.txt
```

When wanting to look for specific file names within a directory, the `-name` option allows you input any file name you wish. When running this command, it will take the argument, determine which files meet the criteria, and return them to the user.

```
[cs15lsp23rk@ieng6-203]:stringsearch-data:404$ find technical -name "chapter*"
technical/911report/chapter-1.txt   
technical/911report/chapter-10.txt  
technical/911report/chapter-11.txt  
technical/911report/chapter-12.txt  
technical/911report/chapter-13.1.txt
technical/911report/chapter-13.2.txt
technical/911report/chapter-13.3.txt
technical/911report/chapter-13.4.txt
technical/911report/chapter-13.5.txt
technical/911report/chapter-2.txt   
technical/911report/chapter-3.txt   
technical/911report/chapter-5.txt   
technical/911report/chapter-6.txt   
technical/911report/chapter-7.txt   
technical/911report/chapter-8.txt   
technical/911report/chapter-9.txt   
```

Additionally, you can utilize `[file name]*` as the argument if you wish to find files that start with the text found before the asterisk. This can allow access to multiple file paths that follow the criteria you wish for.

## Using the `-iname` command-line option

[The source that I used for this option.](https://www.computerhope.com/unix/ufind.htm)

```
[cs15lsp23rk@ieng6-203]:stringsearch-data:455$ find technical -iname A_Helping_Hand.txt
technical/government/Media/A_helping_hand.txt
```

This option works similarly to `-name` however, it is case insensitive meaning it ignores capitalization matching and checks if only the text itself matches the argument. This is useful if you are unsure of how capitalization is held on the file that you are looking for.

```
[cs15lsp23rk@ieng6-203]:stringsearch-data:456$ find technical -iname survey*           
technical/government/Media/Survey.txt
```

Also just like `-name`, you can utilize `[file name]*` as the argument if you wish to find files that start with the text found before the asterisk. If you know any key words that your file must start with, this will be a sure fire way to find it.

## Using the `-type` command-line option

[The source that I used for this option.](https://www.redhat.com/sysadmin/linux-find-command)

```
[cs15lsp23rk@ieng6-203]:stringsearch-data:405$ find technical -type d         
technical
technical/911report
technical/biomed
technical/government
technical/government/About_LSC
technical/government/Alcohol_Problems  
technical/government/Env_Prot_Agen     
technical/government/Gen_Account_Office
technical/government/Media
technical/government/Post_Rate_Comm    
technical/plos
```

When wanting to look for a specific file type within a directory, the `-type` option allows you to specify types such as files `f` and directories `d`. Here this command finds all of the directories that are within the file that we started in.

```
[cs15lsp23rk@ieng6-203]:stringsearch-data:406$ find technical/government/Alcohol_Problems/ -type f
technical/government/Alcohol_Problems/DraftRecom-PDF.txt
technical/government/Alcohol_Problems/Session2-PDF.txt
technical/government/Alcohol_Problems/Session3-PDF.txt
technical/government/Alcohol_Problems/Session4-PDF.txt
```

When using `-type f`, you can find all of the files that reside in a specific directory of your choosing as well. This can allow you to sift through many different lines of paths if there are many directories or other types you do not want to see on the output.

## Using the `-path` command-line option

[The source that I used for this option.](https://www.computerhope.com/unix/ufind.htm)

```
[cs15lsp23rk@ieng6-203]:stringsearch-data:420$ find technical -path 'technical/government/Media/The*'
technical/government/Media/The_Bend_Bulletin.txt
technical/government/Media/The_Columbian.txt
technical/government/Media/The_State_of_Pro_Bono.txt
```

Using this option allows for the user to look for files that follow a specific file path. This can be useful if there is a file you know the path of but not the actual name of the file itself.

```
[cs15lsp23rk@ieng6-203]:stringsearch-data:428$ find technical -path 'technical/government/*/Progress_report.txt'
technical/government/About_LSC/Progress_report.txt
```

You can also use wildcards like the asterisk here to fill in for the path name if you wish to look through multiple directories under the same path pattern to find the file you are looking for.
