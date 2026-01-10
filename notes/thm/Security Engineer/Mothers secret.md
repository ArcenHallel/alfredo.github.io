going to break down how this room works.

you can use birpsuite for this but i used mozilla web broswer instead

visit IP machine in browser

takes us to ![[Pasted image 20240619193536.png]]

with 4 different options 

![[Pasted image 20240619193605.png]]

 the other 2 not important, only the flag we will need but its blocked since we are not the right user yet.


right click and inspect the webpage


under the **network** tab we can see the status of the traffic and more details 

![[Pasted image 20240619193809.png]]

right click that status to edit and resent

![[Pasted image 20240619193925.png]]

the file from the class room is a yaml file 

add to the header 

* content-type:  application/json

![[Pasted image 20240619195501.png]]

from the file provided to us in the room

API ROUTES

------------------------------------------

yaml.js
------------------------------------------

import express from "express";
import yaml from "js-yaml";
import fs from "fs";
import { attachWebSocket } from "../websocket.js";

const Router = express.Router();

const isYaml = (filename) => filename.split(".").pop() === "yaml"; ^61eac7

Router.post("/", (req, res) => {
  let file_path = req.body.file_path;
  const filePath = `./public/${file_path}`; ^6f3c77

  if (!isYaml(filePath)) {
    res.status(500).json({
      status: "error",
      message: "Not a YAML file path.",
    });
    return;
  }

  fs.readFile(filePath, "utf8", (err, data) => {
    if (err) {
      res.status(500).json({
        status: "error",
        message: "Failed to read the file.",
      });
      return;
    }  ^1f7355

	res.status(200).send(yaml.load(data));

    attachWebSocket().of("/yaml").emit("yaml", "YAML data has been processed.");
  });
});

export default Router;
------------------------------------------

Nostromo.js
------------------------------------------

import express from "express";
import fs from "fs";
// import { attachWebSocket } from "../../mothers_secret_challenge/websocket.js";
import { attachWebSocket } from "../websocket.js";
import { isYamlAuthenticate } from "./yaml.js";
let isNostromoAuthenticate = false;

const Router = express.Router();

Router. post ("/nostromo", (req, res) => {
  let file_path = req.body.file_path;
  const filePath = `./public/${file_path}`;

  fs.readFile(filePath, "utf8", (err, data) => {
    if (err) {
      res.status(500).json({
        status: "error",
        message: "Science Officer Eyes Only",
      });
      return;
    }

    isNostromoAuthenticate = true
    res.status(200).send(data);

    attachWebSocket()
      .of("/nostromo")
      .emit("nostromo", "Nostromo data has been processed.");
  });
});

Router.post("/nostromo/mother", (req, res) => {
 
  let file_path = req.body.file_path;
  const filePath = `./mother/${file_path}`;

  if(!isNostromoAuthenticate || !isYamlAuthenticate){
    res.status(500).json({
      status: "Authentication failed",
      message: "Kindly visit nostromo & yaml route first.",
    });
    return 
  }

  fs.readFile(filePath, "utf8", (err, data) => {
    if (err) {
      res.status(500).json({
        status: "error",
        message: "Science Officer Eyes Only",
      });
      return;
    }

    res.status(200).send(data);

    // attachWebSocket()
    //   .of("/nostromo")
    //   .emit("nostromo", "Nostromo data has been processed.");
  });
});

export default Router;
___________
##

inspecting the file we can see a status of POST[[#^6f3c77]]
Router.post("/nostromo", (req, res) => {
 let file_path = req.body.file_path;
const filePath = `./public/${file_path}`

knowing that these are POST requests with error codes change the request from GET to POST

![[Pasted image 20240619200116.png]]

in the body of the request: (we now its a yaml file based off)[[#^61eac7]]
	 {"file_path": " test.yaml"}
	
![[Pasted image 20240619200450.png]]

what we get is status "error" 
message "failed to read the file"
looking back at the json file it states that if the file is not present we get 

status "error" 
message "failed to read the file" [[#^1f7355]]

from the provided information in the room 


"Operating Manual

﻿Below are some sequences and operations to get you started. Use the following to unlock information and navigate Mother:

* Emergency command override is 100375. Use it when accessing Alien Loaders. 
* Download the task files to learn about Mother's routes.
* Hitting the routes in the right order makes Mother confused, it might think you are a Science Officer!"


the 100375:  "use it when accessing Alien Loader"
ok lets try changing the in the "body"

![[Pasted image 20240619200831.png]]

we get more info 
api/nostromo & 0rd3r937.txt 

* *REROUTING TO: api/nostromo

back in the POST request add api/nostromo
![[Pasted image 20240619201245.png]]
and in the body
0rd3r937.txt
![[Pasted image 20240619201355.png]]
resend and we get 

![[Pasted image 20240619201313.png]]

we now have the order 
* Flag{X3n0M0Rph}  
* 937
 and our security clearance has changed 
![[Pasted image 20240619201446.png]]
we are now ash instead of crew mate

back to the room details it states:
**Can you guess what is /api/nostromo/mother/secret.txt?

/api/nostromo/mother
lets add this to the POST request
![[Pasted image 20240619201805.png]]
and back at the body lets replace our last txt with secret.txt 
![[Pasted image 20240619201819.png]]
and what we get is ![[Pasted image 20240619201834.png]]

the secret stating that in /opt/m0th3r has our last flag

to travers to that dir we edit the body to 
` ../../../../` to move 4 spaces into `/opt/m0th3r
![[Pasted image 20240619202247.png]]

Flag{Ensure_return_of_organism_meow_meow!}


#thm #exploit #