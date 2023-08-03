# awk

ps will print a columns, $1 will print first column

```bash
ps | awk '{print $1}'
```

mutiple columns

```bash
ps | awk '{print $1, $3}'
```

**column separator** is a space by default, use -F to change it

```bash
awk -F ":" '{print $1}' /etc/passwd
```

to change **output column separator**, put it inside 
double quote ( "_" mean underscore output separator )

```bash
ps | awk '{print $1"_"$3}'
```

use a **pattern matching**, "NF" is the **columns length**,
hence $NF is the last column since indexing start at 1

```bash
awk -F "/" '/^\// {print $NF}' /etc/shells
```

**functions**

```bash
awk 'length($0) > 7' /etc/shells
```

**conditions**

```bash
ps -ef | awk '{ if($NF == "/bin/zsh") print $0}'
```

**multiple expression**, called if condition is true, on each line

```bash
awk '/^#/ { if ($0 == "# "selected) p = 1; else if (p) exit; } p && NF { print; }'
```

explanation:

- `{ if ($0 == "# "selected) p = 1; else if (p) exit; }`
  - one expression, always called on each line
- `p && NF { print; }`
  - other expression, called when condition (`p && NF`) is true