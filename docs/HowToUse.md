TempMail Object
=========
A temp mail object must be initlised to use this library. It can be done so like this:

```
   from tempMail2 import TempMail
   Object = TempMail(api_key = 'apikey')
```

The object can be initlised with the folowing paramieters:
* login (string) an optional varible specifying the login for email address. If not set it will generate a random login for you to use. This can be retreved through methods.
* domain (string) an optional varible specifying the domain for email address. If not set it will generate a random domain for you to use. This can be retreved through methods.
* api_domain (string) an optional varible used to specify the domain of the API you want to refrence. Best left alone if you don't know what this does.
* api_key (string) a REQUIRED varible for the api key. You need this in order to access the API in the first place. See `How Do I Get An Api Key.md <tempmail/docs/HowDoIGetAnApiKey.md>` for more info on this.

If you are confused about what going on here, maybe try looking at a few python toturials that specificaly cover classes and objects and how they are used, although you probally already know if you ever gone through a python toturial.

TempMail Methods
========

For the sake of these examples, we will assume all examples here are preceded by::

    from tempMail2 import TempMail
    tempmailobj = TempMail(api_key = 'myappscoolapikey')

With the api_key obtously being a stand-in for whatever api key you get from the `api <https://rapidapi.com/Privatix/api/temp-mail>` for your app.

TempMail.available_domains()
-----
Return list of available domains for use in email address.

```
print(tempmailobj.available_domains()[0]) #print the first avalible domain
```

TempMail.generate_login([min_length], [max_length], [digits])
-----
Generate string for email address login with defined length and type of characters to use.

* min_length (int) specifies the minimum length of login. Default value is ``6``.
* max_length (int) specifies the maximum length of login. Default value is ``10``.
* digits (bool) determines weather or not numbers are allowed in the generated login. Default value is ``True``.

```
print(tempmailobj.generate_login()) #example output: hsd6gvd8
print(tempmailobj.generate_login(min_length = 12, max_length = 20, digits = False)) #example output: dkfkwjrsfsjiskjkdfk
```
   
TempMail.get_email_address()
-----

Returns the full email address. If the object (```tempmailobj``` in this example) was initalised with a domain and login (in our example it isn't, but it could be)
it will return the email address from thoes varibles. Otherwise it will return the randomly generated email adress form the initlisation of the mail object.

```
tempmailobj.get_email_address() #example output: ash7f90@gsnail.com
```

TempMail.get_hash(email)
-----



TempMail.get_mailbox(email, email_hash)
-----

TempMail.delete_email(email, email_hash)
-----

TempMail.get_attachments(email, email_hash)
-----

TempMail.get_message(email, email_hash)
-----

TempMail.source_message(email, email_hash)
-----
