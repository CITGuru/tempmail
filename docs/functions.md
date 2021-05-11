TempMail Methods
=========



For the sake of these examples, we will assume all examples here are preceded by::

    from tempMail2 import TempMail
    tempmailobj = TempMail(api_key = 'myappscoolapikey')

With the api_key obtously being a stand-in for whatever api key you get from the `api <https://rapidapi.com/Privatix/api/temp-mail>` for your app.
If you are confused about what going on here, maybe try looking at a few pyhton toturials that specificaly cover classes and objects.

TempMail.available_domains()
-----
This gets all the availble doamins for email adress that you can receve.
Returns it as a dictionary (TODO: check this once the thing starts working again).

    print(tempmailobj.available_domains())

TempMail.generate_login(min_length, max_length, digits)
-----

TempMail.get_email_address()
-----

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
