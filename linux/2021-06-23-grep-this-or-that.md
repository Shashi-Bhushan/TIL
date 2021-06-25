# Grep multiple things

We could grep for multiple conditions using regex pattern. 
For eg. 
```shell
cat ... | grep 'this\|that' 
```

this will search for the string `this` or `that` from previous piped command. Check this for more details https://unix.stackexchange.com/questions/82990/how-can-i-grep-for-this-or-that-2-things-in-a-file
