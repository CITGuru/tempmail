Tempmail2
=========

Python API Wrapper version 2 for `temp-mail.org <https://temp-mail.org/>`_ service. Temp-mail.org is a service which lets you use anonymous emails for free. You can view full API specification in `api.temp-mail.org <http://api.temp-mail.org/>`_.

Requirements
------------

`requests <https://crate.io/packages/requests/>`_ - required.

You can install it through ::

 $ pip install requests

Installation
------------

Installing with pip::

    $ pip install tempMail2

Usage
-----

Before you can use this, you need to get api key from https://rapidapi.com/Privatix/api/temp-mail.

So create an account on Mashape and get the Mashape Api Key

Get all emails from given email login and domain::

    from tempMail2 import TempMail

    tm = TempMail(api_key='apikey', login='denis', domain='@gnail.pw')
    print tm.get_mailbox()  # list of emails in denis@gnail.pw

Generate email address and get emails from it::

    from tempMail2 import TempMail

    tm = TempMail(api_key='apikey')
    email = tm.get_email_address()  # v5gwnrnk7f@gnail.pw
    print tm.get_mailbox(email)  # list of emails
