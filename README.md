# IntelliJ IDEA launcher

### SYNOPSIS
`idea [-fv] [project] [file]`

### DESCRIPTION
`idea` opens or creates a file and launches IntelliJ with the given or parent project.  
Output redirection to file is also supported.  
If the project or file are not found, prompt the user for creation.

### OPTIONS

```
project A path to directory with IDEA project (default is working directory).
        If a project is not found, idea will recursively search for a parent project.
        If a parent project is not found idea will create one.

file    Path to a file.
        If the file is not found idea will create one.

When a single none-existing path is passed (file or project), idea will
treat the path as file and use the working directory as project.

-f      Force creation without prompting for confirmation.
-v      Verbose mode.
```

### EXAMPLES

###### Open the project in the current working directory or a parent directory:
```
$ idea
$ idea .
```

###### Open/create a file using the project in the current or a parent directory:
`$ idea my-file`

###### pipe stdin into a new/existing file
`kubectl logs -f pod | idea my-file`

###### Open the file using the project in the given or parent directory:
`$ idea my-project my-file`