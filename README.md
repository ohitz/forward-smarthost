forward-smarthost
=================

This script was used for a mailserver migration (qmail to postfix). It
can be called from .qmail on the old server to forward all received
messages for an account to the new server so the messages will
eventually end up on the new server.

The script can be called in the .qmail file as follows:

  `|forward-smarthost smarthost1 smarthost2 smarthost3 ...`
  
The first smarthost to accept the mail will be used. Sender and
recipient are taken from the `SENDER` and `RECIPIENT` environment
variables. In addition, `anything@-` is stripped off the recipient.

The program can be tested from the commandline as follows:

  `cat mail.txt | SENDER=sender@domain.com RECIPIENT=recipient@domain.com ./forward-smarthost`
