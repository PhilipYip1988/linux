## GNOME Desktop Environment

Fedora has a Vanilla GNOME Desktop Environment which behaves slightly different to Microsoft Windows and is optimised for screen space. The GNOME Dock is hidden by default.

Press `⊞` to view the GNOME Dock. This will take the application out of focus. All applications will be re-tiled so the open application of interest can be selected. The dock has the all applications button which is similar to the Windows start screen.

<img src="./images/vanilla_gnome/img_001.png" alt="img_001" width="800"/>

An application such as Nautilus file explorer can be opened from the dock:

<img src="./images/vanilla_gnome/img_002.png" alt="img_002" width="800"/>

Nautilus opens in Home by default:

<img src="./images/vanilla_gnome/img_003.png" alt="img_003" width="800"/>

The Documents folder can be selected:

<img src="./images/vanilla_gnome/img_004.png" alt="img_004" width="800"/>

There is now a single application open. When `⊞` is pressed, this single application displays:

<img src="./images/vanilla_gnome/img_005.png" alt="img_005" width="800"/>

The `𓃑` button on the dock can be used to select all applications:

<img src="./images/vanilla_gnome/img_006.png" alt="img_006" width="800"/>

In this case, the Terminal will be launched:

<img src="./images/vanilla_gnome/img_007.png" alt="img_007" width="800"/>

Notice the prompt has the form:

```
username@pcname:location$
```

In this case the location is `~` meaning Home:

<img src="./images/vanilla_gnome/img_008.png" alt="img_008" width="800"/>

If the Documents folder is selected and right clicked (2 finger press on a touchpad), Open in Terminal can be selected:

<img src="./images/vanilla_gnome/img_009.png" alt="img_009" width="800"/>

Notice the location is now `~/Documents` where `/` is the default directory separator on Linux:

<img src="./images/vanilla_gnome/img_010.png" alt="img_010" width="800"/>

The binary `cd` can be used to change the directory. The directory to be changed to is then supplied as a command line argument. This has the general form:

```bash
binary command_arg
```

In this case:

```bash
cd ~
```

Notice the location is now `~` as expected:

<img src="./images/vanilla_gnome/img_011.png" alt="img_011" width="800"/>



Changing back to Documents, recall the binary is `cd` and the command line argument is `~/Documents`

```bash
cd ~/Documents
```

The binary `nano` is a terminal based text editor and will open in the location specified in the Terminal, in this case `~/Documents`. If supplied with a file name, expressed as a command line argument it will open the file if it exists, or create a new file with that file name when saved:  

```bash
nano script.py
```

<img src="./images/vanilla_gnome/img_012.png" alt="img_012" width="800"/>

Python code can be added to this `script.py` file. For example:

```python
print('Hello World!')
```

`Ctrl` + `x` can be pressed to exit nano:

<img src="./images/vanilla_gnome/img_013.png" alt="img_013" width="800"/>

To save select `y`:

<img src="./images/vanilla_gnome/img_014.png" alt="img_014" width="800"/>

Press `↲` to save using the file name previously specified `script.py`:

<img src="./images/vanilla_gnome/img_015.png" alt="img_015" width="800"/>

Notice this file is now created and displays in files:

<img src="./images/vanilla_gnome/img_016.png" alt="img_016" width="800"/>

It can be viewed in text editor:

<img src="./images/vanilla_gnome/img_017.png" alt="img_017" width="800"/>

The binary `python` can be launched, supplying `script.py` as a command line argument:

```bash
python script.py
```

<img src="./images/vanilla_gnome/img_018.png" alt="img_018" width="800"/>

The binary `python` will open, execute all the code in the file and then exit:

<img src="./images/vanilla_gnome/img_019.png" alt="img_019" width="800"/>

Now multiple applications are open. Press `⊞` to view the GNOME Dock. This will take all applications out of focus. An application can be selected to be put on top:

<img src="./images/vanilla_gnome/img_020.png" alt="img_020" width="800"/>

<img src="./images/vanilla_gnome/img_021.png" alt="img_021" width="800"/>

If `⊞` is selected a search for the Gparted application can be made:

<img src="./images/vanilla_gnome/img_022.png" alt="img_022" width="800"/>

It is not installed, so a suggestion is made from software:

<img src="./images/vanilla_gnome/img_023.png" alt="img_023" width="800"/>

It can be installed:

<img src="./images/vanilla_gnome/img_024.png" alt="img_024" width="800"/>

It can be launched:

<img src="./images/vanilla_gnome/img_025.png" alt="img_025" width="800"/>

Gparted is a partition editor which requires root access and needs to be run as a super user. To run the application as a super user, an authentication prompt shows. To authenticate, the user password needs to be input:

<img src="./images/vanilla_gnome/img_026.png" alt="img_026" width="800"/>

Gparted now launches:

<img src="./images/vanilla_gnome/img_027.png" alt="img_027" width="800"/>

