
## Viva project ##

In this document I will focus on the following features:

**Business requirements**
* 1. Videos working inside and outside china
* 2. add Cuepoints (add timestamp to video)
* 3. Show Cuepoints in the frontend
* 4. Collect user data such as:
        * First name
        * Last name
        * Mobile Number
        * Email
        * Wechat ID
        * ID Card (file - image / document format)
        * Project (file - document format)
* 5. Easy way to generate frontend with the data
* 6. Easy way to modify / update users profile with video interview
* 7. generate link to go directly to user's profile.


### 1. Videos working inside and outside china ###

There are several alternatives to this. I did a research to understand what's the best way to do it and I found the following:

**Dacast**

Dacast can be used as a **Video on demand** platform where we can upload all the videos related to the interviews. They offer their services in [china](https://www.dacast.com/video-hosting-china/).

**BrightCove**
[BrightCove](https://www.brightcove.com/en/) offer a video cloud solution but is not working well in china.


**Youku**
[Youku](https://www.youku.com) is a video hosting service based in China. We can upload the videos to Youku but we need to verify that we're the authors of the videos. Also, it's working well in China and outside china (but it's slow outside china). Also we need to check how we can disable all the advertising.

**AWS S3 solution**

Other possible solution is to pay an AWS S3 bucket inside china and outside china and use geoDNS to redirect traffict based on user's location (cost approximately 400 - 700 rmb per month).

### 2. Add Cuepoints (add timestamp to video) & 3. Show Cuepoints in the frontend ###

I couldn't find a video hosting service that can, at the same time:
    * working well inside and outside china
    * CuePoints feature
    * easy way to show CuePoints in the frontend

what I would recommend is to use something working well inside and outside china (perhaps Dacast in the beginning when in the meantime we work in develop a solution with aws s3 buckets and geodns) and develop a script to add the CuePoints, save that in a database (if we're using wordpress as CMS we're already using MySQL as a database, so we can save all the CuePoints related to a specific video there) and then display it in the frontend.

### 4. Collect user data. 5. Easy way to generate frontend with the data. 6. Easy way to modify / update users profile with video interview.

This can be easily implemented and I already did a proof of concept of this. The user flow will be in this way:


**First: user need to schedule the interview**
![alt text](https://raw.githubusercontent.com/lautaro450/viva-images/master/landing-page.png "landing page")

**2. We can collect the user data in the first step of the form**
![alt text](https://raw.githubusercontent.com/lautaro450/viva-images/master/user-data.png "user data collection") 


**After the user finished their registration process, a new page will be created with the form information. The only thing the interviewer need to do here is to add the video related to the interview**
![alt text](https://raw.githubusercontent.com/lautaro450/viva-images/master/modify-profile.png "user profile")
