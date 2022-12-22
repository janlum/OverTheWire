# OverTheWire Leviathan Level 3

## Credentials
username: leviathan3
password: Q0G8j4sakn

## Writeup

To keep a shell open after piping an `echo` command into an executable, use the following syntax.

```
(echo "asdf"; cat) | ./executable
```

Using `ltrace`, we can see that the executable compares the input password with the term "snlprintf". Using this password, we obtain a shell to leviathan4 which gives us the flag.

## Flag
Level 4 Password: AgvropI4OA
