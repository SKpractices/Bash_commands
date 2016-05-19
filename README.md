# Bash_commands



To display all files in subdirectories: \n
find . -maxdepth 1 -mindepth 1 -type d | while read dir; do
  printf "%-25.25s : " "$dir"  
  find "$dir" -type f | wc -l  
  done


To count number of files in the sub directory of current directory.   

find . -maxdepth 1 -type d -print0 | xargs -0 -I {} sh -c 'echo -e $(find {} | wc -l) {}' | sort -n


