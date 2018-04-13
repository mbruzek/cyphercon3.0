# Developers, developers, developers.
# When DevOps Fails to Secure.

By: David Bryan (VideoMan)

I came in after David started his talk but it was very good. He was talking
about using SSH keys are not enough. We all should be using
[SSH Agent forwarding](https://developer.github.com/v3/guides/using-ssh-agent-forwarding/)
to secure our keys.

David pointed out several ways that developers misuse ssh keys.

One pentest got access to a server and did a simple search for "id* or "ssh*"
inside unprotected  files and found ssh keys that allowed access to other
systems.

VM images contain ssh keys and they may be stored on a NAS that has a default
username/password combination. Or too many people have access to the NAS.

One case he found a list of AWS EC2 keys and IP addresses next to the ssh keys
which could be used to pivot to the cloud.

The basic steps are to find open access like an NFS share or a kick start file
and search for keys.

IPMI access is a management console and the security on these things is very
basic. Once you have access to the IPMI system you can shut the system down
and log in.

Jenkins servers with no authentication allow hackers to gain access to a
trusted system and use the script console to run commands from inside the
network such as netcat to get a reverse shell

Other things to search for were in github. The `.netrc` directory contains
github credentials. Many github repos contain usernames and passwords for
servers or other services used by the company (mailgun).

## Cracken

The company he worked for was using AWS instances with GPUs to crack hashed
password files. This was expensive and they came up with a better way.
Built 2 physical servers with a beefy power supply and 8 NVIDIA GTX 980
graphics cards. One of these systems can crack passwords 10x faster than the
Amazon GPU systems.

Using these systems they could crack a 7 character password in 8 minutes.
An 8 character password takes hours.

### Web applications need strong password requirements and implementation!

Web applications that use unsalted passwords have hashes that show how many
people are using the same password. He showed some top common passwords after
their company cracked the hash file (123456 and Spring2017 were very common).

### Fix password problems

* Educate Developers
* Passwords on ssh keys
* Use SSH agent forwarding
* Do security testing early
* Use outside people to do security testing because inside the reporting
structure leads to being overridden to make deadlines.

[dave@drstrangelove.net](dave@drstrangelove.net)
