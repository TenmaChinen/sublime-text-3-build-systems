# sublime-text-3-build-systems

## Description
Sublime Text 3 Build-Systems for several programming languages
1. `selector` allows to define the scope of the language syntax that is detected by Sublime Text 3.
    `text` scope for text files like HTML or Markdown.
    `source` scope for code files.
2. `cmd` or `shell_cmd` allows to execute required programs for each language.

## Python
#### Python.sublime-build
`Added by default`

### JavaScript
#### JavaScript.sublime-build
```json
{
    "cmd": ["node", "$file"],
    "selector": "source.js"
}
```

### Java
#### Java.sublime-build
```json
{
    "shell_cmd": "javac $file_name && java $file_base_name",
    "selector" : "source.java"
}
```

### PostgreSQL
#### PostgreSQL.sublime-build

The username it's usually `postgres` by default when Server is created in PgAdmin

```json
{
    "shell_cmd": "set \"PGPASSWORD=your_server_password\" && psql -U your_server_username -f \"$file_name\"",
    "selector" : "source.sql"
}
```
If you want to select a default database
```json
{
    "shell_cmd": "set \"PGPASSWORD=your_server_password\" && psql -U your_server_username -d classic_models -f \"$file_name\"",
    "selector" : "source.sql"
}
```

### HTML
#### HTML.sublime-build

##### Microsoft EDGE executable path
```json
{
    "cmd": ["C:\\Program Files (x86)\\Microsoft\\Edge\\Application\\msedge.exe", "$file"],
    "selector": "text.html",
}
```
For other browser like Google Chrome, replace this path for the path where your browser `.exe` is located in your PC.

### BAT
#### batch.sublime-build

```json
{
    "cmd": "cmd /c \"${file}\"",
    "selector": "source.Batch",
    "file_patterns": ["*.bat", "*.cmd"]
}
```
