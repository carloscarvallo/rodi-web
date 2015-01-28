rodi-web
========
A web-service interface for RoDi (Robot Didáctico inalámbrico).

API
----

* Blink

    ```
    GET /blink/<rate-in-milliseconds>/
    ```

    ie.,
    ```
    curl --get http://192.168.4.1:1234/blink/1000/ // blink each second
    curl --get http://192.168.4.1:1234/blink/0/    // stop blinking
    ```

* Sense

    ```
    GET /sense/
    ```

    Returns a JSON formatted array of two integers, for left and right sensor values.

    ie.,
    ```
    $curl --get http://192.168.4.1:1234/sense/
    [62, 66]
    ```

* Move

    ```
    GET /move/<left-orientation>/<right-orientation>/
    ```

    ie.,
    ```
    $curl --get http://192.168.4.1:1234/move/97/97/   // stop
    $curl --get http://192.168.4.1:1234/move/0/0/     // turn right
    $curl --get http://192.168.4.1:1234/move/180/180/ // turn left
    $curl --get http://192.168.4.1:1234/move/0/180/   // forward
    $curl --get http://192.168.4.1:1234/move/180/0/   // backward
    ```

* Sing

    ```
    GET /sing/<note>/<duration>
    ```

    ie.,
    ```
    curl --get http://192.168.4.1:1234/sing/31/250/ // blink each second
    ```

    Notes can be found in http://arduino.cc/en/tutorial/tone

* See

    ```
    GET /see/
    ```

    Returns a JSON formatted integer, for the distance in centimeters.

    ie.,
    ```
    $curl --get http://192.168.4.1:1234/see/
    13
    ```

Authors
----------
* Martin Abente Lahaye - tch@sugarlabs.org

Cool Stuff
-------------------
I recommend Turtle Blocks (javascript) as a client for RoDi-web. Grab the latest
bits from https://github.com/walterbender/turtleblocksjs. Don't forget to load
the RoDi plugin!

