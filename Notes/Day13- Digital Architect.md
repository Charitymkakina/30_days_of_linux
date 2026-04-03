# Challenge 2
Your mission is to architect a clean, logical, and efficient file structure that will support the growing development team.

By creating proper directories, organizing files, securing backups, and cleaning up old data, you'll establish the foundation

that Project Phoenix needs to succeed.

# Tasks
1. Navigate into the` ~/project/phoenix_project directory.`
2. Create three new subdirectories: src for source code, config for configuration files, and docs for documentation.

# Requirements
1. All new directories must be created inside the`~/project/phoenix_project directory.`
2. The directory names must be exactly src, config, and docs.
3. You should use a single command to create all three directories simultaneously.

# Solution:
`pwd`- To check the current directory

Changing the directory: `cd ~/project/phoenix_project directory.`

`mkdir src config docs`

Verify: `ls -f.`

# Tasks
1. Move the `main_app.py` file into the `src directory.`

2. Move the `config.json` file into the `config directory.`

3. Move the `README.md` file into the `docs directory.`
   
# Requirements
Ensure you are in the `~/project/phoenix_project` directory before performing the move operations.

Use the `mv` command to relocate each file.

# Solution
`cd ~/project/phoenix_project directory`

`mv main_app.py src/`

`mv config.json config/`

`mv README.md docs/`

# Tasks
1. Create a backup copy of the config.json file.
   
# Requirements
1. The backup file must be created within the `~/project/phoenix_project/config/ directory.`
   
2. The backup file must be named exactly `config.json.bak.`

# Solution:
`cp config/config.json config/config.json.bak`

`cd ~/project/phoenix_project directory/config`

`ls` 

output: `config.json config.json.bak`

# Tasks

1. Move the entire shared_docs directory and all of its contents into the `~/project/phoenix_project/docs/ directory.`
   
# Requirements
1. The source directory is `~/project/shared_docs.`
   
2. The destination path is `~/project/phoenix_project/docs/.`
   
3. The entire directory, not just its contents, must be moved.

# Solution
`mv ~/project/shared_docs ~/project/phoenix_project/docs.`

`cd ~/project/phoenix_project/docs.`

`ls.`

Output: `README.md shared_docs.`

# Tasks
1. Navigate to the ~/project/logs directory.

2. Create a compressed tar archive named old_logs.tar.gz that contains all log files from the year 2023.
   
3. After the archive is successfully created, delete the original 2023 log files that you just archived.
   
# Requirements
1. The final archive must be named exactly old_logs.tar.gz.
2. The archive must be located in the ~/project/logs directory.
3. Only log files with 2023 in their name should be archived and subsequently removed.
4. The log file from 2024 (app_2024-05-01.log) must not be included in the archive and must not be deleted.

# Solution:
1. Navigate to the logs directory: `cd ~/project/logs.`
   
2. Create the compressed archive with only 2023 log files: `tar -czvf old_logs.tar.gz *2023*.log.`
  
3. After confirming the archive is created, delete the original 2023 logs: `rm *2023*.log.`

TIPS:
Use the `tar` command to create archives.

The options `-czf` are a powerful combination: c (create), z (compress with gzip), and f (specify filename).

You can use a wildcard `(*)` to select multiple files that match a pattern. For example, `*_2023-*.log` will match all files that end with .log and have _2023- in their name.

The `rm`command is used to remove (delete) files. Be careful when using it with wildcards!

