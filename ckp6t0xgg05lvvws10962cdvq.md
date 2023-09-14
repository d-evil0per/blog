---
title: "How to host websites using free cloud storage"
seoTitle: "How to host websites using free cloud storage"
seoDescription: "You can host static websites using free cloud storage like google drive & one drive."
datePublished: Thu May 27 2021 11:19:49 GMT+0000 (Coordinated Universal Time)
cuid: ckp6t0xgg05lvvws10962cdvq
slug: serverless-hosting
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1622106424183/5p3YxWgn1.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1622106436729/NTrDOUBcr.jpeg
tags: server-hosting, serverless, 2articles1week

---

We use free cloud storage daily, If you own an Android device you should have the **Google Drive** app pre-installed on your phone. Google provides free storage up to **15 GB** for each Gmail user and similarly, Microsoft also provides free cloud storage as **Onedrive** with **5 GB** storage space. People use this drive to store their personal files and data so that they do not have to carry it with them everywhere.  they can access those files from anywhere and anytime. people can also share those files with anybody with some restriction or no restriction depending upon the person to whom they are sharing the files and the confidentiality of the data. 

Now in this article, we will learn how can we use it to host a website. Let suppose I am a student or a learner and I am working on my portfolio design and I want that it should be available on the internet so that my mentor can access and see the progress of the website. So, It makes me end up asking these questions to myself. **Where can I host it?** and **how can I do it for free?** Because I don't have a budget to host it on a server.

Let's get started with the process. First, we need to create a simple website that we can host on our google drive and one drive. you can use your own website and follow the steps provided in this article. So, let create a website.

I am planning to design a website which looks something like this:


![exsite.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1622109018291/XI5S4LFro.png)
 
From below you can find the  HTML code with in-line CSS, you can also use external `css` and `js` files and place it under some folder named `static`  or `assets`

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="utf-8" />
        <meta name="viewport" content="width=device-width, initial-scale=1.0, shrink-to-fit=no" />
        <title>drivetoweb</title>
        <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/twitter-bootstrap/4.6.0/css/bootstrap.min.css" />
        <link rel="stylesheet" href="https://use.fontawesome.com/releases/v5.12.0/css/all.css" />
        <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/ionicons/2.0.1/css/ionicons.min.css" />
    </head>
    <body style="font-family: Poppins, sans-serif; background: #e0e0e0;">
        <div
            class="container-fluid d-flex d-sm-flex d-md-flex d-lg-flex d-xl-flex justify-content-center align-items-center justify-content-sm-center align-items-sm-center justify-content-md-center align-items-md-center justify-content-lg-center align-items-lg-center justify-content-xl-center align-items-xl-center"
            style="height: 700px; border-style: none;"
        >
            <div class="card" style="border-radius: 20px; background: #e0e0e0; box-shadow: 20px 20px 60px #bebebe, -20px -20px 60px #ffffff; border-style: none; border-top-left-radius: 120px; border-bottom-left-radius: 120px;">
                <div class="card-body">
                    <div class="row justify-content-around justify-content-xl-center">
                        <div
                            class="col-12 col-sm-4 col-md-4 col-lg-4 col-xl-4 d-flex d-sm-flex d-md-flex d-lg-flex d-xl-flex justify-content-center align-items-center justify-content-sm-center align-items-sm-center justify-content-md-center align-items-md-center justify-content-lg-center align-items-lg-center justify-content-xl-center align-items-xl-center"
                        >
                            <img class="rounded-circle" src="assets/img/173155111_3910222829061840_984467136129611587_n.jpg" width="200" />
                        </div>
                        <div class="col offset-0 offset-sm-1 offset-md-1 offset-lg-1 offset-xl-1">
                            <h2 class="d-flex justify-content-center justify-content-sm-start justify-content-md-start justify-content-lg-start align-items-lg-center" style="color: var(--secondary);">Rahul Dubey</h2>
                            <h6 class="d-flex justify-content-center justify-content-sm-start justify-content-md-start justify-content-lg-start" style="color: var(--secondary);">Developer | Artist | Writer</h6>
                            <p class="d-flex justify-content-center justify-content-md-start justify-content-lg-start" style="color: rgb(108, 117, 125);">Hi, Please follow my blog&nbsp; for more interesting articles.</p>
                            <div class="row">
                                <div class="col-8 col-sm-7 col-md-7 col-lg-7 col-xl-7 offset-2 offset-sm-0 offset-md-0 offset-lg-0 offset-xl-0">
                                    <div>
                                        <div class="d-flex justify-content-between social-icons d-block" style="padding: 0px; background: transparent;">
                                            <a href="https://deviloper.in" target="_blank"><i class="fab fa-blogger-b shadow-soft" style="color: rgb(117, 121, 128); font-size: 24px; border-style: none; border-color: var(--blue);"></i></a>
                                            <a href="https://twitter.com/XcessDhir" target="_blank">
                                                <i class="icon ion-social-twitter shadow-soft" style="color: rgb(117, 121, 128); font-size: 24px; border-style: none; border-color: var(--blue);"></i>
                                            </a>
                                            <a href="https://www.facebook.com/dhir.kashayup" target="_blank"><i class="icon ion-social-facebook shadow-soft" style="border-style: none; color: rgb(117, 121, 128); font-size: 24px;"></i></a>
                                            <a href="https://www.instagram.com/dhir.kashayup/" target="_blank"><i class="icon ion-social-instagram shadow-soft" style="border-style: none; color: rgb(117, 121, 128); font-size: 24px;"></i></a>
                                            <a href="https://www.linkedin.com/in/rahuldubey4311/" target="_blank">
                                                <i class="icon ion-social-linkedin shadow-soft" style="border-style: none; color: rgb(117, 121, 128); font-size: 24px;"></i>
                                            </a>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.6.0/jquery.min.js"></script>
        <script src="https://cdnjs.cloudflare.com/ajax/libs/twitter-bootstrap/4.6.0/js/bootstrap.bundle.min.js"></script>
    </body>
