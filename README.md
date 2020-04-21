# Distributed Web Server - Prototype
This is a prototype of a distributed web server built with [Node js](https://github.com/nodejs/node) alongside Node js Framework [Express](http://expressjs.com/) with the purpose of demonstrating how a web server may be distributed internally.

## Architecture
We have built three distinct web servers distributed locally. __Server Distributer__ as the main server, being the one responsible for handling client requests and feching files that are all hosted on the other two servers, __Server A__ and __Server B__. As a matter of security, __Server A__ and __Server B__ will only allow requests coming from __Server Distributer__ even though they are not necessarily connected to the internet. Servers __A__ and __B__ work as File Servers serving files to __Server Distributer__, which then send them to the clients accordingly.

This prototype project has its architecture entirely based on the one illustrated below.
![illustration](assets/img/web-server-illustration.png)

### File Structure
* Distributer Server
```
       |--- conf 
src ---|--- controller 
       |--- routes 
```
* Internal Servers _(host servers A and B)_
```
       |--- conf
src ---|
       |--- public
```
In Distributer Server conf.js file in conf folder you will find the following configuration:
* Host: Distributer HOST;
* Port: Distributer PORT;
* Servers: Object with all the __Internal Servers__ available to fetch files from.

In Internal Servers conf.js files you will find the following configuration:
* Host: Internal Server HOST;
* Port: Internal Server PORT;
* Distributer: Domain to allow requests from (__Distributer Server__ domain).

> Files to be provided go in public folder of __Internal Servers__.

## Hosted Applications
These below are the relative paths of each of the hosted applications we have included in our project.
* ```/spotify/home```: PWA mini-player using Spotify data, with a search area for artists or songs and a 30-second audio player. This application is being hosted on __Internal Server B__ and serves as an example on how widely distrubuted a distributed server can be, conceptually speaking. It brings up data from distributed web servers on the web while being hosted on an internal server that is part of another distributed web server. See more details about this project in particular [here](https://github.com/Dheyson/spotify-player);

* ```/aria/home```: Html template downloaded at [onepagelove](https://onepagelove.com/aria). Hosted on __Internal Server A__;
* ```/dazzle/home```: Html template donwloaded at [onepagelove](https://onepagelove.com/dazzle). Hosted on __Internal Server B__.

## Getting Started
### Prerequisites
What things you need to install the software and how to install them

```
nodejs >= 10.0
npm >= 6.10.0 or yarn@latest
```

### Installing
A step by step series of examples that tell you how to get a development env running

Say what the step will be
```
- Download the project or clone it
- npm install or yarn install on each root server
- npm run dev or yarn run dev on each root server
```

## Contributing
Please read [CONTRIBUTING.md](https://github.com/melquibrito/distributed-web-server/blob/master/CONTRIBUTING.md) for details on our code of conduct, and the process for submitting pull requests to us.

## Authors
* **[Melqui Brito](https://github.com/melquibrito)** - _Web Servers_
* **[Dheyson Alves](https://github.com/Dheyson)** - _[PWA Spotify Player](https://github.com/Dheyson/spotify-player)_
* **[Átila Assunção](https://github.com/AtilaAssuncao)** - _Web Servers_

See also the list of [contributors](https://github.com/melquibrito/distributed-web-server/contributors) who participated in this project.

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE.md) file for details.

