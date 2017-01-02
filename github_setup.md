

```python
import os
username = 'drscook'
useremail = 'scook@tarleton.edu'
os.system('git config --global --replace-all user.name ' + username)
os.system('git config --global --replace-all user.email ' + useremail)

rsafile = '/home/ubuntu/.ssh/id_rsa'
if os.path.isfile(rsafile):
    print('RSA key exists\n')
else:
    os.system('ssh-keygen -t rsa -b 4096 -N "" -C ' + useremail + ' -f ' + rsafile)
os.system('eval "$(ssh-agent -s)"')
os.system('ssh-add ' + rsafile)
print('Copy this public key to your github profile\n')
with open(rsafile + '.pub', 'r') as f:
    print(f.read())
```

    RSA key exists
    
    Copy this public key to your github profile
    
    ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAACAQDaZ0N03VXt959ulsGajM+mlp8lCgLdlfwnucPCxUVEYO2EhilxyjFlKIinOyz1A7+tfeF1cX8Jyu2FCzfWX/1e5TqjeqdykNV8iqMa64hK97Mwcw3hrOtu1Rofvv2LXmo76qTXDQuRLqam1sVe7eYuYtyhUe5AQaeaab/a0h5ggl3galJ8s7SXzd4vRfHLmZZwH0TvzqX+dlAoejmwjk8CD7LrPmP41lvaIOsCKVuL4H+d+QaB4ryFirWBcdT6pD51tH6W+eBCyGO2ENSt4pt/GvNZq8DwMN3gm52gOctmoPbgf3rb/iefzNLHoWbCH7cY0AGr5f9t5VgPxSUlBjFnJO91tO5kZR7wdEjplbeUTg6PHWdqyM0oNNxV8L0liogD0hSbf0Jn033ZyvIUlrtcbCp9BX6R9OXYbDt5hmzM/Tbx9F6NJAAGEQH7nIjueIR84hRtwAM2m8zlIzeSX3axYPjAFPJFAyGT5fYhf49y4a7ZoecFhiRpg3J5IxZzF+l1ZNB953zN6BZ7QFEpVJbgaHwW1s1VJ50jO3TVzyVjdGXlJ8QsWDaQVwVVzBfdfs6dcBX+KtiQO8S+NwyibAWN+ZBBnow13OYEtj/vRieSkCXN2oJdDJvbRN6CPuGx0MeAdHPKNny1LucqUEkQ4cS2deQsjWzwCI3HzYzuch/oDQ== scook@tarleton.edu
    



```python
import os
gitdirname = '/home/ubuntu/notebooks/test2'
url = 'git@github.com:drscook/test2.git'

try:
    os.mkdir(gitdirname)
    print('Creating directory ' + gitdirname)
except:
    print('Directory ' + gitdirname + ' already exists')
    pass
os.chdir(gitdirname)
os.system('git clone ' + url + ' .')
os.system('git pull')
testfile = gitdirname + '/testgit.md'
with open(testfile, 'a') as f:
    f.write("If you can read this, I can push to github\n\n")
os.system('git add ' + testfile)
os.system('git commit -m "Testing git write access"')
os.system('git push')
```

    Directory /home/ubuntu/notebooks/test2 already exists





    0




```python
msg = '"Testing git write access"'
os.system('git add *.ipynb')
os.system('git add *.html')
os.system('git commit -m ' + msg)
os.system('git push')
```




    0




```python
with open()
```


```python
os.path.isfile("/home/ubuntu/.ssh/id_rsa")
```




    True




```python
a=4
```

a = 4

https://help.github.com/articles/generating-an-ssh-key/
http://stackoverflow.com/questions/6565357/git-push-requires-username-and-password


create and cd into desired directory
git init



```python
git commit -am.
git push
```