</html>

```
**You can download this design from my  [Github](https://github.com/d-evil0per/serverless-hosting)  Repository.**

Now once my design is ready, I need to upload this into google drive or one drive to host it. Let's see the steps for hosting it on both cloud storage.

## Hosting on Free Cloud Storage

For hosting we are using  [DriveToWeb ](https://drv.tw). let me give you some brief about it.

[DriveToWeb ](https://drv.tw) liberates content creation by enabling anyone to quickly spin up a website using files stored on popular cloud drives, such as Google Drive and Microsoft OneDrive (including OneDrive for Business). Entrepreneurs, developers, educators, and students all over the world have found great advantages in using DriveToWeb over conventional web hosting services. Publishing becomes a simple 3-step process:

- Upload your website folder to Google Drive or OneDrive;
- Share that folder for public access;
- Sign in above and obtain links to your content.

### Google Drive

- Login to your  [Google Drive](https://drive.google.com/) with your credential
- Upload your website folder or create a new folder in your drive, in our case we have created a folder called `myProfile` as shown below

![new folder.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1622110598191/MU6QrjhbiW.png)

- upload all your website files and folder inside the project(`myProfile`) folder.

![gdupload.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1622110576544/hFfz7Zff5.png)

- once the upload is done. we will make this folder public by following these steps:
  - select the folder, right-click and click on the share option.
  - make sure it is set to `Anyone on the Internet can find and view` as shown below.


![gd-public.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1622110937969/vHzyhZYwC.png)


### Microsoft OneDrive

- Login to your  [OneDrive Account](https://onedrive.live.com/) with your Microsoft account.

- Upload your website folder or create a new folder in your drive, in our case we have created a folder called `myProfile` as shown below

![odrive.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1622111884621/rPRHWkVTo.png)

- upload all your website files and folder inside the project(`myProfile`) folder.

![upload.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1622111923747/UbDA1o-82.png)

- once the upload is done. we will make this folder public by following these steps:
  - select the folder, right-click and click on the share option.
  - make sure it is set to `Anyone with the link can view` as shown below.

![share.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1622112124905/vclJ81jgl.png)


### Getting the public URL

**Now let's go to [DriveToWeb ](https://drv.tw) and select `Host on Google drive` option if you have uploaded your website on google drive and select `Host On Microsoft OneDrive` if you have uploaded on OneDrive.**


![drtw.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1622111181936/IksRLrC7k.png)

- It will ask you to log in to `Google Drive` or `OneDrive` depending on the option that you have selected earlier.
- Then it will ask for some permissions to access your public files, allow all the required permissions. 

- once you allowed all the permission it will redirect you to its landing page with the public URL of your website.


![drtw-webpage.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1622111450004/LYgAtv-Bz.png)

- You will find a long URL on the page under the `Your web pages` section.
- We need to shorten this URL using any of the URL-shortening websites like  [Tiny URL](https://tinyurl.com/), [Bitly](https://bitly.com/), etc. we are shortening it so that we don't have to remember the whole URL. These websites also provide alias features so that we can add an alias to remember the website.

- let's go to [Tiny URL](https://tinyurl.com/) and short our URL.

![tinyurl.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1622112737523/8uTOXMDEG.png)

- put the URL and also provide an alias to it.


![tinyurl-create.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1622112799820/IDKll57dY.png)

- let's check if your short URL works or not. Let's put the URL in the browser and check.

![searching-profile.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1622112912460/EohvxxeZS.png)

Once this above URL is hit in the browser it will get redirected to the original long URL (`https://wpcdm4uxgeu0azza8qp0ta-on.drv.tw/myProfile/`) which points to your website.


![hosted.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1622113039573/3DzVgiNA9.png)

**Bingo!!** now your website is live, Now you can share that TinyURL with anyone and they can access it from anywhere and anytime.

So **Why are you holding off?** Go host your portfolios, Resume, designs, etc. and share with everyone without any cost.

## Bonus Points

- Site with the server site scripting doesn't work. because they need a dedicated server to run the backend scripts.
- you can create a blog and host it using [DriveToWeb ](https://drv.tw), check this page  [BLOGGING WITH STATIC GENERATORS](https://docs-of.drv.tw/application/static-blogs/) 
- you can use your custom domain as well. check this page  [USING A CUSTOM DOMAIN NAME](https://docs-of.drv.tw/how-to/using-custom-domain-name/) 
- it also provides [USING A CDN (CONTENT DELIVERY NETWORK)](https://docs-of.drv.tw/how-to/using-cdn/)  option.

Please Subscribe to my newsletter for more interesting articles if you want to get notified whenever I post a new article. You can always give this article a reaction if you like it or learn anything from it.

Chao!! 


