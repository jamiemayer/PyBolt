# PyBolt Client

----

Small lightweight library intended to be used for getting and decrypting passwords from a passbolt server.

## Installation

To install from PyPi:
```shell
pip install pybolt_client
```

## Usage

The library uses one class names `Client`.

**Positional Arguments**

* `url` - The url of the passbolt server you wish to connect to.

**Keyword Arguments**

* `gpg_path` - The path to the users gpg home directory. This will default to `~/.gnupg/`.
* `private_key_path` - The path the the users private GPG key. Defaults to `~/.gnupg/private.key`.
### Retrieving a password.
Password retrieval is relatively simple. First we need to instantiate an instance of `Client` and then 
call the `get_password_by_name` method, passing it the name of the password as set in passbolt. 

Example:

```python
from passbolt_client import Client

client = Client("https://passbolt.example.com")

print(client.get_password_by_name("Rees-Mogg's Onlyfans"))

```