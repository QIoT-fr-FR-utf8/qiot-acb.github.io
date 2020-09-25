# QIoT Sensor

* TOC
{:toc}

## Implementation

### The coding side ![codeside](img/jedi-master.png) *(not the dark side ;) ![dark-side](img/darkside.png) )*

[![](https://mermaid.ink/img/eyJjb2RlIjoiZ3JhcGggTFI7XG5hcHAucHkgLS1yZXRyaWV2ZS0tPiBnYXNfZXh0ZW5kc1xuYXBwLnB5IC0tcmV0cmlldmUtLT4gcGFydGljdWxlc19leHRlbmRzXG5hcHAucHkgLS1yZXRyaWV2ZS0tPiB3ZWF0aGVyX2V4dGVuZHNcblF1YXJrdXMgLS1jb25zdW1lLS0-IGFwcC5weVxuUHJvbWV0aGV1cyogLS1jb25zdW1lLS0-IGFwcC5weSIsIm1lcm1haWQiOnsidGhlbWUiOiJkZWZhdWx0IiwidGhlbWVWYXJpYWJsZXMiOnsiYmFja2dyb3VuZCI6IndoaXRlIiwicHJpbWFyeUNvbG9yIjoiI0VDRUNGRiIsInNlY29uZGFyeUNvbG9yIjoiI2ZmZmZkZSIsInRlcnRpYXJ5Q29sb3IiOiJoc2woODAsIDEwMCUsIDk2LjI3NDUwOTgwMzklKSIsInByaW1hcnlCb3JkZXJDb2xvciI6ImhzbCgyNDAsIDYwJSwgODYuMjc0NTA5ODAzOSUpIiwic2Vjb25kYXJ5Qm9yZGVyQ29sb3IiOiJoc2woNjAsIDYwJSwgODMuNTI5NDExNzY0NyUpIiwidGVydGlhcnlCb3JkZXJDb2xvciI6ImhzbCg4MCwgNjAlLCA4Ni4yNzQ1MDk4MDM5JSkiLCJwcmltYXJ5VGV4dENvbG9yIjoiIzEzMTMwMCIsInNlY29uZGFyeVRleHRDb2xvciI6IiMwMDAwMjEiLCJ0ZXJ0aWFyeVRleHRDb2xvciI6InJnYig5LjUwMDAwMDAwMDEsIDkuNTAwMDAwMDAwMSwgOS41MDAwMDAwMDAxKSIsImxpbmVDb2xvciI6IiMzMzMzMzMiLCJ0ZXh0Q29sb3IiOiIjMzMzIiwibWFpbkJrZyI6IiNFQ0VDRkYiLCJzZWNvbmRCa2ciOiIjZmZmZmRlIiwiYm9yZGVyMSI6IiM5MzcwREIiLCJib3JkZXIyIjoiI2FhYWEzMyIsImFycm93aGVhZENvbG9yIjoiIzMzMzMzMyIsImZvbnRGYW1pbHkiOiJcInRyZWJ1Y2hldCBtc1wiLCB2ZXJkYW5hLCBhcmlhbCIsImZvbnRTaXplIjoiMTZweCIsImxhYmVsQmFja2dyb3VuZCI6IiNlOGU4ZTgiLCJub2RlQmtnIjoiI0VDRUNGRiIsIm5vZGVCb3JkZXIiOiIjOTM3MERCIiwiY2x1c3RlckJrZyI6IiNmZmZmZGUiLCJjbHVzdGVyQm9yZGVyIjoiI2FhYWEzMyIsImRlZmF1bHRMaW5rQ29sb3IiOiIjMzMzMzMzIiwidGl0bGVDb2xvciI6IiMzMzMiLCJlZGdlTGFiZWxCYWNrZ3JvdW5kIjoiI2U4ZThlOCIsImFjdG9yQm9yZGVyIjoiaHNsKDI1OS42MjYxNjgyMjQzLCA1OS43NzY1MzYzMTI4JSwgODcuOTAxOTYwNzg0MyUpIiwiYWN0b3JCa2ciOiIjRUNFQ0ZGIiwiYWN0b3JUZXh0Q29sb3IiOiJibGFjayIsImFjdG9yTGluZUNvbG9yIjoiZ3JleSIsInNpZ25hbENvbG9yIjoiIzMzMyIsInNpZ25hbFRleHRDb2xvciI6IiMzMzMiLCJsYWJlbEJveEJrZ0NvbG9yIjoiI0VDRUNGRiIsImxhYmVsQm94Qm9yZGVyQ29sb3IiOiJoc2woMjU5LjYyNjE2ODIyNDMsIDU5Ljc3NjUzNjMxMjglLCA4Ny45MDE5NjA3ODQzJSkiLCJsYWJlbFRleHRDb2xvciI6ImJsYWNrIiwibG9vcFRleHRDb2xvciI6ImJsYWNrIiwibm90ZUJvcmRlckNvbG9yIjoiI2FhYWEzMyIsIm5vdGVCa2dDb2xvciI6IiNmZmY1YWQiLCJub3RlVGV4dENvbG9yIjoiYmxhY2siLCJhY3RpdmF0aW9uQm9yZGVyQ29sb3IiOiIjNjY2IiwiYWN0aXZhdGlvbkJrZ0NvbG9yIjoiI2Y0ZjRmNCIsInNlcXVlbmNlTnVtYmVyQ29sb3IiOiJ3aGl0ZSIsInNlY3Rpb25Ca2dDb2xvciI6InJnYmEoMTAyLCAxMDIsIDI1NSwgMC40OSkiLCJhbHRTZWN0aW9uQmtnQ29sb3IiOiJ3aGl0ZSIsInNlY3Rpb25Ca2dDb2xvcjIiOiIjZmZmNDAwIiwidGFza0JvcmRlckNvbG9yIjoiIzUzNGZiYyIsInRhc2tCa2dDb2xvciI6IiM4YTkwZGQiLCJ0YXNrVGV4dExpZ2h0Q29sb3IiOiJ3aGl0ZSIsInRhc2tUZXh0Q29sb3IiOiJ3aGl0ZSIsInRhc2tUZXh0RGFya0NvbG9yIjoiYmxhY2siLCJ0YXNrVGV4dE91dHNpZGVDb2xvciI6ImJsYWNrIiwidGFza1RleHRDbGlja2FibGVDb2xvciI6IiMwMDMxNjMiLCJhY3RpdmVUYXNrQm9yZGVyQ29sb3IiOiIjNTM0ZmJjIiwiYWN0aXZlVGFza0JrZ0NvbG9yIjoiI2JmYzdmZiIsImdyaWRDb2xvciI6ImxpZ2h0Z3JleSIsImRvbmVUYXNrQmtnQ29sb3IiOiJsaWdodGdyZXkiLCJkb25lVGFza0JvcmRlckNvbG9yIjoiZ3JleSIsImNyaXRCb3JkZXJDb2xvciI6IiNmZjg4ODgiLCJjcml0QmtnQ29sb3IiOiJyZWQiLCJ0b2RheUxpbmVDb2xvciI6InJlZCIsImxhYmVsQ29sb3IiOiJibGFjayIsImVycm9yQmtnQ29sb3IiOiIjNTUyMjIyIiwiZXJyb3JUZXh0Q29sb3IiOiIjNTUyMjIyIiwiY2xhc3NUZXh0IjoiIzEzMTMwMCIsImZpbGxUeXBlMCI6IiNFQ0VDRkYiLCJmaWxsVHlwZTEiOiIjZmZmZmRlIiwiZmlsbFR5cGUyIjoiaHNsKDMwNCwgMTAwJSwgOTYuMjc0NTA5ODAzOSUpIiwiZmlsbFR5cGUzIjoiaHNsKDEyNCwgMTAwJSwgOTMuNTI5NDExNzY0NyUpIiwiZmlsbFR5cGU0IjoiaHNsKDE3NiwgMTAwJSwgOTYuMjc0NTA5ODAzOSUpIiwiZmlsbFR5cGU1IjoiaHNsKC00LCAxMDAlLCA5My41Mjk0MTE3NjQ3JSkiLCJmaWxsVHlwZTYiOiJoc2woOCwgMTAwJSwgOTYuMjc0NTA5ODAzOSUpIiwiZmlsbFR5cGU3IjoiaHNsKDE4OCwgMTAwJSwgOTMuNTI5NDExNzY0NyUpIn19LCJ1cGRhdGVFZGl0b3IiOmZhbHNlfQ)](https://mermaid-js.github.io/mermaid-live-editor/#/edit/eyJjb2RlIjoiZ3JhcGggTFI7XG5hcHAucHkgLS1yZXRyaWV2ZS0tPiBnYXNfZXh0ZW5kc1xuYXBwLnB5IC0tcmV0cmlldmUtLT4gcGFydGljdWxlc19leHRlbmRzXG5hcHAucHkgLS1yZXRyaWV2ZS0tPiB3ZWF0aGVyX2V4dGVuZHNcblF1YXJrdXMgLS1jb25zdW1lLS0-IGFwcC5weVxuUHJvbWV0aGV1cyogLS1jb25zdW1lLS0-IGFwcC5weSIsIm1lcm1haWQiOnsidGhlbWUiOiJkZWZhdWx0IiwidGhlbWVWYXJpYWJsZXMiOnsiYmFja2dyb3VuZCI6IndoaXRlIiwicHJpbWFyeUNvbG9yIjoiI0VDRUNGRiIsInNlY29uZGFyeUNvbG9yIjoiI2ZmZmZkZSIsInRlcnRpYXJ5Q29sb3IiOiJoc2woODAsIDEwMCUsIDk2LjI3NDUwOTgwMzklKSIsInByaW1hcnlCb3JkZXJDb2xvciI6ImhzbCgyNDAsIDYwJSwgODYuMjc0NTA5ODAzOSUpIiwic2Vjb25kYXJ5Qm9yZGVyQ29sb3IiOiJoc2woNjAsIDYwJSwgODMuNTI5NDExNzY0NyUpIiwidGVydGlhcnlCb3JkZXJDb2xvciI6ImhzbCg4MCwgNjAlLCA4Ni4yNzQ1MDk4MDM5JSkiLCJwcmltYXJ5VGV4dENvbG9yIjoiIzEzMTMwMCIsInNlY29uZGFyeVRleHRDb2xvciI6IiMwMDAwMjEiLCJ0ZXJ0aWFyeVRleHRDb2xvciI6InJnYig5LjUwMDAwMDAwMDEsIDkuNTAwMDAwMDAwMSwgOS41MDAwMDAwMDAxKSIsImxpbmVDb2xvciI6IiMzMzMzMzMiLCJ0ZXh0Q29sb3IiOiIjMzMzIiwibWFpbkJrZyI6IiNFQ0VDRkYiLCJzZWNvbmRCa2ciOiIjZmZmZmRlIiwiYm9yZGVyMSI6IiM5MzcwREIiLCJib3JkZXIyIjoiI2FhYWEzMyIsImFycm93aGVhZENvbG9yIjoiIzMzMzMzMyIsImZvbnRGYW1pbHkiOiJcInRyZWJ1Y2hldCBtc1wiLCB2ZXJkYW5hLCBhcmlhbCIsImZvbnRTaXplIjoiMTZweCIsImxhYmVsQmFja2dyb3VuZCI6IiNlOGU4ZTgiLCJub2RlQmtnIjoiI0VDRUNGRiIsIm5vZGVCb3JkZXIiOiIjOTM3MERCIiwiY2x1c3RlckJrZyI6IiNmZmZmZGUiLCJjbHVzdGVyQm9yZGVyIjoiI2FhYWEzMyIsImRlZmF1bHRMaW5rQ29sb3IiOiIjMzMzMzMzIiwidGl0bGVDb2xvciI6IiMzMzMiLCJlZGdlTGFiZWxCYWNrZ3JvdW5kIjoiI2U4ZThlOCIsImFjdG9yQm9yZGVyIjoiaHNsKDI1OS42MjYxNjgyMjQzLCA1OS43NzY1MzYzMTI4JSwgODcuOTAxOTYwNzg0MyUpIiwiYWN0b3JCa2ciOiIjRUNFQ0ZGIiwiYWN0b3JUZXh0Q29sb3IiOiJibGFjayIsImFjdG9yTGluZUNvbG9yIjoiZ3JleSIsInNpZ25hbENvbG9yIjoiIzMzMyIsInNpZ25hbFRleHRDb2xvciI6IiMzMzMiLCJsYWJlbEJveEJrZ0NvbG9yIjoiI0VDRUNGRiIsImxhYmVsQm94Qm9yZGVyQ29sb3IiOiJoc2woMjU5LjYyNjE2ODIyNDMsIDU5Ljc3NjUzNjMxMjglLCA4Ny45MDE5NjA3ODQzJSkiLCJsYWJlbFRleHRDb2xvciI6ImJsYWNrIiwibG9vcFRleHRDb2xvciI6ImJsYWNrIiwibm90ZUJvcmRlckNvbG9yIjoiI2FhYWEzMyIsIm5vdGVCa2dDb2xvciI6IiNmZmY1YWQiLCJub3RlVGV4dENvbG9yIjoiYmxhY2siLCJhY3RpdmF0aW9uQm9yZGVyQ29sb3IiOiIjNjY2IiwiYWN0aXZhdGlvbkJrZ0NvbG9yIjoiI2Y0ZjRmNCIsInNlcXVlbmNlTnVtYmVyQ29sb3IiOiJ3aGl0ZSIsInNlY3Rpb25Ca2dDb2xvciI6InJnYmEoMTAyLCAxMDIsIDI1NSwgMC40OSkiLCJhbHRTZWN0aW9uQmtnQ29sb3IiOiJ3aGl0ZSIsInNlY3Rpb25Ca2dDb2xvcjIiOiIjZmZmNDAwIiwidGFza0JvcmRlckNvbG9yIjoiIzUzNGZiYyIsInRhc2tCa2dDb2xvciI6IiM4YTkwZGQiLCJ0YXNrVGV4dExpZ2h0Q29sb3IiOiJ3aGl0ZSIsInRhc2tUZXh0Q29sb3IiOiJ3aGl0ZSIsInRhc2tUZXh0RGFya0NvbG9yIjoiYmxhY2siLCJ0YXNrVGV4dE91dHNpZGVDb2xvciI6ImJsYWNrIiwidGFza1RleHRDbGlja2FibGVDb2xvciI6IiMwMDMxNjMiLCJhY3RpdmVUYXNrQm9yZGVyQ29sb3IiOiIjNTM0ZmJjIiwiYWN0aXZlVGFza0JrZ0NvbG9yIjoiI2JmYzdmZiIsImdyaWRDb2xvciI6ImxpZ2h0Z3JleSIsImRvbmVUYXNrQmtnQ29sb3IiOiJsaWdodGdyZXkiLCJkb25lVGFza0JvcmRlckNvbG9yIjoiZ3JleSIsImNyaXRCb3JkZXJDb2xvciI6IiNmZjg4ODgiLCJjcml0QmtnQ29sb3IiOiJyZWQiLCJ0b2RheUxpbmVDb2xvciI6InJlZCIsImxhYmVsQ29sb3IiOiJibGFjayIsImVycm9yQmtnQ29sb3IiOiIjNTUyMjIyIiwiZXJyb3JUZXh0Q29sb3IiOiIjNTUyMjIyIiwiY2xhc3NUZXh0IjoiIzEzMTMwMCIsImZpbGxUeXBlMCI6IiNFQ0VDRkYiLCJmaWxsVHlwZTEiOiIjZmZmZmRlIiwiZmlsbFR5cGUyIjoiaHNsKDMwNCwgMTAwJSwgOTYuMjc0NTA5ODAzOSUpIiwiZmlsbFR5cGUzIjoiaHNsKDEyNCwgMTAwJSwgOTMuNTI5NDExNzY0NyUpIiwiZmlsbFR5cGU0IjoiaHNsKDE3NiwgMTAwJSwgOTYuMjc0NTA5ODAzOSUpIiwiZmlsbFR5cGU1IjoiaHNsKC00LCAxMDAlLCA5My41Mjk0MTE3NjQ3JSkiLCJmaWxsVHlwZTYiOiJoc2woOCwgMTAwJSwgOTYuMjc0NTA5ODAzOSUpIiwiZmlsbFR5cGU3IjoiaHNsKDE4OCwgMTAwJSwgOTMuNTI5NDExNzY0NyUpIn19LCJ1cGRhdGVFZGl0b3IiOmZhbHNlfQ)

The python application is composed of two main part :  
   + The retrievers : Metrics extended class  
   + The API exposer : Flask application with swagger explaination


#### Retrievers

There are three retrievers :
   - gas_extend.py
   - weather_extend.py
   - particules_extend.py

Example with gas_extend.py:

```python
# gas_extend.py
from time import gmtime, strftime
from enviroplus import gas

#prom side
from prometheus_client import Gauge
from metrics import PROM_GAS_METRICS

def r_float_value_adc():
    if isinstance(gas.readall().adc, float):
        return gas.read_all().adc
    else:
        return 0


def r_float_value_nh3():
    if isinstance(gas.readall().nh3, float):
        PROM_GAS_METRICS['gauge']['nh3'].set(gas.read_all().nh3)
        return gas.read_all().nh3
    else:
        return 0


def r_float_value_oxidising():
    if isinstance(gas.readall().oxidising, float):
        PROM_GAS_METRICS['gauge']['oxidising'].set(gas.read_all().oxidising)
        return gas.read_all().oxidising
    else:
        return 0


def r_float_value_reducing():
    if isinstance(gas.readall().reducing, float):
        PROM_GAS_METRICS['gauge']['reducing'].set(gas.read_all().reducing)
        return gas.read_all().reducing
    else:
        return 0


def json_parsing_return():

    d_jsonexport={}
    d_jsonexport['instant']=strftime("%Y-%m-%d %H:%M:%S%Z", gmtime())
    d_jsonexport['nh3']=gas.read_all().nh3
    d_jsonexport['oxidising']=gas.read_all().oxidising
    d_jsonexport['reducing']=gas.read_all().reducing
    
    PROM_GAS_METRICS['gauge']['nh3'].set(d_jsonexport['nh3'])
    PROM_GAS_METRICS['gauge']['oxidising'].set(d_jsonexport['oxidising'])
    PROM_GAS_METRICS['gauge']['reducing'].set(d_jsonexport['reducing'])

    return d_jsonexport
```

Each of this have checking functions which enable to validate the type of values, and one which return the formatted values in json.

#### API Exposer

the main app : app.py

This application is composed of multiple route with specific actions, I describe it for you ;-) :

+  /
   +  Method : GET
   + the main route, it show a Welcome Message, and it can be use it to check the avaiability of the service
   + ``` { "result":{"Hello QIoT"}} ```

+  /api/sensors
   +  Method : GET
   +  this path display the differents route, it is a basic / static functions
   +  ``` {"result":{}} ```


+  /api/sensors/{gas,weather,pollution}
   +  Method : GET
   +  return the value of the sensor


+  /api/lcd
   +  Method : POST
   +  Display message into LCD screen


+  /api/docs
   +  Method : GET
   +  Return a docs about the API (Swagger)

Also we managed the **404 error page**

```python
#!/usr/bin/env python3

# Import basic libs
import time
import os
import atexit

# Import flask for webservice and prometheus for metrics
from flask import Flask,jsonify, Response,request, render_template
from prometheus_client import generate_latest, CONTENT_TYPE_LATEST

# Import applications libs
from metrics import REQUEST_TIME
import gas_extend
import particules_extend
import weather_extend
import lcd

atexit.register(lcd.stop)

# Create Flask application
app = Flask(__name__)

@app.route('/metrics')
def metrics():
    """Flask endpoint to gather the metrics, will be called by Prometheus."""
    return Response(generate_latest(), mimetype=CONTENT_TYPE_LATEST)

@app.route('/', methods=['GET'])
def index():
    result={}
    result['result']="Hello QIoT"
    return jsonify(result)


@app.route('/api/sensors', methods=['GET'])
def listsensor():
    if request.method == 'GET':
        listofSensor=[]
        listofSensor.append('/api/sensors/gas')
        listofSensor.append('/api/sensors/pollution')
        listofSensor.append('/api/sensors/weather')
        listofSensor.append('/api/lcd')
        result={}
        result={"result":listofSensor}

        return jsonify(result)


@app.route('/api/sensors/gas', methods=['GET'])
def get_data_gas():
    if request.method == 'GET':
        result={}
        result={"result":gas_extend.json_parsing_return()}
        return jsonify(result)

@app.route('/api/sensors/pollution', methods=['GET'])
def get_data_particules():
    if request.method == 'GET':
        result={}
        result={"result":particules_extend.json_parsing_return()}
        return jsonify(result)

@app.route('/api/lcd', methods=['POST'])
def post_message_to_lcd():
    if request.method == 'POST':
        data=request.get_json()
        result={"result":{"message posted":lcd.draw_message(data['message'])}}
        return jsonify(result)
    

@app.route('/api/sensors/weather', methods=['GET'])
@REQUEST_TIME.time()
def get_weather():
    if request.method == 'GET':
        result={}
        result={"result":weather_extend.json_parsing_return()}
        return jsonify(result)


@app.route('/api/docs')
def get_docs():
    print('sending docs')
    return render_template('swaggerui.html')

@app.errorhandler(404)
def ressource_not_found(e):
    error="{0}".format(e)
    return jsonify({"result":error}), 404


if __name__=='__main__':
    lcd.draw_message()
    app.run(host=os.getenv('FLASK_APP_HOST'),port=os.getenv('FLASK_APP_PORT'),
            debug=os.getenv('FLASK_APP_DEBUG'))

```
For all of this we use ***Flask***, we don't use [``` python3 app.py ```] to run the app. we use ***gunicorn*** to run it in production mode.

### Container image

To be compliant with the specifications, the container image is built based on the Fedora 31, with the following:
* Fedora base image, including all packages and python libraries to interract with the Raspberry Pi
* Fedora flask image, including python libraries and environment variables to launch flask application

The container is started with the following parameters:
* `-d` as daemon
* `--network=qiot` to be run in a specific dedicated network
* `-- privileged` to access to external devices such as GPIOs
* `-p 8000:8000` to expose external port 8000 (see [prometheus](prometheus.md), not used for production)
* `--name qiot-sensor` to define a tiny name

## Issues, Ideas

### Container Alpine

The current container is 970 MB, which is **HUGE** for a simple flask application. This is due mainly to:
* Fedora base image
* Python libraries and dependencies
* Unoptimised docker image build

We tried to build an alpine linux container, but the `numpy` python package is still compiling on aarch64 device...

### LCD

The Enviro+ board includes a LCD screen. We could use it to display usefull local information, inspired from [pimoroni examples](https://github.com/pimoroni/enviroplus-python/blob/master/examples/weather-and-light.py).

Instead, we prefer displaying useless information, and provides API endpoint, so if you want to post some text, on the board, you can:
```bash
curl -X POST -H 'Content-Type: application/json' -i 'http://127.0.0.1:8000/api/lcd' --data '{
"message": "Axians loves QIoT"
}'
```

Below the startup message:

![LCD message](img/enviro.jpg)

## Annexes

### Build process

1. Checkout code
1. Build image 
1. Login to Quay.io
1. Push to Quay!

```
$ git clone https://github.com/ACB-FR/qiot-sensor-py
$ cd qiot-sensor-py
$ sudo podman build -t quay.io/acb-fr/qiot-sensor -t quay.io/acb-fr/qiot-sensor:1-aarch64 -t quay.io/acb-fr/qiot-sensor:1.0.3 .
$ sudo podman login
$ sudo podman push quay.io/acb-fr/qiot-sensor:1.0.3
```

Note: podman commands are run in sudo mode, as the container runs in privileged mode, and it's easier for that PoC to build and run container as root.

### Start Container

Once the container is built, run it!

```
$ sudo podman run -d --network=qiot --privileged -p 8000:8000 --name qiot-sensor quay.io/acb-fr/qiot-sensor:1.0.3
```

Make it restart automatically on boot with systemd:

1. Generate systemd file
1. Modify to comply with new linux tree `/run`
1. Copy and activate service

```
$ sudo podman generate systemd --name qiot-sensor > podman-qiot-sensor.service
$ vi podman-qiot-sensor.service
PIDFile=/run/containers/storage/overlay-containers/[...]/userdata/conmon.pid
$ sudo systemctl daemon-reload
$ sudo systemctl enable podman-qiot-sensor
$ sudo systemctl start podman-qiot-sensor.service
```

1. Check it runs!

```
$ sudo systemctl status podman-qiot-sensor.service
● podman-qiot-sensor.service - Podman container-qiot-sensor.service
   Loaded: loaded (/etc/systemd/system/podman-qiot-sensor.service; enabled; vendor preset: disabled)
   Active: active (running) since Tue 2020-09-22 19:24:41 UTC; 5min ago
     Docs: man:podman-generate-systemd(1)
 Main PID: 97930 (conmon)
    Tasks: 3 (limit: 997)
   Memory: 3.4M
      CPU: 1.940s
   CGroup: /system.slice/podman-qiot-sensor.service
           ├─97928 /usr/sbin/dnsmasq -u root --conf-file=/run/containers/cni/dnsname/qiot/dnsmasq.conf
           └─97930 /usr/bin/conmon --api-version 1 -s -c 8ffb54b96b1abf4b9d1144d5458a72dd20cd51c0b9b4f64134670d32d5cfad8d -u 8ffb54b96b1abf4b9d1144d5458a72dd20cd51c0b9b4f64134670d32d5cfad8d -r /usr/bin>

Sep 22 19:24:41 qiot.verchere.lab dnsmasq[97928]: using local addresses only for domain dns.podman
Sep 22 19:24:41 qiot.verchere.lab dnsmasq[97928]: reading /etc/resolv.conf
Sep 22 19:24:41 qiot.verchere.lab dnsmasq[97928]: using local addresses only for domain dns.podman
Sep 22 19:24:41 qiot.verchere.lab dnsmasq[97928]: using nameserver 192.168.1.10#53
Sep 22 19:24:41 qiot.verchere.lab dnsmasq[97928]: using nameserver 192.168.1.254#53
Sep 22 19:24:41 qiot.verchere.lab dnsmasq[97928]: read /run/containers/cni/dnsname/qiot/addnhosts - 1 addresses
Sep 22 19:24:41 qiot.verchere.lab podman[97782]: 2020-09-22 19:24:41.29127181 +0000 UTC m=+1.755286386 container init 8ffb54b96b1abf4b9d1144d5458a72dd20cd51c0b9b4f64134670d32d5cfad8d (image=quay.io/acb>
Sep 22 19:24:41 qiot.verchere.lab podman[97782]: 2020-09-22 19:24:41.336614494 +0000 UTC m=+1.800629071 container start 8ffb54b96b1abf4b9d1144d5458a72dd20cd51c0b9b4f64134670d32d5cfad8d (image=quay.io/a>
Sep 22 19:24:41 qiot.verchere.lab podman[97782]: qiot-sensor
Sep 22 19:24:41 qiot.verchere.lab systemd[1]: Started Podman container-qiot-sensor.service.
```
