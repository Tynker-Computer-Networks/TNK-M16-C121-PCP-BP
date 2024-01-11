Crack the WiFi password.
=====================================


In this activity, you will crack the WiFi password using Brute Force Dictionary method.




<img src= "https://media.slid.es/uploads/1525749/images/10963492/Screenshot_2023-11-30_at_6.30.23_PM__1_.png" width = "100%" height = "auto">




Follow the given steps to complete this activity:
1. Crack the WiFi password.


* Open the file `main.py`.


* Reading and loading json file ("wifi.json").


```
file = open('wifi.json')
data = json.load(file)


```
* Brute force attack to get password.


```
print("Brute force attack enabled\nWait for sometime...\n")


for wifiSSID in data:
    passwordHash = data[wifiSSID]




```


* Reading the wordlist to perfrom Dictionary Attack.


```
wordListFile = open('wordlist.txt', 'r', errors='ignore')
    body = wordListFile.read().lower()
    words = body.split('\n')
    print("Searching the Password of " + wifiSSID + "\n")


```


* Iterate the loop on words list to get the valid password.
    ```
    for i in range(len(words)):
            word = words[i]
    ```


* Generate the word hash.
	```
wordHash = generateHash(word)
```


* Match the word hash with the password hash.
			```
if (wordHash == passwordHash):
                print("WiFi SSID : ", wifiSSID)
                print("Word hash: ", wordHash)
                print("Password hash: ", passwordHash)
                print("Decrypted WiFi Password: ", word)
                print("=" * 100, "\n")
                break


```


* Save and run the code to check the output.
