# Fake Windows Login

(BETA - In Development)


# 2021 Update. I should preface this by saying please do not try to steal peoples credentials. Its probably illegal where you live and I do not condone it. This was made purely as an experiment trying to make a webpage look like a windows 7 lockscreen and to test my abilities at web development. Lets just say i was bad at it and move on. This repo is kept here as an archive but will never be updated in the future. Seriously don't steal peoples login info. Don't. Do. It. Period.


For Windows instalations using a custom login background please navigate to the following local file path:
- `C:\\Windows\System 32\oobe\Info\Backgrounds`
Then upload the image named `BackgroundDefault.jpeg` to your root directory path.
Then rename to `bg.png`

For Windows instilations connected to a network domain please modify the folowing line:
- /index.xhtml:
-	154: `<p class="domain"> Domain: ________</p>`

If you are not connected to a domain please remove the following lines:
- /index.xhtml:
-    154: `<p class="domain"> Domain: _______</p>`
-    155: `<p class="domainlog"> How do I log in to another domain?</p>`

For windows instalations where the red shutdown button is not displayed, comment the following lines:
- /index.xhtml:
-	172: `<img src="/shutdown.png"  draggable="false" ondragstart="return false;" />`


For windows instalations with profile pictures please do the following:
- navigate to control pannel --> User Accounts and Family Safty --> User Accounts
- Take a screen shot of that user picture and remove all whitespace and add a transparent background.
- Then upload that image to your root directory and name it `profile.png`

To use HTTP POST change the following line to add your POST action:
- /index.xhtml:
-	156: `<form id="info" method="post" action="________________________">`

If you do not want HTTP POST then delete the following lines:
- /index.xhtml:
-	156: `<form id="info" method="post" action="________________________">`
-	160:     `</form>`

To start from Bash:

- `$ /etc/init.d/apache2 start`

To deploy on Heroku:
- Set buildpack to php.
- DO NOT modify the following files unless you know what you are doing:
-    `/index.php`
-    `/composer.json`

For liscense see:
- `/liscense.txt`

Origional Authors:
- Nate Goldsborough     
- Seth Traman
