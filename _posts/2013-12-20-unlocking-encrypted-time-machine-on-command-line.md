--- 
layout: post 
title: Unlocking Encrypted Time Machine on Command Line
tags: osx, backup, encryption, password, cli
--- 
The auto generated password I chose for locking my encrypted time
machine was not being accepted by the graphical interface when I needed
to unlock it. Knowing that I was typing it in correctly, I decided it
was some special character that the GUI was freaking on. Therefore I
looked for ways to do it on the command line in hopes of this providing
some resolution. It did.

In order to do this I first had to find the volume's UUID. 

```` 
diskutil cs list 
```` 

From the output, the UUID is the massive key on a line that looks like:

 **Logical Volume XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX**

Note that it's not the **Logical Volume Group** or the 
**Physical Volume** or the **Logical Volume Family**. It's simply the 
**Logical Volume**. 

From here you can copy the UUID and run the following command:

```` 
diskutil cs unlockVolume XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX -passphrase myS00P3RHAXT0RPr0ofp@55Word 
````

This should unlock the volume and Time Machine should start running and
backing up again. Notice that if you have some special characters in
your password that you'll need to surround the password with quotes. 
