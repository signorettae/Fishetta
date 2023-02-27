# Fishetta

# Status: Archived

This repository has been archived and is no longer maintained because the Pushetta service does not exist anymore.
![status: inactive](https://img.shields.io/badge/status-inactive-red.svg)

---

## Fishetta - A Pushetta library for Fishino Boards

Since I've been using [Fishino](https://fishino.com/home.html) boards I wanted to easily send notifications to my devices.

I found a free service called [Pushetta](https://www.pushetta.com/) which allowed to send push notifications by sending  a simple HTTP request using their [API](https://web.archive.org/web/20191026083212/http://www.pushetta.com/pushetta-api/).

On the [documentations](https://web.archive.org/web/20191026165325/http://www.pushetta.com/pushetta-docs) I found a code snipped for Arduino boards so i managed to write a Fishino library starting from it.

### A simple example

Here you can find the most important parts of the example sketch.

```C++
///////////////////////////////////////////////////////////////////
//   Fishetta library example                                    //
//   Created by Emanuele Signoretta, August 9, 2017.             //
//   Send push notification by using the Pushetta webapp.        //
///////////////////////////////////////////////////////////////////

#include <SPI.h>
#include <Fishino.h> 
#include <Fishetta.h>

[...]

const char * APIKEY  = "" ; // Put here your API key 
const char * CHANNEL  = ""; // Put here your channel name

[...]

Fishetta push(CHANNEL,APIKEY); 

void setup()
{
[...]
}

void loop()
{

if (push.sendPushNotification("Fishetta library test!")){
  String serial_print = "Sent push notification at ";
  serial_print += CHANNEL;
  serial_print += " channel !";
  Serial.println(serial_print.c_str());} 

delay(10000);

}
```
