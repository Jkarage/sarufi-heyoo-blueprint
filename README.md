<samp>

# sarufi-heyoo-blueprint

Starter code to integrating sarufi with [heyoo](https://github.com/Neurotech-HQ/heyoo).

A blueprint for deploying sarufi chabot on WhatsApp Cloud API. In this blueprint, we shall set up a webhook to receive whatsapp messages. The are several ways you can set up a webhook. I will be showing how to use [ngrok](#using-ngrok) and [Replit](#using-replit).


## USING NGROK

Make sure you have [ngrok](https://ngrok.com/) installed in your working machine.

### Quick setup

Have [sarufi package](https://github.com/Neurotech-HQ/sarufi-python-sdk) installed on your machine before launching your whatsapp bot.
- Lets Make a project folder named `whatsapp-bot` then create virtual evironment `whatsapp-bot-env` to hold our package. 

  Run the command to make the magic happen

  ```bash
  mkdir whatsapp-bot
  python -m venv whatsapp-bot-env
  cd whatsapp-bot
  source  whatsapp-bot-env/bin/activate
  pip3 install --upgrade sarufi
  ```

- Create a file named '.env` in your working folder to hold environment variables by running. 
  
  ```
  cd ..
  touch .env
  ```
   In the file add the following. Read on how to [get whatsapp creds](#whatsapp-cloud-creds)

   ```bash
    sarufi_username = Your sarufi username
    sarufi_password = Your sarufi password
    sarufi_bot_id   = Your Bot Id
    whatsapp_token  = Your Whatsapp token
    phone_number_id = whatsapp phone number id
  ```
  
- Once you have environment variables set, you are ready to fire 🚀 your `app.py` in activated virtual envirnoment.
  ```bash
  python3 app.py
  ```
  Then run the command below to start ngrok

  ```bash
  ./ngrok http 5000
  ```

  **`Note:`** keep the port number the same as used in `app.py`

- Finish up. After ruuning the command, you will have to copy the url ngrok provides. The url looks like `https://xxxxxxxxxxx.ngrok.io`

  With the provided url, follow simple steps at [Setting whatsapp webhook](#setting-whatsapp-webhook).

  Open `app.py`, copy the `VERIFY_TOKEN`--> paste into verify token in your whatsapp cloud --> **verify and save**.

  We are heading a the best part of this journey. Just take time to [subscribe to message topic](#webhook-field-subscription).
  When done ,you are good to go... fire up your bot in whatsapp by sending text.

  🏁 When done with saving the token and url, go on to text your bot.



## USING REPLIT

- Log into your [Replit](https://replit.com/) account.
  
  Create a python repl. Download `main.py` from [Whatsapp bot using sarufi API and heyoo](https://replit.com/@jovyinny/Whatapp-bot-using-Sarufi-api-and-heyoo).

  Upload/copy `main.py` code into your replit repl created.  In your repl, navigate to Tools --> packages, then install `heyoo`.

  Navigate to Tools--> Secrets to create environment variables. Read [Getting whatsapp creds](#whatsapp-cloud-creds).

  Create
    |Secrete key               | Description|
    |:---                      |:---        |
    |`phone_number_id`         | Whatsapp cloud phone ID|
    |`whatsapp_token`          | Your whatsapp token|
    |`sarufi_username`         | Your sarufi username|
    |`sarufi_password`         | sarufi password|
    |`sarufi_bot_id`           | Your sarufi bot id|

- Run the script
  
  After creating the secret keys, run your `main.py`. A small webview window will open up with a url that looks like `https://{your repl name}.{your replit usermae}.repl.co`. 

  With the url, follow simple steps at [Setting whatsapp webhook](#setting-whatsapp-webhook).

- Final touches

  Go into your repl, copy the `VERIFY_TOKEN` --> paste into verify token in your whatsapp cloud --> **verify and save**.

  We are reaching at a good point with the set-up. Lets [subscribe to message topic](#webhook-field-subscription).
  When done ,you are good to go... fire 🚀 up your bot in whatsapp by sending text.

## Whatsapp cloud creds

Navigate to `Whatsapp`-->`Getting started` to get whatsApp cloud `token` and `phone number ID` to be used. 

You will have access token and phone number id.

![How to get whatsapp token and phone number ID](./img/get_whatsapp_token.png)

## Setting whatsapp webhook
Navigate to your whatsapp cloud account --> `configuration` --> edit --> then paste the url into callback url.
  
![Web hook setup](./img/webhook_setup.png)

## Webhook field subscription

After veryfing and saving whatsapp webook, navigate to webhook fields --> click `manage` to subscribe to `message` topic.

![Webhook fields subscription](./img/webhook_subscription.png)

## Issues

If you will face any issue, please raise one so as we can fix it as soon as possible

## Contribution

If there is something you would like to contribute, from typos to code to documentation, feel free to do so, `JUST FORK IT`.

## Credits

All the credits to

1. [kalebu](https://github.com/Kalebu/)
2. [Jovine](https://github.com/jovyinny/)
3. All other contributors

</samp>
