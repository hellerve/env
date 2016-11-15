# env

An environment variable language for zepto.
It manages your environment variables and parses
them into appropriate datatypes.

It is inspired by [envy](https://github.com/lexi-lambda/envy)
for Racket and [envied](https://github.com/eval/envied) for Ruby.

## Usage

There is a simple example in the
[examples](https://github.com/hellerve/env/blob/master/examples/syntax.zp)
directory. On a high level, the syntax for the configuration
language is as follows:

```
#lang env

VARNAME
; comment
VARNAME2: <optional type>
```

Commented lines begin with semicolons.

Valid types are: `string`, `number`, `integer`, `float`, `complex`,
`ratio`, `list`, `vector`, and `hash-map`. For the number literals,
use them as they would be parsed by zepto (i.e., a ratio looks like
this: `1/1`), for collection types `env` assumes whitespace delimited
collections of strings.

```
#lang env

; mylist=1 2 3 => ["1" "2" "3"]
mylist: list
; myvec=1 2 3 => {1" "2" "3"}
myvec: vector
; myhash=1 2 3 4 => #{1" "2", "3" "4"}
myhash: hashmap
```

<hr/>
Have fun!
