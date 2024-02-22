# Praktikum 2 - Paroolide murdmine  

Teises praktikumis tegelesime paroolidega. Õppisime räsi ja soola kohta. Murdsime jõumeetodil pythoni koodiga paroole.  
Kasutasime John'i eesti sõnastiku abil. 

Ül1
Kuus leitud salasõna olid 'ut', 'ati', 'hack', 'hd', 'led', 'asdf'

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
Ül2  
![2](https://github.com/JuhanPauklin/AndmeturbePraktikumid/assets/90179916/9c2ed5fc-4bdf-49f2-89ed-dbcc810ae177)  

Ül3  
Matrikkel: C03189
Password: peace1
![3](https://github.com/JuhanPauklin/AndmeturbePraktikumid/assets/90179916/56f6a53e-2264-456c-9a39-a0bba339da08)

