Command Reference
=======================================

info
----
info command will dump device information. It requires no parameters.

.. code-block:: sh

    esp32>info
    Bluetooth:
      Device Name: MSTP_WCVT

    MSTP:
      Address: 1
      Baud Rate: 38400
      Bacnet Network: 1001

    Ethernet:
      Ethernet mode: DHCP
      Bacnet Network: 1000
      Bacnet IP Port: 47808

    WiFi:
      WiFi mode: OFF
      WiFi SSID:
      Bacnet Network: 2000
      Bacnet IP Port: 47808

    Gateway Priority:
      wifi > ethernet

info command's outputs are in 5 catagories.

Bluetooth: Device Name and Password (Password is hidden)

* Device Name: How device's name, this will be used by bluetooth and mDNS

MSTP: MSTP related settings

* Address: MSTP address

* Baud Rate: baudrate of the RS485, valid values are 9600/19200/38400/76800

* Bacnet Network: Network Id of the MSTP trunk

Ethernet: Ethernet Settings

* Ethernet mode: dhcp/static/off for using dhcp mode/static ip mode/off. If the ethernet currently has an IP address assigned to Ethernet, the IP address will also be printed

* Bacnet Network: Network Id of the Bacnet IP

* Bacnet IP Port: udp port number used for the Bacnet IP

WiFi: WiFi Settings

* WiFi mode: can be sta/ap/off for wifi station/wifi ap/off mode

* WiFi SSID: ssid of WiFi, WiFi password can be set but hidden from info output. If the ethernet currently has an IP address assigned to Ethernet, the IP address will also be printed

* Bacnet Network: Network Id of the Bacnet IP

* Bacnet IP Port: udp port number used for the Bacnet IP

Gateway Priority:

* When ethernet and wifi are both connected, which interface has higher priority to route IP packet to remote network.

bluetooth
---------

.. code-block:: sh

    bluetooth <name> [--pwd=your_password]
      name: is the device name
      --pwd=your_password: pass is optional for you to set the bluetooth pairing password, just replacing your_password with any string you want, the length shall be no shorter than 8 characters

mstp
----

.. code-block:: sh

    mstp [--baud=<n>] [--addr=<n>] [--network=<n>]


netcfg
------

.. code-block:: sh

    netcfg [--wifi=<sta/ap/off>] [--ethernet=<dhcp/static/off>] [--defaultgw=]

wifi_bip
--------

.. code-block:: sh

    wifi_bip <ssid> [<pass>] [--network=<n>] [--port=<n>]

eth_bip
-------

.. code-block:: sh

    eth_bip [--network=<n>] [--port=<n>] [--ip=<addr>] [--gw=<gateway>]

restart
-------
restart is a convenient command for you to use after you change any setting on console to make sure the device reboot to use the new settings
