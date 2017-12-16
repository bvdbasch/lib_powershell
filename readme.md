# LIB POWERSHELL

- **Module Name:** 	LIB POWERSHELL
  - **Description:**VGL POWERSHELL LIBRARY
    - **Purpose:**Library to provide easy implementation of various powershell tasks

This is a pure VGL implementation to call powershell task such as sending emails. It removes the need for third party programs like [BLAT](http://blat.net).

The routines are suitable for both foreground and background operations. This means they can be invoked from either `MODE BACKGROUND` or `MODE INTERACTIVE`.

This library does not have a user interface.

## License
This work is published under the [smile license](http://licence.auth0.nl "SMILE!"). The details are behind the link, but the gist of it is 

> ***Do whatever you want, as long as you do something good (help someone out, smile; just be nice)***

## Attribution	
- *Jingyu Sung* : Original concept of powershell mail 

## Routines
### `PS_SENDMAIL`
Send a email using powershell, *without attachments*. Plain text, body does not support HTML.

**Parameters:**

- from_mail
- to_mail
- subject_line
- mail_body
- smtp_server
- smtp_port
- smtp_user
- smtp_password


### `PS_SENDMAIL_ATTACH`
Send a email using powershell, *with attachments*. Plain text, body does not support HTML.

**Parameters:**

- from_mail
- to_mail
- subject_line
- mail_body
- smtp_server
- smtp_port
- smtp_user
- smtp_password
- attachments

## MANUAL
### Dependencies
> **This lib checks if powershell is installed on the target systems. If Powershell cannot be found the routines will not be executed**

### Installation
Routines in this library are `GLOBAL`. Add and compile this library and call the routines whenever desired.

All routines accept the necessary parameters as values to avoid forcing the programmer to code set names.

## Example

	JOIN LIBRARY lib_powershell

```VGL
ps_sendmail(
	"my@mail.com",
	 "destination@mail.com",
	 "This is the email subject",
	 "This is the email body text",
	 "mail.mymailserver.extension",
	 "25",
	 "my@mail.com",
	 "Totally not my password"
)
```

The above example joins the powershell library, thus making it's routines available and then sends an email using the ps_sendmail routine.