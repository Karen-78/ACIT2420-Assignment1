bckup.config file should be placed in ~/.config/bckup directory.
bckup script should be placed in ~/bin directory. 

Note: Must provide the full path to the file or directory you wish to backup onto Spaces. 

Options: 
    -c is "copy" - Copies the specified file to Spaces.
    -s is "sync" - Detects difference between local folder and destination folder on Spaces and any changes in destination folder will be replaced. New files will be deleted and deleted files will be uploaded. rclone will prompt the user before deleting or copying. 
    -l is "list" - Lists the files that are backed up on Spaces. 

Explanation of bckup.config file: 
    config_spaces_name is the name of your remote configured during rclone config 
    spaces_backup_path is the path you want to backup to on Spaces. It should start with the name of your Spaces Object Storage. 


Examples how to use the script from your home directory: 

To copy a file to Spaces: 
``` 
./bin/bckup/bckup -c backup-example
```

To sync a folder to Spaces: 
```
./bin/bckup/bckup -s ~/dir-to-backup
```
Note: using sync will result in rclone prompting if you want to make, copy, or delete files and directories. 

To see backed up files on Spaces: 
``` 
./bin/bckup/bckup -l
```

To restore files from remote to local system: 
```
./bin/bckup/bckup -r
```