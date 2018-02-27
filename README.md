# Getting Gmail metadata with Talend
This repository contains a simple example of use of GetGoogleToken. The goal is to first execute this job and then execute GetGmailMetadata to get metadata from Gmail.

# Table of contents

  * [Requirements](#requirements)
  * [Installation](#installation)
     * [Create Google Cloud project](#create-google-cloud-project)
     * [Configure GoogleContexts.csv](#configure-googlecontexts.csv)
     * [Configure GoogleContexts.csv location](#configure-googlecontexts.csv-location)
  * [Basic Overview](#basic-overview)
  * [Usage](#usage)

# Requirements
 - [Talend Open Studio for MDM](https://fr.talend.com/products/mdm/mdm-open-studio/)
 - [Google Cloud Platform](https://console.cloud.google.com/)
 - [GetGoogleToken](#) (already imported in this repo)

# Installation
## Create Google Cloud project
Create a Google Project at this url: https://console.cloud.google.com/
Then go to APIs & Services > Credentials and create an OAuth Client ID of type "Other":
![enter image description here](https://lh3.googleusercontent.com/HWRDRWaRjIx92RWhojm1GYSQAe37j4jAAVg76oBBzSi4egv0YRjpZZsvODva0cA5k4rA9bGfHs3bXlmwII_t71BjgspxMqAb9q0L0qApwkKkVFFaUTpchCjkov6ct2RzOQHj5GUJY-KdpGpQ1WR2W0MOuSKpUsEkaxtWZOOtCky8fkGUS5V9CQLM-NyugHw_POa5Ir_4e6xueJWR9YSDR0DrioOtcyUf8Sj7UC_8pA6saoPfBiI-L4SVwPh_G7VcswXvZSi1rrKQxKtYIUU39QSm10wsN-reeE0gEU4gLMljWUCrGZGWoiOggseO9ICqAkuqT3q4ZAb1rPHjjKuDTKWBXm5Hdhc187ec7Hm3kA3sJHlZMl0sWuam2ktnUlIFXMoRCL8I-PtA2OGIRSsTGQSQXAnb-GAnjFkFu0MCqOhGtW0-n2RSAlZyIJ3IFrWaXXr7rPu6RrOxpT3ODtDGYdkD8xfEvcgDpf3N9uWkq_wZXNcfs2FK089ST9EsbIHh32W-b2XokSuHQzFb-8KK0nosv7mhl-JmG38qF2S8iE4hwhCunLxLz8WTa0qkuOTs5Us8CJFFFb8z3WaFk03qOMNrVs9OpnBaQjV7keOm=w382-h285-no)

![enter image description here](https://lh3.googleusercontent.com/nzI5ZYZeXHN4Ow1w94SS-l3Ue3zywrfXxPBvi0Y70X12wEPHmwTkgxEjXHCB0xXpwpfAmFnY7guVUQsSRgxb3wJjIemVvSsCWqiyBbDalyjjwC34Oy46ubJKbEkzUJId8OjEDmIY_yhItER2Wg8srAcpq6VgiQhJVvlWIJnmQK5DYTQvWzauQr0Zw6rm9Oz-JDTnRLONIYqMkf5IyqXS3b-Ra5IWs1Os-IYZX2rD0VXulQwOYPP6h4IsJsHnVeCT0uuZMG-diAy6iZrLlpplk0USqF6yLdVaeb9ukbDFgw9LcOATOuR_w2yGyHvYi-Ip4cr_FOzR8X-DC0UKxyq3TtegT-9iCSMjRM33vXpF7I13FtQhoFNZ98rnsyISqF4rMFQGot-U2szG7eyHTB0hx8M_OgqwG94IKIhMmVrdJq0K-LvhVVbj8QOo84j18QhLgbqtduthJlH2KlO80HHmdzu5xI51V5nwvC_HiDk9Bs_OgYCEtuLZj4oBDyugLDP87QKqSH0nw36OPaxBn4LulbuXiYg17cgz8K3Mh9zhxfVg7589aQlUmPNfs_6pICGteQmx0eeFO2eBeIUsono6NftQgYwTPBod1788Wi0Z=w470-h233-no)

From here Cloud Console will provide you the following :
 - Client ID
 - Client Secret

Go to APIs & Services > Library:
![enter image description here](https://lh3.googleusercontent.com/ku3IQhpwe9KySbsB_CO2a9C96M3TMoSOCn0n5wuhez6QU8Q4L8bLLTkgk3lnAXE1ydAckE6kp-amywr0mV832zIrvsMnsJOdI-L483atXFphXU46PGvfGmZL7yzgNTTHpRgF46oca8YPm42FYsAT1fXDKLczLBGxQiSgax-LJETIwxn0uxBl_lXR6ybcZOZdSvAaC6egz7Q5TWmYP52N4rtW79Y-TYliEekVaCjrWeQfDFw37wWGXMNgOUxD30yDfXr7g6RsgPcD_R-ujnwfXJJrp_7LvYBKZ4NbHCTCPC7b9hwl5eWx8DVqZYs04tUmyOnAxzRYt_MfDGFGkb-MTv5vb05eaC4Q_e2hMQd88lmJ5LJ4YgcYnF_zddcCp2gWd7bopS4diEeYKDiEiLUmZ6zMWOOjWskdhecmj3gIYEljVgC-idBwZWe3G-B44nn1mHLVUUQvM2VON4h4jGbxm6D6-qCA9svICSMIOe1Yw8pW_WyKsN5o0XO_tRCAz_oFzDhf_ZcSiSQtA6-oI4-MzxS78o4vL8lm19hEjSekFFlMm5ETSdn2Yib1d9fYj2XoMQIsVuvaeXDwIKjsCRqsr6KW2ETBkqiNAKyqVcfL=w479-h217-no)
Search for **Gmail** and enable.

## Define GoogleContexts.csv location
Here we need to specify in Talend job where will be located your data and GoogleContexts.

Edit Talend job and in context tab, specify the folder location of GoogleContexts.csv in path context:
![enter image description here](https://lh3.googleusercontent.com/TAOHv5Aul6rnPk5VjE22-mTO-GqwO_xm5h72ENQgoMPS62tHJctmmMcWXA71TmRCJoAn7vhFs-eXBfTLlh2RqZkWZ5fS33RgPUk3Y92jMvw2YRSjOksicRTsp0gJ6fmSGXJGtBGKQk-puvSyaNeuzEY9cdjHnS22fQfdR4Pxo25ndYTz_J9ojGwC2nvAs1ge2vIgK8OWSAzu8zLgTESlLh2lD5o7i0SG0HxJVCPy8KTFKVXse8JdccSnlhqMMT6Ip0Wor1_tsO3ruUuqj-Q8DSonb5GNWNsom6ZexCDpSyYqIhvIJUTV8Gq6K0yU4uHEXkNBSMO7utzZ5vycTnJ1Ss16VI_8_IodC618VB8BSVspDICV75uyuIpScfUjDzboT9OYak3X7CfidXiBpzTgobUA1dQZcxYcmPFZW2h5W0yiIoorsGuSFWasNsB3-Wmfg6dLxd5PkVz3iu-LBolTCkxH2xx65OFAdKsIjNqlPZCC7QUr8hhL6UVkKO8qKKEjop5oPel66lNDw5xG_-SD1qRmBiNuZ6YctnHHE5Xn6SJSC20YxEzigF3bGkvRXeN8dfdWppRYWX2YufN_ZTl1G50aMuGPHbtd30VXhmjH=w1048-h298-no)

In this example the location of GoogleContexts.csv file is located in the following folder: C:\talend\

## Configure GoogleContexts.csv
Once Google cloud project created and API enabled, edit the file GoogleContexts.csv and fill with the right credentials:

    client_id;YOUR_CLIENT_ID
    client_secret;YOUR_SECRET_ID
    scope;YOUR_SCOPES
    email;YOUR_ADDRESS_EMAIL

Replace **YOUR_CLIENT_ID** and **YOUR_SECRET_ID** with those you created on [Create Google Cloud project](#create-google-cloud-project) section.

You need to know the scope required for your project. Here we need to get metadata from Gmail. The one below is enought:

    https://www.googleapis.com/auth/gmail.metadata

This is how it looks like when configured:

    client_id;YOUR_CLIENT_ID
    client_secret;YOUR_SECRET_ID
    scope;https://www.googleapis.com/auth/gmail.metadata
	email;mypersonal@gmail.com

# Basic Overview
![enter image description here](https://lh3.googleusercontent.com/1avbaLWPglNldSGteLhz66IEnDBU-KOY9yhEYklAOSQwOQa0ZgtuJIBnCnfux0GRSn56RGiRscRe7Vz4tL8piluwyM-dV1wSUlz3D9-qq9O-Jbyc27Ct57t5Fr473kn_3UKdLe9FcWFGAg2aiOtS0UAaPLj1j2hq6x9Q6hzy0mor4JjAQFC7pYD2nD6foJ-GUWwY3RFO32WbPyBossan0Ttz5Di1Xlml23mQEcqtYj4Bx7WVQMmv37Y-Gbw5gpdqxRv0iyjJpCF5-Pnf6Vf-jlHLYJ2Hjuyl9m5KWLdTQtl5NwnmtvJmx1FgT4CJZvN_3QehHmP0dj_AkgIZakqembgqaUXJ2E1gnXvo7yFJHLnU5rGTnojdMIzReq8npVrgprZfQKlQG-Wf5Och6rv1aYx_HfRxjUn7OZpkd2CAcb3AE7_G2dXZFhe13reAi87zepITRHKfQrspGLMWVV8vel7TJ0Yl5jU4cmZUnjuCQGf5ymBQiEo7KmLkF6nWN9SoE44PCg35DYDNm5LNpo4O1PgXrwC4d0z4KpMZVpaB8nvKUREOGReU9UDeRl7yrDBEV7QMxJWp4GF5OTjYjNgdzLT4mbYub6ZNrshrBQlU=w766-h216-no)

tRunjob is the first executed component and is running our main job called **GetGoogleToken** and then is making sure GoogleContexts.csv is well updated.

We load GoogleContexts.csv as context with tContextLoad component to extract access_token and re use it as a context in next steps.

Use tRestClient component and call for this endpoint URL: `"https://www.googleapis.com/gmail/v1/users/"+context.email+"/profile"`
The variable context.email is recovered in GoogleContexts that you defined in [Configure GoogleContexts.csv](#configure-googlecontexts.csv) section.

In advanced settings of tRestClient add in HTTP headers the following:
*"Authorization"* as **Name** and *"Bearer " + context.access_token* as **Value**:
![enter image description here](https://lh3.googleusercontent.com/GZ3mA65eYIKOkc4-RrQtNb6zPzq8YYLgliiZngRxYX-n_oDFOpc6sYCRf1AAZWcmKHZGZsyy5gsJbo-yXi-_BW9qYqf1Y-zlDrqYkku6ECELcjEd_VuaHg5mru7IatwaXK55oodK6FF0l-hd1Wyy2kAfUMmiHEvSmpucP7q2Uzgje6U5jprQto8oGwtcm7laMsGhO4ALNCVOTIux07x6BqXwaHgxv_QKyiBCjs0pxlG3HVxhnOTKSMYsHzvgevZwWuubZlMBuxQE9NZUscGXg59gbm3a6ClacswFEakcQgrxLvYreU5atzu7Bb2Cgl94OoOM5TOTS9_dGZBLWPyyqGjXXJWzV1TuIVvc0xscEGw_Z31XVnfEtjsoWzFqNHm8aEFqfkVhn7B08QC5f4V7fhRi632qDZlrGTzUNogCmkTZNFtREie4at8yBvtSiC4U_KXaEeOnyZ9calcJ7tN3rmYYrInYmrys8LcWw6Eekaa6FuLJonV9Ql-17HLPy6bDq1BGlkSLTZHo2S4tjsh6Cm7Jv4QNmOqMwGsXoEvQxV0_YNlO4DSyuXwGBMF5snPr2vfEgOKTh-FJpoEidmXR5kkt4UKmo7k2_UEqMxju=w1072-h124-no)

# Usage

When executed the first time, access_token is not yet retrieved. Therefore you have to authorize your application requesting Gmail:
You will receive for the first time a message saying the following:

    [statistics] connecting to socket on port 4047
    [statistics] connected
    Refresh token and access token not found.
    https://accounts.google.com/o/oauth2/auth?scope=https://www.googleapis.com/auth/gmail.metadata&state=123456789qwertyui&redirect_uri=urn:ietf:wg:oauth:2.0:oob&response_type=code&client_id=441071126182-kg470tgvp2vr14jk259of6ap0lkh728s.apps.googleusercontent.com&approval_prompt=auto&include_granted_scopes=true&access_type=offline

URL has been generated according to your client id and scopes you defined. The process is the following:
 - Copy paste URL on a browser and get authorization 
 - Copy paste authorization code and put in Talend in message box :
![enter image description here](https://lh3.googleusercontent.com/Qk3B8Da3L_zdRDUbH428G60627iY-cFAwp_g5h308aTLeu37K0BTQa5jBjSZIAeQIUXX4byfelEhH6OBREcwgd7xZzmLLCNlCW3esYk_r3TUViuBVpNMVrNSpJfulNDxkI0GGt9JAobZ9xJPz1vQJDtl7S4Fq3Ion6y4vueBZG4-rbhprr85TaLB0c_DRhkSaeSoJTVFkhGb7WxNyj42ZFZROTKQ3q744g0M1Zg51tjOHyIOqkWeKw5ah5X4pmoOWeAMJ5UZEPSX_sNUkTDfHMvltrTza1UDk0K310ZJZHPjjqtG9VYSJ9ke066qvXaeniV-SGTD8VveoNo8FJ3Rr5cYej_HNFwtAbEX_Zg3nptYmeWppdKtWU2DlEILb_CeY2YQKNBNGysSURJLNC2PPHBgsZYvTMFeOSoUv9Dh1Axf2jfYAScEwJqE2svqXisJvcysOePAkjbC_ajflBgmJvTSw--CbYOFPK4hAajlQfG4uvQKVgwlg-IlzsEy3SVpFN5bMcjGUBgZ2YcfPCeQrKJMORLH1c7RKRFFMjxSFZZaQcbqiaVr-7miNIknR2ggoh2E8dtGpZSyz9dSVkRJSTVrbjiU8DPvZzg6obII=w526-h120-no)

When clicked on Ok, access_token is generated. This step must be done only the first time.

The goal was to create a simple job using  **GetGoogleToken** to request Gmail API and retrieve the following data:
 Property name	 | Value | Description 
------------- | ------------- | -------------
 emailAddress | string | The user's email address.	
 messagesTotal | integer | The total number of messages in the mailbox.	
 threadsTotal | integer	 | The total number of threads in the mailbox.	
 historyId | unsigned long | The ID of the mailbox's current history record.

Execute your job and you will have as a result metadata of your Gmail account:

    [statistics] connecting to socket on port 4026
    [statistics] connected
    Access token ready
    The total number of messages in the mailbox: 73852
    The total number of threads in the mailbox: 42640
    [statistics] disconnected

Talend sucessfully requested GMail API and extracted metadata.
