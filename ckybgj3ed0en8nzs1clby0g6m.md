---
title: "How to generate and use an SSL certificate in NodeJS"
seoTitle: "How to generate and use an SSL certificate in NodeJS"
datePublished: Wed Jan 12 2022 11:26:13 GMT+0000 (Coordinated Universal Time)
cuid: ckybgj3ed0en8nzs1clby0g6m
slug: ssl-certificate-in-nodejs
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1641986641610/-V02jcCMl.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1641986741834/xZrEjX6Ko.jpeg
tags: ssl, nodejs, expressjs-cilb5apda0066e053g7td7q24

---

In this article, we will see how can we generate an SSL certificate for our development server. And later on, we will see how can we use that certificate inside our application.

## Let's Create a Demo App in Express js

To create a new **npm** project, let's create a directory named "**node-ssl-server**" and open the **node-ssl-server** directory in the terminal using this command.
```cmd
cd node-ssl-server
```

 Then run this command to create a new **npm** project.

```cmd
 npm init -y
```
Now let's install the dependency i.e **express**, to do so run this command:
```cmd
npm install --save express
```
Now let's create a start script in **package.json**, just add this line inside the "**script{}**"  as shown below:

```js
"scripts": {
    "start":"node index.js"
  },
```

you can also use nodemon if you have nodemon installed in your system like this:

```js
"scripts": {
    "start":"nodemon index.js"
  },

```
Now let's add a **index.js** file in our app and add few lines in it as shown below:
```js
const express = require('express') 
const https = require("https") // https module to create a ssl enabled server
const path = require("path") // path module 
const fs = require("fs") //file system module

const app =express()

app.use("/",(req,res,next)=>{
    res.send("hello from ssl secured server!!")
})

const options ={
  key:'',
  cert:'' 
}
const sslserver =https.createServer(options,app)

sslserver.listen(port,()=>{console.log(`Secure Server is listening on port ${port}`)});
```

## Let's Generate SSL Certificates

before we proceed further let's create a directory to store the certificates inside our app folder. 

```cmd
mkdir cert
```

now move to the **cert** directory using **cd** command
```cmd 
cd cert
``` 
To generate the SSL Certificate we need to follow these steps as shown below:
- Generate a Private Key
- Create a CSR ( certificate signing request) using the private key.
- Generate the SSL certification from CSR
  
#### Generate a Private Key

To generate a private key we will run this command as shown below:
```cmd
 openssl genrsa -out key.pem
```
Once we ran the above command it will generate the private key and save it in **key.pem** file inside **cert** directory and gives this type of message in the terminal.
```cmd
Generating RSA private key, 2048 bit long modulus
...+++
.................+++
e is 65537 (0x10001)
```

#### Create a CSR ( Certificate Signing Request)

Since we are our own certificate authority, we need to use CSR to generate our certificate. To do so we need to run the below command.
```cmd
openssl req -new -key key.pem -out csr.pem
```
Once we ran this command it will ask a few questions as shown below:

```cmd
You are about to be asked to enter information that will be incorporated
into your certificate request.
What you are about to enter is what is called a Distinguished Name or a DN.
There are quite a few fields but you can leave some blank
For some fields, there will be a default value,
If you enter '.', the field will be left blank.
-----
Country Name (2 letter code) [XX]:IN
State or Province Name (full name) []:
Locality Name (eg, city) [Default City]:
Organization Name (eg, company) [Default Company Ltd]:
Organizational Unit Name (eg, section) []:
Common Name (eg, your name or your server's hostname) []:
Email Address []:

Please enter the following 'extra' attributes
to be sent with your certificate request
A challenge password []:
An optional company name []:
```
you can skip any question by simply press enter else if you want to provide the details you can provide it, it's totally upto you.

Once you done with these question it will generate the CSR in **csr.pem** file inside **cert** folder.




#### Generate the SSL Certificate

Now for the final steps, we need to use the **key.pem**  and **crs.pem** files to generate our SSL certificate. 

let's run the below command to generate it.

```cmd
openssl x509 -req -days 365 -in csr.pem -signkey key.pem -out cert.pem
```
### Note: 
- we are using [x509](https://en.wikipedia.org/wiki/X.509) because it is the standard defining the format of the public-key certificate.
- we set the validity of the certificate as 365 days.

After running the above command it will save the certificate in the **cert.pem** file inside **cert** folder. Now you can remove the **csr.pem** file or you can keep it.



## Integration of the SSL Certificate in Express

Now let's use these certificates inside our app using **file system (fs) and path module**. To do so, we need to edit a few lines in our app as mentioned below:

Earlier we had created  a constant variable **options**. now we will update that part of the code by adding the path of the generated certificates inside it as shown below.

Before:
```js
const options ={
  key:'',
  cert:'' 
}
```
After:
```js
const options ={
  key:fs.readFileSync(path.join(__dirname,'./certs/key.pem')),
  cert:fs.readFileSync(path.join(__dirname,'./certs/cert.pem')) 
}

```

Once it's done save it and run the server by 
```cmd
npm start
```
You can check if HTTPS is working or not by just accessing it from this URL:
```chrome
https://localhost:3002
```


## Conclusion:
- You might see **Not Secure** in your browser though we have a valid certificate, it is just because we have generated the certificate and it is not generated by some known certificate authorities, so, your browser doesn't Trust you as a valid certificate authority. But we should typically use this process for development purposes and for Production we should be using a certificate that is generated by a certificate authority like **Let's Encrypt**.