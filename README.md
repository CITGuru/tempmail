# Tempmail2

Python API Wrapper version 2 for [temp-mail.org](https://temp-mail.org/) service. [Temp-mail.org](https://temp-mail.org/) is a service which lets you use anonymous emails for free. You can view full API specification on the [RapidAPI Page](https://rapidapi.com/Privatix/api/temp-mail).

## Installation

### Requirements

[Requests](https://crate.io/packages/requests/) is required for this module to work. You can install it through the command line:

```bash
pip install requests
```

### Installation

Install with pip through the command line:

```bash
pip install tempMail2
```

## Usage

Before you can use this, you need to get api key from [RapidAPI](https://rapidapi.com/Privatix/api/temp-mail). See [HowDoIGetAnApiKey.md](docs\HowDoIGetAnApiKey.md) if you need more info on this.

See [HowToUse.md](docs\HowToUse.md) for what all the methods  and the class does.

### Examples

Get all emails from given email login and domain:

```python
from tempMail2 import TempMail

tm = TempMail(api_key='yourRapidAPIAppkey', login='coolusername', domain='@domaingiven.com')
print (tm.get_mailbox())  # retreves the list of emails in coolusername@domaingiven.com
```

Generate email address and get emails from it:

```python
from tempMail2 import TempMail

tm = TempMail(api_key='yourRapidAPIAppkey')
email = tm.get_email_address()  # v5gwnrnk7f@gnail.pw for example
print (tm.get_mailbox(email))  # list of emails
```