# Linux File & Directory Management
1. Renaming and moving a file
`mv file1.txt newname.txt.`

Rename the file from file1.txt to newname.txt.

2. Move a file to a directory
`mv newname.txt testdir/.`

Moves a newname.txt to testdir/ directory

3. Rename a directory
`mv testdir_copy new_testdir.`

Renames the directory testdir_copy to new_testdir

4. Move and Rename in One Command
`mv testdir/newname.txt ./original_file1.txt.`

Moves newname.txt out of testdir.

Renames it to original_file1.txt.

`./` means the current directory.

# REMOVING FILES AND DIRECTORIES
1. Removing a single file
`rm original_file1.txt.`

Deletes the file permanently.

TIP: Verify using ls to confirm if original_file1 has been removed

2. Removing interactively
`rm -i file2.txt.`

(-i) allows you to be prompted with y (yes) or n (no)for your confirmation before deleting.

3. Remove empty directory
`rmdir new_testdir.`

NOTE: Deletes a directory only if it is empty.
 
4. Remove the directory and its contents.
`rm -r testdir.`
`-r` recursive
Deletes the directory and everything inside it

5. Force removal
`rm -rf /.`

to be used with extreme caution, as it can delete files permanently, even if they are write-protected files.

# To demonstrate forceful deletion
`mkdir temp_dir.`

`touch temp_dir/temp_file.txt.`

`ls -R temp_dir.`

Note: The capital R used here is referred to as recursive listing

to forcefully remove the directory `rm -rf temp_dir.`

