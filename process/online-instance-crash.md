## Online Instance Crash

It occurs when we receive an email from our infrastructure monitor
that tells us that a Cozy instance crashed:

1. An email arrives in our Mailbox
2. We run a salt recipe of recovering
3. If that's not enough, the Cozy is restarted manually
4. If the downtime exceeds 30 minutes, a product owner send an 
   apologize email to the user of the instance.
