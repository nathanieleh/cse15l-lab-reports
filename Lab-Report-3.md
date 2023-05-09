# Using the `find` command

The purpose of this command allows the user the pinpoint the location data within the directory given a set of inputs.

## Using the `-name` command-line option

[The source that I used for this option.](https://adamtheautomator.com/bash-find/#Finding_Files_by_File_or_Directory_Name)

When wanting to look for specific file names within a directory, the `-name` option allows you input any file name you wish. When running this command, it will take the argument, determine which files meet the criteria, and return them to the user.

Additionally, you can utilize `[file name]*` as the argument if you wish to find files that start with the text found before the asterisk.

## Using the `-type` command-line option

[The source that I used for this option.](https://www.redhat.com/sysadmin/linux-find-command)

When wanting to look for a specific file type within a directory, the `-type` option allows you to specify types such as files `f` and directories `d`.

## Using the `-path` command-line option

[The source that I used for this option.](https://www.computerhope.com/unix/ufind.htm)

Using this option allows for the user to look for files that follow a specific file path. This can be useful if there is a file you know the path of but not the actual name of the file itself.

You can also use wildcards like the asterisk here to fill in for the path name if you wish to look through multiple directories under the same path pattern.

## Using the `-regex` command-line option

[The source that I used for this option.](https://www.computerhope.com/unix/ufind.htm)

When wanting to look for specific files / directories, the `-regex` option allows you utilize the [regex](https://regexr.com) pattern system to find the name of a file. When running this command, it will take the argument, determine which files meet the criteria, and return them to the user.
