## Bypassing two-factor authentication

Sometimes, a website's 2FA setup is so poorly built that you can skip it completely.

This usually happens when the login process is split into two separate steps:

1. You enter your password on page one.

2. You enter your verification code on page two.

Because of this split, the website often secretly considers you "logged in" the moment you pass step one.

<b>The Flaw:</b> If you skip page two entirely and type the URL of a private dashboard straight into your browser, a flawed website will let you right in. It completely forgets to check if you ever actually entered that security code.
<br>
<br>

## Demo

On this demo, we will try to bypass 2 factor authentication using the labs available on portswigger academy.

Log in to your own account. Your 2FA verification code will be sent to you by email. Click the ```Email client``` button to access your emails.

<img width="780" height="134" alt="image" src="https://github.com/user-attachments/assets/d51213b4-1bb7-43ed-9008-54d0442f6724" />
<br>

<img width="1232" height="413" alt="image" src="https://github.com/user-attachments/assets/0e25f663-b028-447f-875a-49d22f0b746c" />
<br>
<br>

Go to your account page and make a note of the URL.

<img width="956" height="631" alt="image" src="https://github.com/user-attachments/assets/deb8829c-3049-4545-9802-d63a54156ead" />
<br>
<br>

Log out of your account then log in using the victim's credentials.

<img width="798" height="501" alt="image" src="https://github.com/user-attachments/assets/e6a71b45-7989-4593-bb0f-c6d5f8c8b561" />
<br>
<br>

When prompted for the verification code, manually change the URL to navigate to ```/my-account```

<img width="651" height="50" alt="image" src="https://github.com/user-attachments/assets/297d1581-8453-4ea4-97b3-8ded32604c8b" />
<br>

<img width="525" height="145" alt="image" src="https://github.com/user-attachments/assets/f5bb5671-2379-42dc-9d28-d05f4eef11b8" />













