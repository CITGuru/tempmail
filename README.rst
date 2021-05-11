Tempmail2
=========

Python API Wrapper version 2 for `temp-mail.org <https://temp-mail.org/>`_ service. Temp-mail.org is a service which lets you use anonymous emails for free. You can view full API specification in `rapidapi.com/Privatix/api/temp-mail <https://rapidapi.com/Privatix/api/temp-mail>`_.

Requirements
------------

`requests <https://crate.io/packages/requests/>`_ - required.

You can install it through the command line ::

 $ pip install requests

Installation
------------

Installing with pip through the command line::

    $ pip install tempMail2

Usage
-----

Before you can use this, you need to get api key from https://rapidapi.com/Privatix/api/temp-mail.

So create an account on Rapid API and get the Key by creating an app on there.

A good start would be to impoort the class from the module::

    from tempMail2 import TempMail

Examples
-----

Get all emails from given email login and domain::

    from tempMail2 import TempMail

    tm = TempMail(api_key='yourRapidAPIAppkey', login='coolusername', domain='@domaingiven.com')
    print (tm.get_mailbox())  # retreves the list of emails in coolusername@domaingiven.com

Generate email address and get emails from it::

    from tempMail2 import TempMail

    tm = TempMail(api_key='yourRapidAPIAppkey')
    email = tm.get_email_address()  # v5gwnrnk7f@gnail.pw for example
    print (tm.get_mailbox(email))  # list of emails
