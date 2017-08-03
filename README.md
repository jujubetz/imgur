## About
  This bash script was made to take screenshots from raspberry pi and upload to imgur album (with auth)
  
  
## Setup
  ##### First install necessary packages:
  
    sudo apt-get update
    sudo apt-get install -y curl xclip xsel scrot
  
  ##### Clone or copy the imgur file to your /bin directory
  https://github.com/jujubetz/misc/blob/master/imgur

  ##### Change permissions
  
    sudo chmod +x /bin/imgur
    
  ##### Create an account at imgur
  https://imgur.com/
  
  ##### Create an Application
  https://api.imgur.com/oauth2/addclient
 
  Select the option "OAuth 2 authorization without a callback URL" 
  
  ##### Get your client_id and client_secret.
  
  ##### Get your PIN
  https://api.imgur.com/oauth2/authorize?client_id=YOUR_CLIENT_ID_HERE&response_type=pin

  Authorize the application and copy your PIN
  
  ##### Get your access_token: Change with your information and paste in your terminal.
    curl -X POST -F "client_id=CLIENT_ID" \
                 -F "client_secret=CLIENT_SECRET" \
                 -F "pin=PIN" \
                 -F "grant_type=pin" https://api.imgur.com/oauth2/token
  
  ##### You will get a response with your access_token and more general information.
  
  ##### Create an album at Imgur and copy the ID
  https://imgur.com/a/IDHERE
  
  ##### Edit the script with your information
  
  ##### sudo nano /bin/imgur
  
  client_id=CLIENT_ID
  
  access_token=ACCESS_TOKEN
  
  album_id=ALBUM_ID
  
  ## Usage
  
  ##### By default this very simple script will take a screenshot using scrot and will store that at ~/home/pi/imagem.jpg
  you can change the image name and the path if you want to. You can see the scrot options typing scrot --help 
  in your terminal.
  
  ##### The usage is simple, type in your terminal:
    imgur /path/to/image
    
   
  
  
  
