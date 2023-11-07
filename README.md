# (f)inder

Find anything, everywhere, and search within results. 

**TL;DR:** `f` is meant to eliminate having to type out long find/grep/xargs commands and account for spaces.

## Help

```console
$ f -h  # Contains everything you need
```

## Install

Simply place a copy of `f` in your PATH (e.g. in `~/bin` or `/usr/bin` or where ever). Or, clone this project and softlink to `f`.

## Commands / Options

```console
  $ f d|f|af|cf|pf|i|ia|ic|ip|if|iaf|icf|ipf [-P|N|n|[Ip]] [-<GREP_OPTIONS>] Arg1 [Arg2]'

  All commands operate on current directory. f options can be followed by grep options.

    1-PATTERN:
       d    : Find                     (d)irectory $Arg1
       f    : Find                     (f)ile      $Arg1
      af    : Find            (a)da    (f)ile      $Arg1
      cf    : Find            (c)      (f)ile      $Arg1
      pf    : Find            (p)ython (f)ile      $Arg1
      i     : Find $Arg1 (i)n any      file
      ia    : Find $Arg1 (i)n (a)da    file
      ic    : Find $Arg1 (i)n (c)      file
      ip    : Find $Arg1 (i)n (p)ython file

    2-PATTERN:
      if    : Find $Arg1 (i)n          (f)ile      $Arg2
      iaf   : Find $Arg1 (i)n (a)da    (f)ile      $Arg2
      icf   : Find $Arg1 (i)n (c)      (f)ile      $Arg2
      ipf   : Find $Arg1 (i)n (p)ython (f)ile      $Arg2
  
  OPTIONS:
    -I      : Str(I)ct case (ignorecase is the default)
    -p      : Print (p)lainly without highlighting
    -P      : (P)rint the command that would run
    -n      : Search for (n)otes within files, used with 1-PATTERN i* cmds,
              no PATTERNs are necessary
    -w      : Search for (w)arnings/errors/etc, used with 1-PATTERN i* cmds,
              no PATTERNs are necessary
    -N      : Search for (N)asty words within files, used with 1-PATTERN i* cmds,
              no PATTERNs are necessary
```

## Examples

### Find a C file containing "run", without highlighting and with strict-case

```f cf -Ip run```

### Find the following tags inside a python file, disregarding case

```f ip "(xxx|fixme|todo|removeme)"```

### Count the number of directories that end in bin

```f d -c bin$```

### Search for any notes in c files below .

```f ic -n```

### Print the command to find "ABC" inside an Ada file that contains the string

```f iaf -P ABC user```
