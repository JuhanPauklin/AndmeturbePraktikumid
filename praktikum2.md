# Praktikum 2 - Paroolide murdmine  

Teises praktikumis tegelesime paroolidega. Õppisime räsi ja soola kohta. Murdsime jõumeetodil pythoni koodiga paroole.  
Kasutasime John'i eesti sõnastiku abil. 

Ül1
```python
import string, crypt

encrypted_list = [
    "XZkMWgaNMr552",
    "$6$SomethingHere$L5zuxicIHC90jGVZ9xgoOjUw36DjduwH1nPGJ.uwcgLqCvhlGe6wWp55eojE9jAIXxDbcsmbAKLXuXg2AbKZo0"
    ]
i = 0
pass_list = []

for encrypted in encrypted_list:
    if i < 1:
        salt = encrypted[:2]
    else:
        osad =  encrypted.split("$")
        salt = "$" + osad[1] + "$" + osad[2] + "$"
    print (salt)
    i += 1
    for c1 in string.ascii_lowercase:
        for c2 in string.ascii_lowercase:
            for c3 in string.ascii_lowercase:
                for c4 in string.ascii_lowercase:

                    passwd = c1 + c2 + c3 + c4
                    if encrypted == crypt.crypt(passwd, salt):
                        print ('parool on: ' + passwd)
                        if passwd not in pass_list:
                            pass_list.append(passwd)
                        break
print(pass_list)

```
