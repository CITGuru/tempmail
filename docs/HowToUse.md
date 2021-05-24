The TempMail Object
=========
A temp mail object must be initialized to use this library. It can be done so like this:

```python
   from tempMail2 import TempMail
   Object = TempMail(api_key = 'apikey')
```

The object can be initialized with the following parameters:

* login (string) an optional variable specifying the login for email address. If not set it will generate a random login for you to use. This can be retrieved through methods.

* domain (string) an optional variable specifying the domain for email address. If not set it will generate a random domain for you to use. This can be retrieved through methods.

* api_domain (string) an optional variable used to specify the domain of the API you want to reference. Best left alone if you don't know what this does.

* api_key (string) a REQUIRED variable for the API key. You need this in order to access the API in the first place. See [HowDoIGetAnApiKey.md](HowDoIGetAnApiKey.md) for more info on this.

It is adviseable to retain the reference to the object as that object contains the generated email and or hash.

TempMail Methods
========

***Due to the way things are currently written, all methods require a reference to an instance of a TempMail object, even if the parameters seem to imply otherwise.***

All optional parameters are in square brackets.

For the sake of these examples, we will assume all examples here are preceded by:

```python
from tempMail2 import TempMail
tempmailobj = TempMail(api_key = 'myappscoolapikey')
```

With the api_key obtusely being a stand-in for whatever API key you get from [RapidAPI](https://rapidapi.com/Privatix/api/temp-mai) for your app.

`TempMail.available_domains()`
-----
Return list of available domains for use in email address.

```python
print(tempmailobj.available_domains()[0]) #print the first avalible domain
```

`TempMail.generate_login([min_length], [max_length], [digits])`
-----
Generate string for email address login with defined length and type of characters to use.

* min_length (int) specifies the minimum length of login. Default value is ```6```.
* max_length (int) specifies the maximum length of login. Default value is ```10```.
* digits (bool) determines weather or not numbers are allowed in the generated login. Default value is ```True```.

```python
print(tempmailobj.generate_login()) #output: hsd6gvd8
print(tempmailobj.generate_login(min_length = 12, max_length = 20, digits = False)) #output: dkfkwjrsfsjiskjkdfk
```

`TempMail.get_email_address()`
-----

Returns the full email address. If the object (```tempmailobj``` in this example) was initialized with a domain and login (in our example it isn't, but it could be)
it will return the email address from those variables. Otherwise it will return the randomly generated email address from the initialization of the mail object.

```python
print(tempmailobj.get_email_address()) #output: ash7f90@gsnail.com
```

`TempMail.get_hash(email)`
-----

Gets the given hash from the given email address in the parameter, not from the object its attached to

```python
print(tempmailobj.get_hash(ash7f90@gsnail.com)) #output: b0125bdc82a0b79276f43f784dc9904a
```

- email (string)  the email to get the hash from

`TempMail.get_mailbox([email], [email_hash])`
-----

Return list of emails in given email address or dictionary with `error` key if mail box is empty.


```python
print(tempmailobj.get_mailbox())#prints the contents of your contents for your mailbox
```

- email (string) override the email to check
- email_hash (string) override the email hash to check

`TempMail.delete_email(email, [email_hash])`
-----

Delete a given email in a given email address.


```python
tempmailobj.delete_email(email = tempmailobj.get_email_address())#'Delete a given email in a given email address' (what does that even mean?)
```

- email (string) override the email address
- email_hash (string) override the email hash to check

`TempMail.get_attachments(email, [email_hash])`
-----

Get attachments of a given email in a given email address.


```python
tempmailobj.get_attachments(email = tempmailobj.get_email_address())#'Get attachments of a given email in a given email address' (what does that even mean?)
```

- email (string) override the email address
- email_hash (string) override the email hash to check

`TempMail.get_message(email, [email_hash])`
-----

Get a given email in a given email address.


```python
tempmailobj.get_message(email = tempmailobj.get_email_address())#'Get a given email in a given email address.' (what does that even mean?)
```

- email (string) override the email address
- email_hash (string) override the email hash to check

`TempMail.source_message(email, [email_hash])`
-----

Source a given email in a given email address.

```python
tempmailobj.source_message(email = tempmailobj.get_email_address())#'Source a given email in a given email address.' (what does that even mean?)
```

- email (string) override the email address
- email_hash (string) override the email hash to check