This is equivalent to run as administrator on Windows and is equivalent to a User Account Control Prompt which was seen for example when Rufus was launched:

<img src="./images/vanilla_gnome/img_028.png" alt="img_028" width="300"/>

Vanilla GNOME has no minimise and maximise button. Application window snapping can be carried out using: 

* `⊞` + `←` - left half
* `⊞` + `→` - right half 
* `⊞` + `↑` - full screen maximised

The title bar can also be right clicked (2 finger press for a touchpad) for other options:

<img src="./images/vanilla_gnome/img_029.png" alt="img_029" width="800"/>

If this Application is Hidden:

<img src="./images/vanilla_gnome/img_030.png" alt="img_030" width="800"/>

It can be viewed by pressing `⊞` where all open apps will be tiled:

<img src="./images/vanilla_gnome/img_031.png" alt="img_031" width="800"/>

If a binary is prefixed with `sudo` it is an instruction to run the binary as a super user instead of a user. This gives it access to root and other privileges:

```bash
sudo binary command_arg
```

For example, `nano` can be run as a super user using:

```bash
sudo nano script.py
```

<img src="./images/vanilla_gnome/img_032.png" alt="img_032" width="800"/>

This script file now exists, so is opened:

<img src="./images/vanilla_gnome/img_033.png" alt="img_033" width="800"/>

The Python code can now be updated to print out the command line arguments:

```python
import sys
arguments = sys.argv
print(arguments)
```

It can be saved as before:

<img src="./images/vanilla_gnome/img_034.png" alt="img_034" width="800"/>

The file can be reloaded in the text editor:

<img src="./images/vanilla_gnome/img_035.png" alt="img_035" width="800"/>

Now the binary `python` can be used and supplied a script file as a command line argument, alongside some other optional command line arguments:

```bash
python script.py arg1 arg2 arg3 anystring
```

Notice the first command line argument is `script.py`, the second is `arg1`, the third is `arg2`, the fourth is `arg3` and so on. Notice each of these are returned in quotations denoting that the command line arguments are always recognised as a string.

The default programming language for the Linux Terminal is `bash` and this prefers double quotations for strings, Python on the other hand is a different programming language which prefers single quotations for strings. The above command could therefore also be written as:

```bash
python "script.py" "arg1" "arg2" "arg3" "anystring"
```

Generally the double quotations are only used around a command line argument string when it contains a space, because otherwise the space is an instruct to move onto the next command line argument:

<img src="./images/vanilla_gnome/img_036.png" alt="img_036" width="800"/>

If other locations are selected in Nautilus File Explorer, the root drive can be accessed:

<img src="./images/vanilla_gnome/img_037.png" alt="img_037" width="800"/>

Any folder on the root drive, except the users home folder cannot be modified as a standard user and requires super user access. If the `bin` folder is examined:

<img src="./images/vanilla_gnome/img_038.png" alt="img_038" width="800"/>

Notice that it contains the binaries previously input into the Terminal, for example `nano`:

<img src="./images/vanilla_gnome/img_039.png" alt="img_039" width="800"/>

And `python`. Note that this is the operating system Python and contains only Python and the standard libraries. The system Python should be regarded as part of the Operating System and is updated as part of the Operating System.

For Python development, a user Python should be installed in the users home folder for example by using Miniconda or Anaconda. This allows the user to create a user conda Python environment were they can specify their Python version and third-party libraries without breaking the Operating System:

<img src="./images/vanilla_gnome/img_040.png" alt="img_040" width="800"/>

The binary `bash` is the default programming language used by the Linux Terminal:

<img src="./images/vanilla_gnome/img_041.png" alt="img_041" width="800"/>

The binary `dnf` is Fedora's package manager:

<img src="./images/vanilla_gnome/img_042.png" alt="img_042" width="800"/>

The home folder can be accessed from the root drive:

<img src="./images/vanilla_gnome/img_043.png" alt="img_043" width="800"/>

A standard user can only access the subfolder corresponding to their own username by default i.e. this subfolder is home for the standard user:

<img src="./images/vanilla_gnome/img_044.png" alt="img_044" width="800"/>

And is the location when Home is selected on Nautilus or Nautilus is opened by that user:

<img src="./images/vanilla_gnome/img_045.png" alt="img_045" width="800"/>

The binary `man` can be used to view the manual for a binary name supplied as a command line argument. For example the manual for the package manager can be viewed by inputting:

```bash
man dnf
```

<img src="./images/vanilla_gnome/img_046.png" alt="img_046" width="800"/>

This can be scrolled through using the Terminal. To quit scrolling press `q`:

<img src="./images/vanilla_gnome/img_047.png" alt="img_047" width="800"/>

This returns back to the Terminal:

<img src="./images/vanilla_gnome/img_048.png" alt="img_048" width="800"/>

[Return to Fedora Installation Guide](./readme.md).
