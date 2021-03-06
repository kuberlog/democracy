# The construct

All of the following assumes an already existing construct. It also assumes a 3rd party VPS provider that is trusted to not snoop on the VPS's memory or registers. An HSM could also be used

To create a new construct, an existing construct does the following:
1. Uses BitLaunch to programatically launch a virtual private server
2. Retrieves SSH key from bitlaunch, SSHs into the new server, authorizes its own RSA key with the new server, removes BitLaunch generated key from authorized list
3. Stores the server's new ssh credentials in the existing construct's secrets and then reboots the new server
4. SSHs in and spins up a new construct
5. SCP the construct key to the new construct. The construct could store the key in an HSM.
6. The construct now has access to all the encrypted secrets

## BitLaunch

Bitlaunch allows a user to provision and pay for a VPS programatically. This means a construct can create an account, fund that account, and spin up a new construct, all without human intervention.

## Bootstrapping

The above flow requires an already existing construct. The first construct will need to be boostraped. I (@kuberlog) will bootstrap the first construct using my own email address, crypto wallet, etc. I expect to bootstrap at least the first 2 construct just to ensure that everything is working properly. I will consider the date that the first non-bootstraped construct goes live to be the official launch date for this project. Until then, this will probably be developed in stealth mode.
