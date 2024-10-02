# OverTheWire Bandit Level 12

## Objective

The OverTheWire Bandit wargame level 12 had a password stored in the `data.txt` file which was a hexdump of a file that had been repeatedly compressed. The primary focus of of this level was to teach the user how to create a temporary directopry and to decompress files repeatedly. This more intensive level was designed to devlop an underestanding of problem solving, utilizing the `man` command, and understanding decompression techniques.

### Skills Learned

- File manipulation (ex. creating and copying directories)
- Decompression techniques (`gzip` and `bzip2`)
- Understanding hexdump
- Critical thinking and problem solving

### Tools Used

- Linux terminal
- `ssh`, `ls`, `cp`, `mktemp -d`, `cd`, `xxd -r`, `file`, `mv`, `gzip`, `bzip2`, `rm`, `tar`, `xf`, `cat`

## Steps

*Reference 1: File Decompressing*

![Screenshot 2024-10-02 021017](https://github.com/user-attachments/assets/d61cb9fd-1cd3-445f-aacf-c09d748c70ca)

*Reference 2: `tar` Inclusion and Final Password*

![Screenshot 2024-10-02 022152](https://github.com/user-attachments/assets/114178f7-09ca-42fe-a1d0-ad947a418f88)

*Reference 1 Explanation*

After logging into level 12 and `ls` the directory, I `man` the `xxd` as I was unfamiliar with the command. I then began by creating a temporary directory and reversing the `data.txt` hexadump into its binary state, saving the output in a new file called `data`. Once that was set up, a repetitive process of `file`, `mv`, and `gzip -d` and `bzip2 -d` took place due to the multiple times the file had been compressed.

*Reference 2 Explanation*

Eventually, a `tar` file had appeared; another thing I had never seen before. This archive required a bit of a different approach, utlizing `xf` in order to obtain the correct file which needed to be decompressed. All of this funneled into the final `data` file, containing the ASCII text with the password. Once I used the `cat` command, I successfully completed the level.
