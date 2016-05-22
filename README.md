#powersort
A simple program that sorts on a column and/or regex on input.  

__usage:__   
powersort [-kfr] [file]  
-r | --regex REGEX  
-f | --file FILE  
-k | --column COLUMN  
-kCOLUMN  
example: powersort -k3 -r [0-9]{2}:[0-9]{2} /var/log/system.log  

###parameters
- -k|--column COLUMN   
selects a column on which to sort, just like regular sort.  
for example:  
```
$ echo "  
a 3
b 2
c 1" | powersort -k2

c 1
b 2
a 1
```
- -r|--regex REGEX  
will use REGEX to sort, acting upon a column if one has been selected  
for example:  
```
echo "  
xaysbidu2ahd
dsfa1dsfk
dsfk3dfks" | powersort -r [0-9]

dsfa1dsfk
xaysbidu2ahd
dsfk3dfks
```  
or:  
```
echo "
1 as2
2 3a
3 eiw1" | powersort -k 2 -r [0-9]

3 eiw1
1 as2
2 3a

```
- -f|--file FILEPATH  
chooses a file to act on, otherwise stdin will be used

#TODO
- maybe let -r contain a capture group
