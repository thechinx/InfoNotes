---
description: >-
  Webpage used to store links for all running services on localhost for ADS-B
  feeders.
---

# ADS-B local webpage

## ADS-B local webpage

First check for permissions of directory by running the following commend:

```
ls -la /opt
```

your results should show username owning the directory:

```
dave@flight01:~$ ls -la /opt/
total 44
drwxr-xr-x 10 dave dave 4096 Jul  7 17:24 .
drwxr-xr-x 21 root root 4096 Aug  9  2022 ..
drwxr-xr-x  4 dave dave 4096 Jul  7 11:02 adsb
drwxrwxr-x  2 dave dave 4096 Jun  3 17:03 adsb_backup
drwx--x--x  4 dave dave 4096 Jul  6  2021 containerd
-rw-rw-r--  1 dave dave 1618 Oct 13  2022 docker-compose.yml
drwxr-xr-x  3 root root 4096 Jan 23  2022 duplicati
drwxr-xr-x  4 dave dave 4096 Oct 13  2022 nginx
drwxr-xr-x  2 dave dave 4096 Jul  6  2021 node-exporter
drwxr-xr-x  2 dave dave 4096 Jul  6  2021 portainer-agent
drwxrwxr-x  2 dave dave 4096 Apr  6  2022 telegraf
```

If the directory is owned by root ( drwxr-xr-x 3 root root) run the following command: ( change "user" to your username)

```
sudo chown -R user:user /opt/  
```

Next add the HTML code. You will need to change all X.X.X.X to your machines local IP address.

```
cd /opt/nginx/src
```

```
nano index.html
```

copy code below and paste. You will need to change all X.X.X.X to your machines local IP address before saving.

```
<!DOCTYPE html>
<html>
  <head>
    <title>Local ADS-B links for Chin Network</title>
    <style>
      .button {
        display: inline-block;
        padding: 10px 20px;
        text-align: center;
        text-decoration: none;
        color: #ffffff;
        background-color: #7aa8b7;
        border-radius: 6px;
        outline: none;
      }
    </style>
  </head>
  <body>
<center>
<h2> Chin Network ADS-B Links </h2>
</center>
    <a class="button" href="http://X.X.X.X:8080" target="_blank">tar1090</a>&nbsp;&nbsp;<a class="button" href="http://X.X.X.X:8080/graphs1090/" target="_blank">Graphs1090</a>&nbsp;&nbsp;<>
<p>
    <a class="button" href="http://X.X.X.X:8081" target="_blank">FlightAware</a>
<p>
    <a class="button" href="http://X.X.X.X:8754" target="_blank">FlightRadar24</a>
<p>
    <a class="button" href="http://X.X.X.X:30053" target="_blank">PlaneFinder</a>
<p>
    <a class="button" href="https://www.adsbhub.org/statistic.php" target="_blank">ADSBHub</a>
<p>
    <a class="button" href="https://opensky-network.org/receiver-profile" target="_blank">OpenSky Network</a>
<p>
    <a class="button" href="https://theairtraffic.com/feed/myip/" target="_blank">TheAirTraffic</a>
<p>
    <a class="button" href="https://adsb.one/feeder-status" target="_blank">ADSB.One Status</a>&nbsp;&nbsp;<a class="button" href="https://adsb.fi/" target="_blank">ADSB.fi Status</a>
<p>
</body>
</html>

```

Save the file and from a browser enter `http://your.local.ip.address/` to visit site.
