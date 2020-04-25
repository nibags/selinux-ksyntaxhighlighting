# SELinux Policies Syntax Highlighting Definition for Kate (KSyntaxHighlighting Framework)

![Example of SELinux policies (CIL policy & TE module) syntax highlighting](https://raw.githubusercontent.com/nibags/selinux-ksyntaxhighlighting/master/test/images/selinux-preview.png)

**Author:** Nibaldo González (<nibgonz@gmail.com>)

**Last Change:** December 2019

    These files are part of the KDE's KSyntaxHighlighting Framework.


## Description:

Add syntax highlighting to KDE text editors (such as Kate, KWrite, KDevelop or 
any application that uses the KSyntaxHighlighting or KTextEditor Framework) for:

* __SELinux Kernel Policy Language__ (`selinux.xml`).
* __SELinux CIL Policies__ (`selinux-cil.xml`).
* __SELinux File Contexts__ (`selinux-fc.xml`).

**NOTE:** `selinux-cil.xml` and `selinux-fc.xml` depend on `selinux.xml`.

For details on the syntax of SELinux policies, visit:
* SELinux Policy Languages: https://selinuxproject.org/page/PolicyLanguage
* The SELinux Notebook: https://selinuxproject.org/page/Category:Notebook
* CIL Documentation: https://github.com/SELinuxProject/selinux/tree/master/secilc/docs
* SELinux Repository: https://github.com/SELinuxProject/selinux

## About XML Files of Syntax Highlighting Definition:

The syntax highlighting definition files, of the KSyntaxHighlighting Framework, 
consist of XML files that are compiled in the KDE Frameworks libraries.

However, these XML files can also be stored in:

<table>
    <tr>
        <td>For local user</td>
        <td>$HOME/.local/share/org.kde.syntax-highlighting/syntax/</td>
    </tr>
    <tr>
        <td>For all users</td>
        <td>/usr/share/org.kde.syntax-highlighting/syntax/</td>
    </tr>
    <tr>
        <td>For <a href="https://flathub.org/apps/details/org.kde.kate">Kate's Flatpak package</a></td>
        <td>$HOME/.var/app/org.kde.kate/data/org.kde.syntax-highlighting/syntax/</td>
    </tr>
    <tr>
        <td>For <a href="https://snapcraft.io/kate">Kate's Snap package</a></td>
        <td>$HOME/snap/kate/current/.local/share/org.kde.syntax-highlighting/syntax/</td>
    </tr>
    <tr>
        <td>On Windows</a></td>
        <td>%USERPROFILE%\AppData\Local\org.kde.syntax-highlighting\syntax\ </td>
    </tr>
</table>

For more details of KSyntaxHighlighting Framework, visit:
* Official Repository: https://phabricator.kde.org/source/syntax-highlighting/
* Documentation: https://docs.kde.org/trunk5/en/applications/katepart/highlight.html

## Installation:

**Important:** `selinux-cil.xml` & `selinux-fc.xml` depend on `selinux.xml`. 
To avoid problems, do not install the files separately, but the 3 together.

If you do not have the latest version of KDE Frameworks, you can manually install 
the latest `.xml` files.

Copy the `.xml` files to the directory of the XML syntax definition files,
mentioned in the previous section.

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

Syntax highlighting of SELinux policies (`selinux.xml`) is automatically applied to 
named files: `*.te`, `*.if`, `*.spt`, `policy.conf`, `access_vectors`, `mls`, `mcs`, 
`mls_macros`, `te_macros`, `policy_capabilities`, `seapp_contexts` & `port_contexts`.

Syntax highlighting of SELinux file contexts is applied to named files: `*.fc`, 
`file_contexts`, `file_contexts_*`, `file_contexts.local`, `file_contexts.homedirs`, 
`file_contexts.template`, `homedir_template`, `property_contexts`, `service_contexts`, 
`hwservice_contexts`, `initial_sid_contexts`, `genfs_contexts` & `fs_use`.

Syntax highlighting of SELinux CIL policies is applied to files with `.cil` extension.

You can also force the syntax highlighting by writing a comment with:

    kate: syntax SELinux Policy;
    kate: syntax SELinux CIL Policy;
    kate: syntax SELinux File Contexts;

## List of Versions:

<table>
    <tr>
        <th width="110px">selinux.xml<br>Version</th>
        <th width="150px">selinux-fc.xml<br>Version</th>
        <th width="90px">Date</th>
        <th>KDE<br>Frameworks</th>
        <th>SELinux<br>Support<br>(checkpolicy)</th>
        <th>Relevant Changes</th>
    </tr>
    <tr>
        <td>3</td>
        <td>-</td>
        <td>Dec. 10, 2019</td>
        <td>5.66.0</td>
        <td>3.0</td>
        <td><ul>
            <li>Add "glblub" keyword (default_range).</li>
            <li>Update permissions list.</li>
        </ul></td>
    </tr>
    <tr>
        <td>-</td>
        <td>4</td>
        <td>Apr. 02, 2019</td>
        <td>5.57.0</td>
        <td>2.8 / 2.9</td>
        <td>No changes, only one indentation is removed.</td>
    </tr>
    <tr>
        <td>2</td>
        <td>3</td>
        <td>Sep. 09, 2018</td>
        <td>5.51.0</td>
        <td>2.8</td>
        <td>Update itemData's style for the new Solarized color schemes of Kate.</td>
    </tr>
    <tr>
        <td>1</td>
        <td>2</td>
        <td>Aug. 28, 2018</td>
        <td>5.50.0</td>
        <td>2.8</th>
        <td>Implement "selinux.xml": some rules and keywords of "selinux-fc.xml" are moved there.</td>
    </tr>
    <tr>
        <td>-</td>
        <td>1</td>
        <td>Jan. 26, 2018</td>
        <td>5.44.0</td>
        <td>-</td>
        <td></td>
    </tr>
</table>

<table>
    <tr>
        <th width="150px">selinux-cil.xml<br>Version</th>
        <th>Date</th>
        <th>KDE<br>Frameworks</th>
        <th>SELinux<br>Support<br>(secilc)</th>
        <th>Relevant Changes</th>
    </tr>
    <tr>
        <td>5</td>
        <td>Dec. 10, 2019</td>
        <td>5.66.0</td>
        <td>3.0</td>
        <td>Add "glblub" keyword (defaultrange).</td>
    </tr>
    <tr>
        <td>3</td>
        <td>Apr. 02, 2019</td>
        <td>5.57.0</td>
        <td>2.8 / 2.9</td>
        <td>No changes, only one indentation is removed.</td>
    </tr>
    <tr>
        <td>2</td>
        <td>Aug. 28, 2018</td>
        <td>5.50.0</td>
        <td>2.8</td>
        <td><ul>
            <li>Add keywords of Android and BPF permissions.</li>
            <li>Implement "selinux.xml": some rules and keywords of "selinux-cil.xml" are moved there.</li>
        </ul></td>
    </tr>
    <tr>
        <td>1</td>
        <td>Jan. 26, 2018</td>
        <td>5.44.0</td>
        <td>2.7</td>
        <td></td>
    </tr>
</table>

<!-- kate: syntax Markdown; -->
