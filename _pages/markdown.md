---
permalink: /markdown/
title: "Useful"
author_profile: true
redirect_from: 
  - /md/
  - /markdown.html
---

In this page, I save some useful information for instant-access.

My own Ubuntu environment
======
```bash
sudo apt install htop
# FreeCAD
sudo apt update
sudo apt install ubuntu-desktop  
sudo apt-get install -y fuse libfuse2 # required by some apps
sudo apt install snapd
sudo snap install freecad
# Brave
sudo apt install curl
sudo curl -fsSLo /usr/share/keyrings/brave-browser-archive-keyring.gpg https://brave-browser-apt-release.s3.brave.com/brave-browser-archive-keyring.gpg
echo "deb [signed-by=/usr/share/keyrings/brave-browser-archive-keyring.gpg] https://brave-browser-apt-release.s3.brave.com/ stable main"|sudo tee /etc/apt/sources.list.d/brave-browser-release.list
sudo apt install brave-browser
# inkscape
sudo apt-get install -y inkscape
# paraview
sudo apt-get install paraview
# VSCode
sudo apt install code
# Setting up remote pc
sudo apt install -y tigervnc-standalone-server tigervnc-xorg-extension tigervnc-viewer dbus-x11
sudo apt install xfce4 xfce4-goodies tasksel
sudo tasksel
sudo update-alternatives --config x-session-manager
sudo snap install -y onlyoffice-desktopeditors
sudo apt install -y libreoffice
# other softwares
cd $HOME
mkdir Applications
cd Applications
# Arduino IDE
wget https://downloads.arduino.cc/arduino-ide/arduino-ide_2.3.4_Linux_64bit.AppImage
chmod +x arduino-ide_2.3.4_Linux_64bit.AppImage
# Ultimaker slicer for 3D printing
wget https://github.com/Ultimaker/Cura/releases/download/5.9.0/UltiMaker-Cura-5.9.0-linux-X64.AppImage
chmod +x UltiMaker-Cura-5.9.0-linux-X64.AppImage
```

Making a Linux server machine
======

First, we need to install ssh:

```bash
sudo apt install openssh-server -y
sudo systemctl enable ssh
sudo systemctl start ssh
```
then check if it is running
```bash
sudo systemctl status ssh
```
Now we need to allow ssh through firewall:
```bash
sudo ufw allow OpenSSH
sudo ufw enable
sudo ufw status
```

For adding user:

```bash
sudo adduser --disabled-password user1
```
Each commend will ask for user info, press enter for optional fields like phone number, office no etc.

Now we want users to setup their own password:

```bash
sudo chage -d 0 user1
```

Now, go to ssh config file and allow this user for access:

```bash
sudo nano /etc/ssh/sshd_config
```

Then add this line at the bottom:

```bash
AllowUsers user1
```

Then restart ssh to apply changes:

```bash
sudo systemctl restart ssh
```

To get the ip, run in the remote linux pc:

```bash
hostname -I
```
and you will get something like `10.208.15.53`.

Then for connection from other pc:
```bash
ssh user1@10.208.15.53
```

(Optinal) For securing the server: go to 

```bash
sudo nano /etc/ssh/sshd_config
```
and make the following changes:
```bash
PermitRootLogin no
PasswordAuthentication yes
```
then reload SSH:
```bash
sudo systemctl reload ssh
```

The configuration should be complete now.

If password is forgotten, you set the password with on the linux machine with:

```bash
sudo passwd user1
```

and manually set the password again. Then run 

```bash
sudo chage -d 0 user1
```

for user to set their own password in their next login.

