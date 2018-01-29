# SELinux Policies Syntax Highlighting Definition, for the KSyntaxHighlighting Framework

**Author:** Nibaldo González (<nibgonz@gmail.com>) (Valparaíso, Chile)

**Last Change:** January 2018


## Description:

Add syntax highlighting to KDE text editors (as Kate, KWrite, KDevelop 
or any application that uses the KSyntaxHighlighting Framework) for:

* SELinux CIL Policies (`selinux-cil.xml`).
* SELinux File Labeling Policies (`selinux-fc.xml`).


## About XML Files of Syntax Highlighting Definition:

The syntax highlighting definition files, of the KSyntaxHighlighting Framework, 
consist of XML files that are compiled in the KDE Frameworks libraries.

However, these XML files can also be stored in:

	$HOME/.local/share/org.kde.syntax-highlighting/syntax/
	/usr/share/org.kde.syntax-highlighting/syntax/

For more details of KSyntaxHighlighting Framework, visit:
* Official Repository: https://phabricator.kde.org/source/syntax-highlighting/
* Documentation: https://docs.kde.org/stable5/en/applications/katepart/highlight.html
* Announcement: https://kate-editor.org/2016/11/15/ksyntaxhighlighting-a-new-syntax-highlighting-framework/


## Installation:

Copy the `.xml` files to `$HOME/.local/share/org.kde.syntax-highlighting/syntax/` (for local user) or `/usr/share/org.kde.syntax-highlighting/syntax/` (for all users).

Ex.: 
For local user:
```bash
mkdir -p $HOME/.local/share/org.kde.syntax-highlighting/syntax/
cp ./selinux-*.xml $HOME/.local/share/org.kde.syntax-highlighting/syntax/
```
For all users:
```bash
sudo mkdir -p /usr/share/org.kde.syntax-highlighting/syntax/
sudo cp ./selinux-*.xml /usr/share/org.kde.syntax-highlighting/syntax/
```

## Usage:

Syntax highlighting of SELinux CIL Policies is automatically applied to files with `.cil` extension. 
Syntax highlighting of SELinux File Contexts is automatically applied to files with `.fc` extension 
and the files with name: `file_contexts`, `file_contexts.local`, `file_contexts.homedirs`, `file_contexts.template` & `homedir_template`.

You can also force the syntax highlighting, by writing a comment with: 
```
kate: syntax SELinux CIL Policy
kate: syntax SELinux File Contexts
```