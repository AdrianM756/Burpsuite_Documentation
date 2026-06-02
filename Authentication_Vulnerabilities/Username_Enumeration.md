## Username Enumeration

Username enumeration happens when a website accidentally drops clues that let an attacker figure out if a specific username exists.

Instead of guessing blindly, the attacker just watches how the website behaves. This usually happens in two places:

<b>The Login Page:</b> The site gives different error messages (e.g., "This user does not exist" vs. "Incorrect password").

<b>The Signup Page:</b> The site says "Username already taken."

<b>Why it's dangerous:</b> Once an attacker knows which usernames are real, they can stop guessing names and focus 100% of their energy on guessing the passwords for those specific accounts. This makes hacking the system much faster and easier.
<br>
<br>

## Demo

On this demo, we will to perform user enumeration and bruteforce attack to one of the labs available in portswigger academy.

With Burp running, we will investigate the login page and submit an invalid username and password. In Burp Suite, go to ```Proxy``` > ``HTTP history`` and find the ``POST /login`` request. Highlight the value of the ```username``` parameter in the request. 

<img width="463" height="32" alt="image" src="https://github.com/user-attachments/assets/bd4d5d70-f761-47b6-8aa2-4601623da378" />
<br>
<br>

Send it to ```Intruder```. In Burp Intruder, notice that the ``username`` parameter is automatically set as a payload position. This position is indicated by two ``§`` symbols, for example: ``username=§invalid-username§``. Leave the password as any static value for now.

<img width="278" height="31" alt="image" src="https://github.com/user-attachments/assets/89bf538a-b909-43da-a94a-d0d212146fd6" />
<br>
<br>

We will then go to Payloads. for the payload type, we will select ```simple list```.

<img width="512" height="161" alt="image" src="https://github.com/user-attachments/assets/6c5d1ea4-4c42-4cb5-8747-f01bb44c3cbe" />
<br>
<br>

On the Payload configuration, we will paste the name on the [Candidate usernames](https://portswigger.net/web-security/authentication/auth-lab-usernames) list that is available.

<img width="509" height="250" alt="image" src="https://github.com/user-attachments/assets/af814c54-1352-4c7d-aa20-5e159f4eaaaf" />
<br>
<br>

Once done, We will then click ```Start attack```.

<img width="1031" height="115" alt="image" src="https://github.com/user-attachments/assets/ccb559aa-a45e-485a-b104-b2d5846ee505" />
<br>
<br>

When the attack is finished, examine the Length column in the results table. You can click on the column header to sort the results. Notice that one of the entries is longer than the others. Compare the response to this payload with the other responses. Notice that other responses contain the message ```Invalid username```, but this response says ```Incorrect password```.

<img width="1299" height="706" alt="image" src="https://github.com/user-attachments/assets/b777f4dd-b946-4060-bbaf-bcb51cf92ab2" />
<br>
<br>

Close the attack and go back to the Intruder tab. Click ``Clear §``, then change the ``username`` parameter to the username you just identified. Add a payload position to the ```password``` parameter. The result should look something like this:

<img width="276" height="31" alt="image" src="https://github.com/user-attachments/assets/c04aac99-4d0b-4178-a9af-9a66dee97a09" />
<br>
<br>

We will then go to Payloads. for the payload type, we will select ```simple list```.

<img width="512" height="161" alt="image" src="https://github.com/user-attachments/assets/6c5d1ea4-4c42-4cb5-8747-f01bb44c3cbe" />
<br>
<br>



On the Payload configuration, we will paste the name on the [Candidate passwords](https://portswigger.net/web-security/authentication/auth-lab-passwords) list that is available.

<img width="509" height="270" alt="image" src="https://github.com/user-attachments/assets/19bff9ed-35b8-4b9e-9e2f-831bbe20febb" />
<br>
<br>

For the password, we will be checking the status code because of we do have a valid username and password, it should redirect us to the account/dashboard page in which we should find the status code ```302```. As you can see, we are able to find the password for the username ```adsl```.

<img width="1266" height="771" alt="image" src="https://github.com/user-attachments/assets/f98d031d-f09e-43ef-938f-738d2b3dc0a0" />
<br>
<br>

If we try to login, we can see that we are able to login using the username and password that we've just obtained.

<img width="403" height="149" alt="image" src="https://github.com/user-attachments/assets/2e747d81-35ab-426c-b5a7-2179e900a9fc" />
<br>
<br>