vncserver commands
======
To specify the port of vncserver:
```
vncserver :2 
```
To kill the process of vncserver:
```bash
vncserver -kill :2
```
If port is in use;
```bash
lsof -ti:5902 | xargs kill -9
```
Reference link is [here](http://www.chiark.greenend.org.uk/~peterb/remoteaccess/connect-to-linux.html).


SSH tunneling
======
First do;
```bash
ssh-keygen
```
Then, modify config file in .ssh folder using [this](http://www.chiark.greenend.org.uk/~peterb/remoteaccess/config.html) link.

After them you should be able to login just by `ssh computer_name`.

gif generator
======
```bash
ffmpeg -i animation.mp4 -vf "fps=20,scale=960:-1:flags=lanczos" -loop 0 wound_healing.gif -y
```


## File Transfer

From remote to local;
```bash
scp -r destrier:/home/ee331/folder   /home/ekrem/folder
```
From local to remote;
```bash
 scp -r folder destrier:/home/ee331/
```

## Ubuntu terminal commands;
[Saving the terminal output to a file.](https://askubuntu.com/questions/420981/how-do-i-save-terminal-output-to-a-file)

About PhD - Advices;
======
Jack Baker's Advices are [here](https://www.jackwbaker.com/advice.html).

Markdown Cheatsheet
======

## Locations of key files/directories

* Basic config options: _config.yml
* Top navigation bar config: _data/navigation.yml
* Single pages: _pages/
* Collections of pages are .md or .html files in:
  * _publications/
  * _portfolio/
  * _posts/
  * _teaching/
  * _talks/
* Footer: _includes/footer.html
* Static files (like PDFs): /files/
* Profile image (can set in _config.yml): images/profile.png

## Tips and hints

* Name a file ".md" to have it render in markdown, name it ".html" to render in HTML.
* Go to the [commit list](https://github.com/academicpages/academicpages.github.io/commits/master) (on your repo) to find the last version Github built with Jekyll. 
  * Green check: successful build
  * Orange circle: building
  * Red X: error
  * No icon: not built

## Resources
 * [Liquid syntax guide](https://shopify.github.io/liquid/tags/control-flow/)
 * [MathJax Documentation](https://docs.mathjax.org/en/latest/)

## MathJax 

Support for MathJax Version 3.0 is included in the template:

$$
\displaylines{
\nabla \cdot E= \frac{\rho}{\epsilon_0} \\\
\nabla \cdot B=0 \\\
\nabla \times E= -\partial_tB \\\
\nabla \times B  = \mu_0 \left(J + \varepsilon_0 \partial_t E \right)
}
$$

The default delimiters of `$$...$$` and `\\[...\\]` are supported for displayed mathematics, while `\\(...\\)` should be used for in-line mathematics (ex., \\(a^2 + b^2 = c^2\\))

**Note** that since Academic Pages uses Markdown which cases some interference with MathJax and LaTeX for escaping characters and new lines, although [some workarounds exist](https://math.codidact.com/posts/278763/278772#answer-278772).

## Markdown guide

Academic Pages uses [kramdown](https://kramdown.gettalong.org/index.html) for Markdown rendering, which has some differences from other Markdown implementations such as GitHub's. In addition to this guide, please see the [kramdown Syntax page](https://kramdown.gettalong.org/syntax.html) for full documentation.  

### Header three

#### Header four

##### Header five

###### Header six

## Blockquotes

Single line blockquote:

> Quotes are cool.

## Tables

### Table 1

| Entry            | Item   |                                                              |
| --------         | ------ | ------------------------------------------------------------ |
| [John Doe](#)    | 2016   | Description of the item in the list                          |
| [Jane Doe](#)    | 2019   | Description of the item in the list                          |
| [Doe Doe](#)     | 2022   | Description of the item in the list                          |

### Table 2

| Header1 | Header2 | Header3 |
|:--------|:-------:|--------:|
| cell1   | cell2   | cell3   |
| cell4   | ce
ll5   | cell6   |
|-----------------------------|
| cell1   | cell2   | cell3   |
| cell4   | cell5   | cell6   |
|=============================|
| Foot1   | Foot2   | Foot3   |

## Definition Lists

Definition List Title
:   Definition list division.

Startup
:   A startup company or startup is a company or temporary organization designed to search for a repeatable and scalable business model.

#dowork
:   Coined by Rob Dyrdek and his personal body guard Christopher "Big Black" Boykins, "Do Work" works as a self motivator, to motivating your friends.

Do It Live
:   I'll let Bill O'Reilly [explain](https://www.youtube.com/watch?v=O_HyZ5aW76c "We'll Do It Live") this one.

## Unordered Lists (Nested)

  * List item one 
      * List item one 
          * List item one
          * List item two
          * List item three
          * List item four
      * List item two
      * List item three
      * List item four
  * List item two
  * List item three
  * List item four

## Ordered List (Nested)

  1. List item one 
      1. List item one 
          1. List item one
          2. List item two
          3. List item three
          4. List item four
      2. List item two
      3. List item three
      4. List item four
  2. List item two
  3. List item three
  4. List item four

## Buttons

Make any link standout more when applying the `.btn` class.

## Notices

Basic notices or call-outs are supported using the following syntax:

```markdown
**Watch out!** You can also add notices by appending `{: .notice}` to the line following paragraph.
{: .notice}
```

which wil render as:

**Watch out!** You can also add notices by appending `{: .notice}` to the line following paragraph.
{: .notice}

### Footnotes

Footnotes can be useful for clarifying points in the text, or citing information.[^1] Markdown support numeric footnotes, as well as text as long as the values are unique.[^note]

```markdown
This is the regular text.[^1] This is more regular text.[^note]

[^1]: This is the footnote itself.
[^note]: This is another footnote.
```

[^1]: Such as this footnote.
[^note]: When using text for footnotes markers, no spaces are permitted in the name.

## HTML Tags

### Address Tag

<address>
  1 Infinite Loop<br /> Cupertino, CA 95014<br /> United States
</address>

### Anchor Tag (aka. Link)

This is an example of a [link](http://github.com "Github").

### Abbreviation Tag

The abbreviation CSS stands for "Cascading Style Sheets".

*[CSS]: Cascading Style Sheets

### Cite Tag

"Code is poetry." ---<cite>Automattic</cite>

### Code Tag

You will learn later on in these tests that `word-wrap: break-word;` will be your best friend.

You can also write larger blocks of code with syntax highlighting supported for some languages, such as Python:

```python
print('Hello World!')
```

or R:

```R
print("Hello World!", quote = FALSE)
```

### Strike Tag

This tag will let you <strike>strikeout text</strike>.

### Emphasize Tag

The emphasize tag should _italicize_ text.

### Insert Tag

This tag should denote <ins>inserted</ins> text.

### Keyboard Tag

This scarcely known tag emulates <kbd>keyboard text</kbd>, which is usually styled like the `<code>` tag.

### Preformatted Tag

This tag styles large blocks of code.

<pre>
.post-title {
  margin: 0 0 5px;
  font-weight: bold;
  font-size: 38px;
  line-height: 1.2;
  and here's a line of some really, really, really, really long text, just to see how the PRE tag handles it and to find out how it overflows;
}
</pre>

### Quote Tag

<q>Developers, developers, developers&#8230;</q> &#8211;Steve Ballmer

### Strong Tag

This tag shows **bold text**.

### Subscript Tag

Getting our science styling on with H<sub>2</sub>O, which should push the "2" down.

### Superscript Tag

Still sticking with science and Isaac Newton's E = MC<sup>2</sup>, which should lift the 2 up.

### Variable Tag

This allows you to denote <var>variables</var>.

***
**Footnotes**

The footnotes in the page will be returned following this line, return to the section on <a href="#footnotes">Markdown Footnotes</a>.
