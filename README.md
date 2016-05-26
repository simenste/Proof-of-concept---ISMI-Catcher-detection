Notes
=====
A very simple and staticly configured web application to detect IMSI Catchers using measurement reports in a predefined scenario. There may currently be some staticly configured local IP-addresses. The project is currently written for localhost only.

The project is based on a proof-of-conecpt project by RangeNetworks: https://github.com/RangeNetworks/presentations

Requirements
=====
* The proof of concept requires two instances of OpenBTS, one that acts as an IMSI Catcher and one that operates as a valid GSM base station receiving the neighbor measurement reports.
* The IMSI Catcher is configured with an ARFCN of 75 and bsic of 29.
* The valid BTS is configured with a ARFCN of 70 and bsic of 29. 
* The two OpenBTS instances must be configured as neighbors in OpenBTS.
* 

Setup
=====

Enable publishing of API data:

    OpenBTS> devconfig NodeManager.API.PhysicalStatus 0.1

Install Python Tornado:

    $ sudo apt-get install python-pip
    $ sudo pip install tornado

Start a quick webserver:

    $ cd PhysicalStatusAPI

    # Python 2.x:
    $ python -m SimpleHTTPServer 8080

    # Python 3.x:
    $ python -m http.server 8080

Start the ZMQ <-> Websocket bridge:

    $ python ./basic-websocket.py

Open the directory in a browser and choose a visualizer:

    http://your-ip:8080


