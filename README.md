# popos_20.04LTS
settings for popos
Gnome v. 3.36.8


### Mouse Logitech M720 Triathlon - Settings
#### Binding Buttons easy way with "Input Remapper"
  https://github.com/sezanzeb/input-remapper  
  [ref](https://ubuntuhandbook.org/index.php/2021/07/remap-keyboard-gamepad-ubuntu/)
  [examples](https://github.com/sezanzeb/input-remapper/blob/HEAD/readme/examples.md)  

    Settings:   
    ```
    "Button Extra" -> Super_L  
    "Contrl L + Alt L + Tab" -> BTN_MIDDLE  
    ```


#### Binding extra Button to Open "link" in "New Tab"
[ref](https://wiki.ubuntuusers.de/xbindkeys/)
[ref](https://www.reddit.com/r/linuxmint/comments/i9w0mb/logitech_m705_to_m720_thumb_button_solution/)   
("['<Primary><Alt>Tab']"  is the hardcoded command for the extra Button)

1. check dconf for in use ['<Control><Alt>Tab'] Button -> []
2. install xbindkeys
    sudo apt-get install xbindkeys   
    sudo apt-get install xbindkeys-config   
    sudo apt-get install xdotool   
    sudo apt-get install xautomation   
    xbindkeys -d > ~/.xbindkeysrc   
    checking what button is the right one: ```xev | grep -A 2 Button```  
    ~/.xbindkeysrc
      ```
      # Open link in new background tab - m720 thumb button
      "sleep 0.1 && xte 'keydown Control_L' 'mouseclick 1' 'keyup Control_L'"
      Control+Alt+Mod2 + Tab
      
      # Open Window-Overview (super) - m720 thumb button 9
      "sleep 0.01 && xte 'keydown super_L' 'keyup super_L'
      b:9 # Maustaste 9
      ```
3. ```xbindkeys```
      
#### Alternatives 
[ref](https://www.medo64.com/2019/03/configuring-thumb-button-on-m720-under-ubuntu/)   
```gsettings set org.gnome.desktop.wm.keybindings minimize "['<Primary><Alt>Tab']" ```
