# shell-data-processing

## Bash Notes

### Redirects
```[command] > [outputFile]``` will redirect output to a file. Will overwrite if the file exists.

```[command] >> [outputfile]``` will redirect output to a file. Will append if the file exists.

Example:
```ls > lsOutput.txt``` will write the output of `ls` to `lsOutput.txt`.

### Pipes
Use `|` to send output (potentially binary data) to another command. 

Example:
`curl https://web.njit.edu/~cm395/theBeeMovieScript/ | grep "bee"` 
will pipe (send) the output of `curl` to `grep`. `grep` will process this as input, and will print all lines containing "bee" (case-sensitive).

## How I sorted the data

`wget https://web.njit.edu/~cm395/theBeeMovieScript/`

Then...

`tr ' ' '\12' < index.html | sort | uniq -c | sort -nr > result.txt`

