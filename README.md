This shell script automates the creation of a directory structure containing multiple project folders, and finds folders named oriserve. In those oriserve directories, it creates a file named test.txt.

Create a directory named projects and inside it, create multiple subdirectories representing projects (e.g., facebook, google, meta, oracle).

The script should find all oriserve subfolders in the projects directory and create a test.txt file in those oriserve folders.
projects/
├── facebook
├── google
│   └── oriserve
│       └── test.txt
├── meta
│   └── oriserve
│       └── test.txt
└── oracle



Steps Implemented in the Script-

Creating the Directory Structure:
The script creates the following directories:
projects/facebook
projects/google/oriserve
projects/meta/oriserve
projects/oracle

Finding the oriserve Folders:
The script searches for directories named oriserve within the projects directory.

Creating test.txt:
For each oriserve directory found, the script creates a test.txt file containing a custom message.

#!/bin/bash

# Define the projects directory
PROJECTS_DIR="projects"

# Step 1: Create the directory structure
mkdir -p $PROJECTS_DIR/facebook
mkdir -p $PROJECTS_DIR/google/oriserve
mkdir -p $PROJECTS_DIR/meta/oriserve
mkdir -p $PROJECTS_DIR/oracle

echo "Directory structure created."

# Step 2: Find 'oriserve' directories and create a test.txt file in them
find $PROJECTS_DIR -type d -name "oriserve" | while read oriserve_dir; do
    echo "This is the test file inside the oriserve directory" > "$oriserve_dir/test.txt"
    echo "Created test.txt in $oriserve_dir"
done

echo "Process completed. All 'oriserve' directories now contain a test.txt file."

Execute the script to create the directory structure and test.txt files:
./create_oriserve_dirs.sh


