export PS1="\[\033[36m\]\u\[\033[m\]@\[\033[32m\]\h:\[\033[33;1m\]\w\[\033[m\]\$ "
\[\033[: begin non-printing escape sequence
36m: cyan
\]: end the sequence
\u: username of current user
\[\033[: begin non-printing escape sequence
32m: green
\]: end the sequence
\h: hostname up to the first .
\[\033[: begin non-printing escape sequence
33;1m: brown, switch colors at the end?
\]: end the sequence
\w: current working directory, with a ~ instead of HOME
\[\033[: begin non-printing escape sequence
m
\]: end the sequene
\$: if the effective UID is 0, a #, or otherwise a $


%(?:%{%}➜ :%{%}➜ ) %{$fg[cyan]%}%c%{$reset_color%} $(git_prompt_info)

%(?:%{%}➜ :%{%}➜ ) : ternary expression where : separates true from false; true result is %{%}➜ , false result is %{%}➜ .
%{ ... %} : includes a string as a literal escape sequence; here i guess there just. is no string
%{$fg[cyan]%} : string as an escape sequence is: $fg[cyan] which accesses an associative array (the one in terminal settings im guessing)
%c: last component of CWD
%{$reset_color%} : string as an escape sequence is: $reset_color which makes the input text go back to the normal color
$(git_prompt_info)
