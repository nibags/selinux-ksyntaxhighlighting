# SELinux Policies Syntax Highlighting Definition for Kate

**Author:** Nibaldo González (<nibgonz@gmail.com>)

**Last Change:** August 2018

```
These files are part of the KDE's KSyntaxHighlighting Framework. 
KDE Frameworks 5.44.0 includes version 1 of "selinux-cil.xml" & "selinux-fc.xml". 
```

## Description:

Add syntax highlighting to KDE text editors (as Kate, KWrite, KDevelop, etc.) for:

* SELinux Policy (`selinux.xml`).
* SELinux CIL Policies (`selinux-cil.xml`).
* SELinux File Contexts (`selinux-fc.xml`).


## About XML Files of Syntax Highlighting Definition:

The syntax highlighting definition files, of the KSyntaxHighlighting Framework, 
consist of XML files that are compiled in the KDE Frameworks libraries.

However, these XML files can also be stored in:

	$HOME/.local/share/org.kde.syntax-highlighting/syntax/
	/usr/share/org.kde.syntax-highlighting/syntax/

For more details of KSyntaxHighlighting Framework, visit:
* Official Repository: https://phabricator.kde.org/source/syntax-highlighting/
* Documentation: https://docs.kde.org/stable5/en/applications/katepart/highlight.html


## Installation:

Copy the `.xml` files to `$HOME/.local/share/org.kde.syntax-highlighting/syntax/` (for local user) or `/usr/share/org.kde.syntax-highlighting/syntax/` (for all users).

Ex.: 
For local user:
```bash
mkdir -p $HOME/.local/share/org.kde.syntax-highlighting/syntax/
cp ./selinux{,-cil,-fc}.xml $HOME/.local/share/org.kde.syntax-highlighting/syntax/
```
For all users:
```bash
sudo mkdir -p /usr/share/org.kde.syntax-highlighting/syntax/
sudo cp ./selinux{,-cil,-fc}.xml /usr/share/org.kde.syntax-highlighting/syntax/
```

## Usage:

You can force the syntax highlighting by writing a comment with: 
```
kate: syntax SELinux Policy
kate: syntax SELinux CIL Policy
kate: syntax SELinux File Contexts
```
