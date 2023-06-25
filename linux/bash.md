# Bash

quick reference

```bash
# variable
name="John"

# string interpolation
echo "I'm in $(pwd)"

# conditional
if [[ -z "$string" ]]; then
  echo "String is empty"
elif [[ -n "$string" ]]; then
  echo "String is not empty"
fi

# conditional execution
git commit && git push
git commit || echo "Commit failed"

# fn
get_name() {
  echo "John is $1"
}
echo "You are $(get_name "wp" )"

# path expansion
echo {A,B}.js
# {A,B}     Same as A B
# {A,B}.js  Same as A.js B.js
# {1..5}    Same as 1 2 3 4 5
```

arguments

- `$#`  Number of arguments
- `$*`  All positional arguments (as a single word)
- `$@`  All positional arguments (as separate strings)
- `$1`  First argument
- `$_`  Last argument of the previous command

parameter expansion

```bash
name="John"
echo "${name}"
echo "${name/J/j}"    #=> "john" (substitution)
echo "${name:0:2}"    #=> "Jo" (slicing)
echo "${name::2}"     #=> "Jo" (slicing)
echo "${name::-1}"    #=> "Joh" (slicing)
echo "${name:(-1)}"   #=> "n" (slicing from right)
echo "${name:(-2):1}" #=> "h" (slicing from right)
echo "${food:-Cake}"  #=> $food or "Cake"

length=2
echo "${name:0:length}"  #=> "Jo"

str="/path/to/foo.cpp"
echo "${str%.cpp}"    # /path/to/foo
echo "${str%.cpp}.o"  # /path/to/foo.o
echo "${str%/*}"      # /path/to

echo "${str##*.}"     # cpp (extension)
echo "${str##*/}"     # foo.cpp (basepath)

echo "${str#*/}"      # path/to/foo.cpp
echo "${str##*/}"     # foo.cpp

echo "${str/foo/bar}" # /path/to/bar.cpp

str="Hello world"
echo "${str:6:5}"   # "world"
echo "${str: -5:5}"  # "world"

src="/path/to/foo.cpp"
base=${src##*/}   #=> "foo.cpp" (basepath)
dir=${src%$base}  #=> "/path/to/" (dirpath)


${foo%suffix}   # Remove suffix
${foo#prefix}   # Remove prefix
${foo%%suffix}  # Remove long suffix
${foo/%suffix}  # Remove long suffix
${foo##prefix}  # Remove long prefix
${foo/#prefix}  # Remove long prefix
${foo/from/to}  # Replace first match
${foo//from/to} # Replace all
${foo/%from/to} # Replace suffix
${foo/#from/to} # Replace prefix


${foo:0:3}    # Substring (position, length)
${foo:(-3):3} # sSubstring from the right

${#foo}       # Length of $foo


str="HELLO WORLD!"
echo "${str,}"   #=> "hELLO WORLD!" (lowercase 1st letter)
echo "${str,,}"  #=> "hello world!" (all lowercase)

str="hello world!"
echo "${str^}"   #=> "Hello world!" (uppercase 1st letter)
echo "${str^^}"  #=> "HELLO WORLD!" (all uppercase)

${foo:-val}     # $foo, or val if unset (or null)
${foo:=val}     # Set $foo to val if unset (or null)
${foo:+val}     # val if $foo is set (and not null)
${foo:?message} # Show error message and exit if $foo is unset (or null)

# Omitting the : removes the (non)nullity checks, e.g. ${foo-val} expands to val if unset otherwise $foo.
```

conditionals

Conditions
Note that [[ is actually a command/program that returns either 0 (true) or 1 (false). Any program that obeys the same logic (like all base utils, such as grep(1) or ping(1)) can be used as condition, see examples.

```bash

[[ -z STRING ]] Empty string
[[ -n STRING ]] Not empty string
[[ STRING == STRING ]] Equal
[[ STRING != STRING ]] Not Equal
[[ NUM -eq NUM ]] Equal
[[ NUM -ne NUM ]] Not equal
[[ NUM -lt NUM ]] Less than
[[ NUM -le NUM ]] Less than or equal
[[ NUM -gt NUM ]] Greater than
[[ NUM -ge NUM ]] Greater than or equal
[[ STRING =~ STRING ]] Regexp
(( NUM < NUM )) Numeric conditions
More conditions
[[ -o noclobber ]] If OPTIONNAME is enabled
[[ ! EXPR ]] Not
[[ X && Y ]] And
[[ X || Y ]] Or
File conditions
[[ -e FILE ]] Exists
[[ -r FILE ]] Readable
[[ -h FILE ]] Symlink
[[ -d FILE ]] Directory
[[ -w FILE ]] Writable
[[ -s FILE ]] Size is > 0 bytes
[[ -f FILE ]] File
[[ -x FILE ]] Executable
[[ FILE1 -nt FILE2 ]] 1 is more recent than 2
[[ FILE1 -ot FILE2 ]] 2 is more recent than 1
[[ FILE1 -ef FILE2 ]] Same files
```

Example

```bash
# String
if [[ -z "$string" ]]; then
  echo "String is empty"
elif [[ -n "$string" ]]; then
  echo "String is not empty"
else
  echo "This never happens"
fi
# Combinations
if [[ X && Y ]]; then
  ...
fi
# Equal
if [[ "$A" == "$B" ]]
# Regex
if [[ "A" =~ . ]]
if (( $a < $b )); then
   echo "$a is smaller than $b"
fi
if [[ -e "file.txt" ]]; then
  echo "file exists"
fi
```

loop

```bash
for i in /etc/rc.*; do
  echo "$i"
done

for ((i = 0 ; i < 100 ; i++)); do
  echo "$i"
done

for i in {1..5}; do
  echo "$i"
done

for i in {5..50..5}; do
  echo "$i"
done

# each line
while read -r line; do
  echo "$line"
done <file.txt

while true; do
  ···
done
```
