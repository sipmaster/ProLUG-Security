streamer1@prolug.asuscomm.com
streamer1 - BigLab56%^

**Bash commands help:**

Find commands you need using:
    - `apropos <keyword>` - Each manual page has a short description available within it.   `apropos` searches the descriptions for instances of `keyword`. This helps to find if a command will suit your needs.
        - `apropos -s <section_number> <keyword>` - Limit the search of `keyword` to section `<section_number>` of the manpages.
- Read this short refresher on Linux Man Pages and how they work, how sections work in manpages, how `man` command works! Before proceeding!
    - `man <command>` - Search for a particular command in all manpages and display the first instance
        - `man -f <command>` or `whatis <command>`  - Searches for the `<command>` across all sections of the manual and lists the results with the corresponding section number and the one-line description from each manpage.
        - `man <manpage_section_number> <term>` - Search for `<term>` in section `<manpage_section_number>` of the manpage and display it. Must for opening specific commands like `adduser(8)`, where `8` is the `<manpage_section_number>`.
- `whereis <command>` - Lists paths of where the command is installed and paths of its corresponding manpages.
- `which <command>`- shows the exact location of a given executable. Only works for executable programs

