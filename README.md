# docker-cheat-sheet

Docker Cheat Sheet. Here you'll find tips and tricks how to use docker containers efficiently.

## Docker Names

Do not use docker names if you want to do things programmatically. They will make things difficult, since names are unique. Instead, store IDs on variables to reference them externally.

To get the container ID programmatically:

```
d=$(docker run -dP nginx)
echo $d
```

From now on where `$d` will refer to a container ID.

## Docker Containers Filters

To get programmatically the exposed port of a container:

```
echo ${$(docker port $d 80)#*:}
```

For more info on variable transformation see [here](http://stackoverflow.com/a/15548660/1776889)
