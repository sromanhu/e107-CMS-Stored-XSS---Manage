# e107 CMS Stored XSS v2.3.2

## Author: (Sergio)

**Description:** Cross Site Scripting vulnerability in e017 CMS v.2.3.2 allows a local attacker to execute arbitrary code via a crafted script to the Name filed in the Manage Menu.
**Attack Vectors:** Scripting A vulnerability in the sanitization of the entry in the Nmem of "Manage" allows injecting JavaScript code that will be executed when the user accesses the web page.

---

### POC:


When logging into the panel, we will go to the "Site Settings" section off General Menu [(http://localhost/cszcms/admin/settings)]

![image](https://github.com/sromanhu/CSZ-CMS-Stored-XSS---Site-Settings/assets/87250597/a7b3bc1d-5f87-4614-8193-946278bb3af3)





We edit that Site Settings that we have created and see that we can inject arbitrary Javascript code in the Additional Meta Tag field.


### XSS Payload:

```js
<img src=1 onerror=alert("XSS")
```


In the following image you can see the embedded code that executes the payload in the main web and the subpages:

![image](https://github.com/sromanhu/CSZ-CMS-Stored-XSS---Site-Settings/assets/87250597/222c99f0-c00e-43d5-a46e-7d7455d2b214)


![image](https://github.com/sromanhu/CSZ-CMS-Stored-XSS---Site-Settings/assets/87250597/1d5272cc-3f41-48a4-9a4c-19db4e744eda)


![image](https://github.com/sromanhu/CSZ-CMS-Stored-XSS---Site-Settings/assets/87250597/d475b79d-0e6e-4f7f-a8e1-ca361515c009)


![image](https://github.com/sromanhu/CSZ-CMS-Stored-XSS---Site-Settings/assets/87250597/4bb0d957-3ab9-4872-bdde-dc5a53160fb6)


If we log in with another user, the payload also skips:

![image](https://github.com/sromanhu/CSZ-CMS-Stored-XSS---Site-Settings/assets/87250597/3af19bb4-e666-48ca-a1de-9914f3997771)



</br>

### Additional Information:
http://cszcms.com
https://owasp.org/Top10/es/A03_2021-Injection/
https://owasp.org/www-community/attacks/xss/
