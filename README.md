# QnapLCD-Menu

A simplistic package and examples using the front panel display and buttons
on QNAP NAS devices under other operating systems. Tested with TVS-671,
but should work on other models that use the "A125" display with two buttons.

# What's Included

In most cases you would setup *preinit.py*, *lcd-menu.py*, and *shutdown.py* to get a workable menu on the Qnap LCD.

* *preinit.py* a short pre-initialization script to print a message on the LCD panel and terminate.

* *postinit.py* a short post-initialization script to print a message on the LCD panel and terminate. Not used in most cases.

* *lcd-menu.py* a Python script that will display a menu similar to the default QNAP menu, written for TrueNAS SCALE but may work with other TrueNAS and FreeNAS systems. This should take the place of the *postinit.py* script if you want the menu system active.

* *shutdown* a short shutdown script to print a message on the LCD panel and terminate.

* *qnaplcd* Python package (class) for using the front-panel (A125) display. Uses *pyserial* and threading to send button events to calling program.

# Installation

To install, clone this repository onto your NAS somewhere that is accessible to the admin (root) user. It needs to be run *as root* to communicate with the display and the TrueNAS CLI.

#### First:
- Copy the scripts to your nas via FTP (suggested: /home/admin/QnapLcdMenu).

#### In the TrueNAS Web Ui go to System Settings/Advanced/Init&Shutdown Scripts/Add and create the following:

![Screenshot 2024-06-19 at 4 39 01 PM](https://github.com/alfredoarrieta/Qnap-TS-469-Pro-Lcd-Scale/assets/43350012/0eb03f37-d82a-44dd-9dd9-4a322c60b168)



#### This is a screenshot of how the configuration should look for the Pre Init:

![Screenshot 2024-06-19 at 4 45 24 PM](https://github.com/alfredoarrieta/Qnap-TS-469-Pro-Lcd-Scale/assets/43350012/26a965ba-c31f-4187-bf00-626418d42c9e)



#### This is a screenshot of how the configuration should look for the Post Init:

![Screenshot 2024-06-19 at 4 45 39 PM](https://github.com/alfredoarrieta/Qnap-TS-469-Pro-Lcd-Scale/assets/43350012/6c02ca55-07b0-4733-b436-bcf18282704d)

(this one is different because the script should run in a separate thread so the system wont kill it after the set timeout is done):



#### This is a screenshot of how the configuration should look for the Shutdown:

![Screenshot 2024-06-19 at 4 45 48 PM](https://github.com/alfredoarrieta/Qnap-TS-469-Pro-Lcd-Scale/assets/43350012/2fbb768f-0581-4f82-a677-bd99efb14e3f)
