An Ansible module for DNSimple API 2.0
======================================

This module assumes you have a DNSimple account, and have an appropriately
registered DNS domain set up in DNSimple.  You also need an API key or token
from DNSimple, and your DNSimple account id.

This project makes use of the dnsimple python module: https://github.com/onlyhavecans/dnsimple-python.  Install it with:

pip install -r requirements.txt

As this module is not yet part of the Ansible codebase, you can install it in your playbook under the library/ directory, simply copy the dnsimple.py module to the library directory.

Example Task
============

Add the following to your playbook.

  - name: register device with dnsimple
    dnsimple:
      type: "A"
      ttl: "60"
      name: "hostname"
      content: "10.0.0.10"
      domain: "example.com"
      dnsimple_token: "ABCDEF0123456789"
      dnsimple_account: "12345"
      state: "present"

