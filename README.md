# virustotalx for endpoints 

# Installation 

```
git clone https://github.com/orwagodfather/virustotalx.git
```

```
cd virustotalx
```


create a 3 accounts [https://www.virustotal.com/gui/join-us](https://www.virustotal.com/gui/join-us) and copy the 3 api keys ===>

```
nano orwa.sh
```

paste 3 api keys here ....


```
  if [ $api_key_index -eq 1 ]; then
    api_key="key-1"
  elif [ $api_key_index -eq 2 ]; then
    api_key="key-2"
  else
    api_key="key-3"
  fi
```

**Ex**

```
  if [ $api_key_index -eq 1 ]; then
    api_key="XXXXXXXXXXXXXX1"
  elif [ $api_key_index -eq 2 ]; then
    api_key="XXXXXXXXXXXXXX2"
  else
    api_key="XXXXXXXXXXXXXX3"
  fi
```


**next step**

`chmod +x orwa.sh` 


# Usage

Create sub domain file `EX` ===> `subdomain.txt`  ===> `wihtout http/s` 

**===>**


```
./orwa.sh subdomain.txt | tee results.txt 
```

**===>**

Added by Nepax
If you encounter the issue of jq
jq: parse error: Invalid numeric literal at line 1, column 10

Follow below steps:
1. wget -O jq https://github.com/jqlang/jq/releases/download/jq-1.6/jq-linux64
2. sudo apt remove jq
3. chmod +x ./jq
4. sudo cp jq /usr/bin

5. Or simply clone this repo
6. And follow from step 3 but dont forget to run step 2 to remove existing jq that is making the issue.

```
cat results.txt | egrep 'http|https' > endpoints.txt
```

