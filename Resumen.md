# An Overview on Embedded Systems

A embedded system, is a computer system with a dedicated function within a larger mechanical or electrical system, often with real-time computing constraints. It is designed to perform a specific task and it is embedded as a part of a complete device often including hardware and mechanical parts.
Some examples of portable devices can be digital watches, MP3 player, factory controllers and larger ones such as stationary installations like traffic lights, factory controllers or even hybrid vehicles. 

Embedded systems have been widely developed in comparison to years ago. These devices interact with the real world and are connected to the internet and so they are open to attacks, hackers and multiple threats.
These attacks may result in physicial side effect as potential damages or personal injury. This is why security in these systems becomes a must. (link to wiki https://en.wikipedia.org/wiki/Embedded_system)

One of the considerations in security for embedded systems, due to their rapid growth are authentication for users, intrusion detection  and so, security requirements have become critical. Main issues in security are encountered when the data is routed through Ethernet, Wi-fi, WiMAX or Bluetooth. So, one possibility of adding security to them is by implementing cryptography algorithms in software. However, they are many challenges and requirements to it. First, performance of these algorithms is key, because they must run at the same rate as the data transmission so it can remain invisible to the user and can't be too fast either, because it might means higher production costs. 
Also, guranteeing security is a challenge. Encryption algorithm has limited physicial security as the secure storage of keys is difficult in most operative systems. 
Hardware encryption devices can be securely encapsulated to prevent attackers from tampering with the system, that means custom hardware is the way to go. However, hardware solution come with a reduced flexibility and again higher costs.
Finally, many of the security protocols decouple the choice of cryptographic algorithm from the design of the protocol. Users negotiate the choice of algorithm to use for a particular secure session. This means, that new devices, to support these applications, should support multiple cryptographic algorithms and protocols or *algorithm agile*, that is be able to select from a variety of algorithms. (link to http://web.itu.edu.tr/~orssi/projeler/ESD_crypto.html)

 
# Criptography 
Crypthography is the study and practice of techniques for secure communication, is about constructing and analyzing protocols to prevent third parties to read private messages.
As the technology advances, security issues became a mayor concern, thus increasing the use of cryptography as a method for maintaining data confidentiality, integrity and authentication. 

## Simmetric Cryptography
Also known as single key encryption, in where encryption and decryption processes are performed by using the same key.
It contains 5 elements:
- Plaintext 
- Encryption Algorithm
- Private Key
- Cyphertext
- Decryption Algorithm

![alt text](https://www.dropbox.com/pri/get/figura1.jpg?_subject_uid=115145873&w=AADVj7FYxyoLYwtfM5Td98AI0DmNMbxJUbZpTB7UMe_cYw)

### Block Cipher Principles
Block Cipher is a type of symmetric encription algorithm that operates on fixed-length groups of bits of plaintext, called blocks and transform them into ciphertext block of the same length. Due that it is symmetric cryptography, it uses the same private key for encryption and decryption.
The block size is usually 64 or 128 bits long.


![alt text](https://www.dropbox.com/pri/get/figura2.jpg?_subject_uid=115145873&w=AABvXUQOIzZX46FWARaoYeRzDAwzJSRF5ae5ms_lIk0DnQ)


A block cipher consists of two paired algorithms, one for encryption, E, and the other for decryption, D. Both algorithms accept two inputs: an input block of size n bits and a key of size k bits; and both yield an n-bit output block. The decryption algorithm D is defined to be the inverse function of encryption, $$D=E^{-1}$$. 

# Data Encryption Standard or DES Algorithm
Developed in the early 1970s at IBM and based on an earlier design by Horst Feistel, the algorithm was submitted to the National Bureau of Standards (NBS) following the agency's invitation to propose a candidate for the protection of sensitive, unclassified electronic government data. In 1976, after consultation with the National Security Agency (NSA), the NBS eventually selected a slightly modified version (strengthened against differential cryptanalysis, but weakened against brute force attacks), which was published as an official Federal Information Processing Standard (FIPS) for the United States in 1977.
DES is now considered insecure for many applications and so it has been replaced by AES algorithm.

DES encryption process is to transform a 64 bit input into a 64 bit output, uses a 64 bit key, though only 56 are actually used by the algorithm and the 8 remain are used for checking parity and are discarded, so the effective key lenght is 56 bits.
Des algorithm envolves a sixteen step process in order to do the transformation, called rounds, the first and last one, is permutation ( *IP*  and *FP*  in the figure below), then, the block is broken into two blocks of 32 bit lenght blocks ($$L_i, R_i)$$. Both block use a individual key:

$$K_i L_i :=R_{i-1};  R_i:=L_{i-1} \oplus f(R_{i-1, K_i})$$

As shown in the figure below.
![alt text](https://www.dropbox.com/pri/get/figura3.jpg?_subject_uid=115145873&w=AABfgVuX8gwNPZin3Dm943ky_5CCCcxkgVLyYl73vSY6JQ)
In the second image, it's possible to see the 16 rounds and the criss-crossing is known as the Feistel scheme.
![alt text](https://upload.wikimedia.org/wikipedia/commons/thumb/6/6a/DES-main-network.png/250px-DES-main-network.png)

The Feistel Scheme used in DES can be summarized in the following image, with $$K_n$$ being the *K-th* key of the round n  
![alt text](https://upload.wikimedia.org/wikipedia/commons/thumb/f/fa/Feistel_cipher_diagram_en.svg/511px-Feistel_cipher_diagram_en.svg.png)

### DES Rounds

1. Permutation 




|58|50|42|34|26|18|10|2
|--|:--|--:|--:|--:|--:|--:|--:|
|60|52|44|36|28|20|12|4|
|62|54|46|38|30|22|14|6|
|64|56|48|40|32|24|16|8|
|57|49|41|33|25|17|9| 1|
|59|51|43|35|27|19|11|3| 
|61|53|45|37|29|21|13|5|
|63|55|47|39|31|23|15|7|
The matrix represents the vector of the first permutation of the 64 bit block

* [AngularJS] - HTML enhanced for web apps!
* [Ace Editor] - awesome web-based text editor
* [markdown-it] - Markdown parser done right. Fast and easy to extend.
* [Twitter Bootstrap] - great UI boilerplate for modern web apps
* [node.js] - evented I/O for the backend
* [Express] - fast node.js network app framework [@tjholowaychuk]
* [Gulp] - the streaming build system
* [Breakdance](http://breakdance.io) - HTML to Markdown converter
* [jQuery] - duh

And of course Dillinger itself is open source with a [public repository][dill]
 on GitHub.

### Installation

Dillinger requires [Node.js](https://nodejs.org/) v4+ to run.

Install the dependencies and devDependencies and start the server.

```sh
$ cd dillinger
$ npm install -d
$ node app
```

For production environments...

```sh
$ npm install --production
$ npm run predeploy
$ NODE_ENV=production node app
```

### Plugins

Dillinger is currently extended with the following plugins. Instructions on how to use them in your own application are linked below.

| Plugin | README |
| ------ | ------ |
| Dropbox | [plugins/dropbox/README.md] [PlDb] |
| Github | [plugins/github/README.md] [PlGh] |
| Google Drive | [plugins/googledrive/README.md] [PlGd] |
| OneDrive | [plugins/onedrive/README.md] [PlOd] |
| Medium | [plugins/medium/README.md] [PlMe] |
| Google Analytics | [plugins/googleanalytics/README.md] [PlGa] |


### Development

Want to contribute? Great!

Dillinger uses Gulp + Webpack for fast developing.
Make a change in your file and instantanously see your updates!

Open your favorite Terminal and run these commands.

First Tab:
```sh
$ node app
```

Second Tab:
```sh
$ gulp watch
```

(optional) Third:
```sh
$ karma test
```
#### Building for source
For production release:
```sh
$ gulp build --prod
```
Generating pre-built zip archives for distribution:
```sh
$ gulp build dist --prod
```
### Docker
Dillinger is very easy to install and deploy in a Docker container.

By default, the Docker will expose port 80, so change this within the Dockerfile if necessary. When ready, simply use the Dockerfile to build the image.

```sh
cd dillinger
docker build -t joemccann/dillinger:${package.json.version}
```
This will create the dillinger image and pull in the necessary dependencies. Be sure to swap out `${package.json.version}` with the actual version of Dillinger.

Once done, run the Docker image and map the port to whatever you wish on your host. In this example, we simply map port 8000 of the host to port 80 of the Docker (or whatever port was exposed in the Dockerfile):

```sh
docker run -d -p 8000:8080 --restart="always" <youruser>/dillinger:${package.json.version}
```

Verify the deployment by navigating to your server address in your preferred browser.

```sh
127.0.0.1:8000
```

#### Kubernetes + Google Cloud

See [KUBERNETES.md](https://github.com/joemccann/dillinger/blob/master/KUBERNETES.md)


### Todos

 - Write MOAR Tests
 - Add Night Mode

License
----

MIT


**Free Software, Hell Yeah!**

[//]: # (These are reference links used in the body of this note and get stripped out when the markdown processor does its job. There is no need to format nicely because it shouldn't be seen. Thanks SO - http://stackoverflow.com/questions/4823468/store-comments-in-markdown-syntax)


   [dill]: <https://github.com/joemccann/dillinger>
   [git-repo-url]: <https://github.com/joemccann/dillinger.git>
   [john gruber]: <http://daringfireball.net>
   [df1]: <http://daringfireball.net/projects/markdown/>
   [markdown-it]: <https://github.com/markdown-it/markdown-it>
   [Ace Editor]: <http://ace.ajax.org>
   [node.js]: <http://nodejs.org>
   [Twitter Bootstrap]: <http://twitter.github.com/bootstrap/>
   [jQuery]: <http://jquery.com>
   [@tjholowaychuk]: <http://twitter.com/tjholowaychuk>
   [express]: <http://expressjs.com>
   [AngularJS]: <http://angularjs.org>
   [Gulp]: <http://gulpjs.com>

   [PlDb]: <https://github.com/joemccann/dillinger/tree/master/plugins/dropbox/README.md>
   [PlGh]: <https://github.com/joemccann/dillinger/tree/master/plugins/github/README.md>
   [PlGd]: <https://github.com/joemccann/dillinger/tree/master/plugins/googledrive/README.md>
   [PlOd]: <https://github.com/joemccann/dillinger/tree/master/plugins/onedrive/README.md>
   [PlMe]: <https://github.com/joemccann/dillinger/tree/master/plugins/medium/README.md>
   [PlGa]: <https://github.com/RahulHP/dillinger/blob/master/plugins/googleanalytics/README.md>
