========================
BluetoothChatWithArduino
========================

BluetoothChatWithArduino is a simple chat project that uses the droid2ino Android library to communicating with Arduino board using a Bluetooth connection.

This app is a simple example of what you can do with the droid2ino library.

It allows you to:

* Send messages to the Arduino board, which will respond you with an echo of what you send to it. 

* You can open a Serial Monitor in the Arduino IDE and send messages to the mobile device, and BluetoothChatWithArduino will show them (only with an external bluetooth module by using the Software Serial library. BQ Zum only has one serial communication port, so it can not use this option).
  
If you have any questions you can contact us through the `DIY forum <http://diy.bq.com/forums/forum/forum/>`_  or sending an email to diy@bq.com.



Features
========

* Send and receive messages from Arduino board through a Bluetooth connection

* Use of `Android v7 Support Library  <http://developer.android.com/tools/support-library/features.html#v7>`_

* Learn how to give a different style to the dialog shown when searching for the paired Bluetooth devices and new ones in order to get better integration with your app

* Learn how to use the connect and disconnect bluetooth functions, as when the user press the action bar buttons in this example

* The Arduino code for this chat example is in the Arduino folder

* In order to save device's battery, if the Bluetooth was disabled before using the app, then when going out from the app, it will be disabled again. If it was enabled, it will remain enabled. If the user accepts enabling the Bluetooth (if it was disabled when entered in the app for the first time), the library remember it, so don't ask the user again and enable the Bluetooth directly when the user come back to the app.

* Sample project to show how to use the library


Installation
============

#. BluetoothChatWithArduino depends on droid2ino library. Clone the droid2ino repository::

    git clone https://github.com/bq/droid2ino.git

#. Install the droid2ino library in your local repository::
  
    cd droid2ino/droid2ino
    gradle install


#. Install `Android Studio <https://developer.android.com/sdk/installing/studio.html>`_ and `Gradle <http://www.gradle.org/downloads>`_.

#. If you use a 64 bits Linux, you will need to install ia32-libs-multiarch::

	sudo apt-get update
	sudo apt-get upgrade
	sudo apt-get install ia32-libs-multiarch 


#. In Android Studio go to ``File`` > ``Open`` and select the BluetoothChatWithArduino from the example folder of the cloned repository.

#. Upload the Arduino code to your robot. You can find it in the Arduino folder of this project. Use the code in the ``using_integrated_bluetooth_module_(bqzum)`` folder if your board only has one serial communication port (as in the BQ Zum board) or use the code in ``using_external_bluetooth_module`` folder if you are using an external bluetooth module.



Requirements
============

- `Java JDK <http://www.oracle.com/technetwork/es/java/javase/downloads/jdk7-downloads-1880260.html>`_ 

- `Android Studio <https://developer.android.com/sdk/installing/studio.html>`_ 

- `Maven <http://maven.apache.org/download.cgi>`_.  If you use Ubuntu::
    
    sudo apt-get update
    sudo apt-get install maven

- `Gradle <http://www.gradle.org/downloads>`_ version 3.3
  
- `Arduino IDE <http://arduino.cc/en/Main/Software#.UzBT5HX5Pj4>`_ 

- Arduino board with Bluetooth


Limitations
===========

In order to fix the problem when receiving the messages from the Arduino board of obtaining empty strings or divided strings, the droid2ino library uses escape characters in order to obtaining the entire message well.
 
- Start escape characters: ``&&`` 

- End escape characters : ``%%``

So an example of a message written by the Arduino program would be::

	&&I write from Arduino%%


License
=======

BluetoothChatWithArduino is distributed in terms of GPL license. See http://www.gnu.org/licenses/ for more details.

