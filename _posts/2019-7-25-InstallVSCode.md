---
layout: post
title: Installing VS Code
---
According to a 2019 survey by StackOverflow, VS Code is the most popular development tool.  If you want to jump on the bandwagon and see just why this text editor is so popular, head to [Visual Studio's website](https://code.visualstudio.com/ "Visual Studio's Website") and download the proper installation file (.deb, .rpm, or .tar.gz).

## Not Linux

I don't think that anyone needs help with this: download and run the file!  Install it for yourself, or for the entire system using the user or system installers respectively.  Alternatively, use the .zip to create a portable text editor.  Sorry, Mac users.  Only one file.

## Installing using Snap

Any system that supports snaps can run the following to install VS Code stable:

    sudo snap install code --classic

or for bleeding-edge features, along with the risk of a broken application, try:

    sudo snap install code-insiders --classic

## Installing using .deb

Really, if you can use a snap, it's much simpler.  However, if you don't want to use snaps, use the fllowing commands to install it from a .deb file:

    sudo dpkg -i <file>.deb
    sudo apt-get install -f

For newer distributions, perhaps this works:

    sudo apt install ./<file>.deb

## Installing using .rpm

Run the following commands to install VS Code and receive updates, using `zypper`, `dnf`, and `yum` as examples:

    sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
    sudo sh -c 'echo -e "[code]\nname=Visual Studio Code\nbaseurl=https://packages.microsoft.com/yumrepos/vscode\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/vscode.repo'
    sudo zypper refresh
    sudo zypper install code

OR

    (yum / dnf) check-update
    sudo (yum / dnf) install code

Use your appropriate package manager (yum, dnf, zypper, etc) to update the package cache and install the package.  If you don't want to receive updates, install the package on VS Code's website using your package manager, using `dnf` as an example:

    sudo dnf install <file>.rpm

## Final Remarks

Now that you have VS Code installed, stay tuned for my list of preferred extensions and color themes!
