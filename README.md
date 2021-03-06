# Introduction

A python library for interacting with the Trend Deep Security Management API.


# Usage

The `Connection` class is the main entry point.  It is designed to be used as a context manager to ensure that the
connection is closed cleanly and consistently.

Example:

```
with Connection(wsdl, user, pass) as trend:
    for profile in  trend.security_profiles.all():
        profile.rules = trend.firewall_rules.by_ids(profile.firewallRules.item)
```

See the Trend API documention for more details on the objects and methods available.

# Contributing

Make a fork, fix and send a Pull Request.

# Hacking

Create a new virtual environment and install the required packages

```
virtualenv venv
source ./venv/bin/activate
python setup.py install
```

Run the unit tests

```
python -m unittest discover
```
or
```
python setup.py test
```