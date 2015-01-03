---
title: "Usage"
bg: orange  #defined in _config.yml, can use html color like '#0fbfcf'
color: black   #text color
fa-icon: rocket
---

## Installation & Usage

First, install Node.js if you haven't already.

Once node is installed, open up a command line and run

```sh
npm install sqlpad -g
```

This will install the SqlPad command line utility to run a SqlPad server. 

To run a SqlPad Server, type the following from the command line:

```sh
sqlpad
```

To get help:

```sh
sqlpad --help
```

## Once SqlPad is Running

Once SqlPad is running, you create an initial admin account by navigationg to http://localhost/signup. Once an initial admin account has been created, all future users must be whitelisted by an admin within the users page.

If for whatever reason you lose admin rights, and the last-admin-standing won't give you admin rights back, you can reinstate them to yourself by running

```sh
sqlpad --admin yourEmailAddress@domain.com
```


## A Realistic Example:  

```sh
sqlpad --dir c:/sqlpad/ --port 3000 --passphrase secret-encryption-phrase
```

The **dir** argument specifies where to keep the sqlpad query/user/connection files. If not provided, SqlPad will put its files in the user's home directory under /sqlpad/db.

The **port** argument specifies the port on which SqlPad should run. The default is port 80, but that may not be available.

The **passphrase** argument is used to encrypt database connection usernames and passwords, and cookie encryption. If not provided, SqlPad will use the default to at least prevent usernames and passwords from being stored in plaintext. 

If a passphrase is ever changed or forgotten, you'll need to re-add the connection usernames and passwords to each database connection. 

If you ever want to save the arguments you are passing in so you don't have to keep typing them over and over, you can save them by passing in the ```--save``` argument.

```sh
sqlpad --dir ./sqlpad/ --port 3000 --passphrase secret-encryption-phrase --save
```

Then the next time you can simply run...

```sh
sqlpad
``` 

...and Sqlpad will use directory ./sqlpad, on port 3000, with the proper encryption passphrase.

These settings can be forgotten by running 

```sh
sqlpad --forget
```