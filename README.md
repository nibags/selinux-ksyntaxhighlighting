# SELinux Policies Syntax Highlighting Definition for Kate

![Example of SELinux policies (TE module & CIL policy) syntax highlighting](https://raw.githubusercontent.com/nibags/selinux-ksyntaxhighlighting/master/test/images/selinux-preview.png)

**Author:** Nibaldo González (<nibgonz@gmail.com>)

**Last Change:** September 2018

```
These files are part of the KDE's KSyntaxHighlighting Framework. 
```

## Description:

Add syntax highlighting to KDE text editors (as Kate, KWrite, KDevelop or any application that uses the KSyntaxHighlighting or KTextEditor Framework) for:

* SELinux Kernel Policy Language (`selinux.xml`).
* SELinux CIL Policies (`selinux-cil.xml`).
* SELinux File Contexts (`selinux-fc.xml`).

**Last versions:**
* `selinux.xml`: Version 2 is included in KDE Frameworks 5.51.0+.
* `selinux-cil.xml`: Version 2 is included in KDE Frameworks 5.50.0+.
* `selinux-fc.xml`: Version 3 is included in KDE Frameworks 5.51.0+.

**Old versions:**
* `selinux.xml`: Version 1 is included in KDE Frameworks 5.50.0+
* `selinux-cil.xml`: Version 1 is included in KDE Frameworks 5.44.0+.
* `selinux-fc.xml`: Version 2 is included in KDE Frameworks 5.50.0+ and version 1 in KDE Frameworks 5.44.0+.


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

**Important:** `selinux-cil.xml` & `selinux-fc.xml` depend on `selinux.xml`. To avoid problems, do not install the files separately, but the 3 together.

If you do not have the latest version of KDE Frameworks, you can manually install the latest `.xml` files.

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

Syntax highlighting of SELinux policies (`selinux.xml`) is automatically applied to named files: `*.te`, `*.if`, `*.spt`, `policy.conf`, `access_vectors`, `mls`, `mcs` `mls_macros`, `te_macros` `policy_capabilities` `seapp_contexts` & `port_contexts`.

Syntax highlighting of SELinux file contexts is applied to named files: `*.fc`, `file_contexts`, `file_contexts_*`, `file_contexts.local`, `file_contexts.homedirs`, `file_contexts.template`, `homedir_template`, `property_contexts`, `service_contexts`, `hwservice_contexts`, `initial_sid_contexts`, `genfs_contexts` & `fs_use`.

Syntax highlighting of SELinux CIL policies is applied to files with `.cil` extension.

Not all SELinux configuration & build files are highlighted by default, since some have generic names.

You can also force the syntax highlighting by writing a comment with: 
```
kate: syntax SELinux Policy;
kate: syntax SELinux CIL Policy;
kate: syntax SELinux File Contexts;
```
<!-- kate: syntax Markdown; -->
