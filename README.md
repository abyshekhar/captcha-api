This is a RESTFul nodejs API for generating and validating a simple captcha. This could be used in the projects where the functionality is needed.

The initial code has been taken from the blog post here - https://healeycodes.com/lets-generate-captchas

There are 2 endpoints 

1. GET https://captcha-api-6152.onrender.com/captcha
2. POST https://captcha-api-6152.onrender.com/captcha

Functionality of the captcha generation code sends the captcha image along with the hash of the captcha text. 

This is done for security reasons so that the captcha is not passed in plain text.

The validation API requires the captch and the original hash to be passed in the request body in json format.

Captcha Generation
Sample Request for with default width and height of the captcha image is 
GET https://captcha-api-6152.onrender.com/captcha

The captcha image with the desired width and height could be requested with the below mentioned URI - 
GET https://captcha-api-6152.onrender.com/captcha/:width?/:height?/

Captcha Verification
Sample Request - 
```
{
    "captcha":"787HoS",
    "hash":"$2b$10$Ic.diQtHeXDQ7ldBo2I2O.u.qbJ96QzIcMggL3cwfs3dB7su.SCR2"
}
```
Sample Responses
Valid Captcha
```
{
    "message": "Verification successful"
}
```
Invalid Captcha
```
{
    "message": "Invalid captcha"
}
```

