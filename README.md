Network Security using SDN (IP Blacklist)

Objective: To block an IP listed in a file.

In this project we use Floodlight SDN controller. We dynamically update a file containing an IP address. We use REST API to perform GET, POST and DELETE operations.

Set-up and installation in VirtualBox:

Commands to run the project

1. Use Ubuntu 16.04
2. Install Mininet
3. Install Floodlight controller 
4. Install Java 8
   sudo apt-get install default-jre 
   sudo apt-get install default-jdk
5. Start Floodlight Controller in a terminal
   $ java -jar target/floodlight.jar
6. Create topology in Mininet by using the command:
    $ sudo mn --controller=remote,ip=127.0.0.1,port=6653 --switch ovsk,protocols=OpenFlow13 --topo single,3
7. In a new terminal install curl
   $ sudo apt-get install curl
8. Use the following commands for GET, POST and DELETE 
   curl -s http://localhost:8080/wm/ipblacklist/ipblacklist/json | python -mjson.tool
   curl -X POST -d '{"ip":"10.0.2.15"}' http://localhost:8080/wm/ipblacklist/ipblacklist/json
   curl -X DELETE -d '{"ip":"10.0.2.16"}' http://localhost:8080/wm/ipblacklist/ipblacklist/json

