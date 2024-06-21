## Wayland

### Display Driver Models 

Linux has two display driver models the modern Wayland and legacy X11. 

On Fedora with GNOME, Wayland is the default display driver model. On the Fedora LXDE Spin, X11 is the default display driver model.

X11 was designed for a system with a single monitor or two matching monitors and therefore supported only standard scaling across all monitors.

<img src="./images/wayland/img_001.png" alt="img_001" width="600"/>

### WD19TB Docking Station

Nowadays it is common to dock a non-touchscreen monitor with a laptop touchscreen that has a much higher screen resolution:

<img src="./images/wayland/img_002.png" alt="img_002" width="600"/>

In order for these two monitors to work well together, they need to use Wayland with a different screen resolution on each monitor:

<img src="./images/wayland/img_003.png" alt="img_003" width="600"/>

### Fractional Scaling

Fractional Scaling is not enabled by default and only integer values of 100 % scaling are supported for each monitor. If the touchscreen monitor is right clicked and Display Settings are opened:

<img src="./images/wayland/img_004.png" alt="img_004" width="600"/>

It defaults to 100 % which is slightly too small and 200 % which is slightly too big:

<img src="./images/wayland/img_005.png" alt="img_005" width="600"/>

The experimental fractional scaling setting is enabled by default on Ubuntu but not on Fedora. Press `⊞` to view the GNOME Dock, then select `𓃑` and then select Terminal:

<img src="./images/wayland/img_006.png" alt="img_006" width="600"/>

Input the following command:

```bash
gsettings set org.gnome.mutter experimental-features "['scale-monitor-framebuffer']"
```

<img src="./images/wayland/img_007.png" alt="img_007" width="600"/>

Then restart. Once restarted, the Fractional Scaling settings display:

<img src="./images/wayland/img_008.png" alt="img_008" width="600"/>

The monitor and the laptop screen can be seen below:

<img src="./images/wayland/img_009.png" alt="img_009" width="600"/>

The laptop screen is high resolution has 2560x1600 pixels and a default scaling of 200 %:

<img src="./images/wayland/img_010.png" alt="img_010" width="600"/>

<img src="./images/wayland/img_011.png" alt="img_011" width="600"/>

The monitor screen has 1920x1080 pixels and a default scaling of 100 %:

<img src="./images/wayland/img_012.png" alt="img_012" width="600"/>

<img src="./images/wayland/img_013.png" alt="img_013" width="600"/>

With fractional scaling, the laptop screen can be changed to 150 %:

<img src="./images/wayland/img_014.png" alt="img_014" width="600"/>

Once Apply is selected:

<img src="./images/wayland/img_015.png" alt="img_015" width="600"/>

Select Keep Settings can be selected:

<img src="./images/wayland/img_016.png" alt="img_016" width="600"/>

The contents on both monitors can now be read well:

<img src="./images/wayland/img_017.png" alt="img_017" width="600"/>

### Removing Fractional Scaling

If there is any instability with this experimental feature it can be disabled. To turn this feature off, open up a Terminal and input:


```bash
gsettings set org.gnome.mutter experimental-features "[]"
```

[Return to Fedora Installation Guide](./readme.md).

