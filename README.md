# birthday-bingo
Play a game of Birthday Bingo!

The player will see a list of friends participating on the left of a bingo board populated with any of our [current offerings](#Current-offerings). Pretty simple, they have to guess the name of the friend that put the clue in the bingo tile by clicking on the dice symbol or a picture if present. On a successful bingo you can configure a remote prize! (Eg: A video/link/message/both/all) - if they guess the entire board right, they unlock the final [prize](#Configuring-the-prize).

Made especially for those honouring the stay home stay safe policy! Share your screen with your friends and have fun with this little game of Birthday Bingo (: 

## Current offerings

Select what kind of bingo you want or mix and match! Current offerings are: 
1. Song Bingo -> `song` <br/>
    Friends will choose songs for the player to guess. The bingo tile will have the name of the song, its artist, and a quote from the song. Click on the dice symbol in the tile to guess the name of the person who chose this song! The player will also be able to click a play button to play this song via youtube if they need a refresher! <br/>
    eg: birthday-bingo.azurewebsites.net<br/>
2. Quote Bingo -> `quote`<br/>
    Friends will choose quotes for the player to guess. The bingo tile will consist of the quote - and the player will click on the dice symbol in the tile to guess the name of the person who put in the quote for them.  <br/>
    eg: quote-bingo.azurewebsites.net<br/>
3. Photo Bingo -> `photo`<br/>
    Friends will choose photos of themselves with the player, and also save a version in which they have cropped themselves out. Pretty simple, the player can share their screen and guess the person who was in that picture with them, and click on the picture to enter their guess. <br/>
    eg: photo-bingo.azurewebsites.net<br/>

## Front page setup

If you would like to add pictures on the front page: <br/>
1. Add their location to [this](data/index.txt) file <br/>
```json
{
    "url": "data/index/name-of-photo.jpg"
}
```
2. Add the pictures in [this](data/index) location in the repo

## Configure your bingo!

1. Locate the file [bingo.txt](data/bingo.txt) and the [images folder](data/images) as this is where you will be putting most of your data

2. Each bingo tile can contain any of the current offerings Collect a json array of data from friends and family with the following recommended fields: <br/> 
Each bingo tile may contain any of the three [current offerings](#Current-offerings) - <br/>

a. For a `song`
```json
{
    "id": 123,
    "type": "song",
    "friend": "name-of-person-choosing-song",
    "song": "name-of-song",
    "artist": "songs-artist",
    "quote": "a-quote-from-the-song",
    "link": "youtube-hash"
}
```
    
b. For a `quote`
```json
{
    "id": 123,
    "type": "quote",
    "friend": "name-of-person-providing-quote",
    "quote": "quote-goes-here"
}
```

c. For a `photo`...
```json
{
    "id": 123,
    "type": "photo",
    "friend": "name-of-friend-in-photo",
    "photo_cropped": "data/images/name-of-friend-in-photo_cropped.jpg",
    "photo_full": "data/images/name-of-friend-in-photo_full.jpeg"
}
 ```
3. Populate [this](data/bingo.txt) file <br/>
    a. put the json array under `data1` <br/>
    b. the number of columns in the bingo grid under `N1` <br/>
    c. the number of rows in the bingo grid under `M1` <br/>
    d. put the number of wrong guesses you would like to allow before the person is asked if they want to give up under `wrong_guess_max1`<br/>
    e. OPTIONAL: If you would like to change the theme of the website, tackle [this](data/songs.css) file.<br/>
    f. OPTIONAL: If you are interested, you can also change values in the self explanatory fields `wrong_guess_color`, `correct_guess_color`, `specific_instructions1`

4. If you have any pictures for photo bingo, put them in the [images folder](data/images) and verify that the image name exactly matches the one you put in the json in step 2

5. [Configure a prize!](#Configuring-the-prize)

6. Upload this code to a web app server (we chose [Microsoft Azure](https://portal.azure.com))

7. BINGO! Send your website link to the birthday boy/girl and get on a video call, ask them to share their screen, and play this game of bingo!

## Configuring the prize

Your prize can be a youtube video, and/or a google drive video or picture, and/or a simple link to another webpage, and/or an image used from any online website (Be cautious of copyright issues). It can be one or two or all of them. Exactly how to configure this is described below. If you have any trouble with image dimensions, change the width and height allowance in [this](prize.html) file.

1. Youtube links<br/>
a. Navigate to the video you want to embed as a prize. Eg: Link = https://www.youtube.com/watch?v=_A70SfWAO18<br/>
b. Copy the part of the link that comes after `v=` (`_A70SfWAO18` in this case)<br/>
c. Put it in [this](data/prize.txt) file in the `youtube_video_hash` variable (enclosed in quotes)

2. Google drive video/picture<br/>
a. Navigate to the video/picture you want to embed as a prize. Open it in a new window. You will see a link eg: https://drive.google.com/file/d/1J_sO-qjA4_42r_aDT-F1EAebZiSSo98u/view <br/>
b. Copy the part of the link that comes between `/d/` and `/view` (`1J_sO-qjA4_42r_aDT-F1EAebZiSSo98u` in this case)<br/>
c. Put it in [this](data/prize.txt) file in the `google_drive_media_hash` variable (enclosed in quotes)

3. Simple link to another website<br/>
a. Put the link in [this](data/prize.txt) file in the `hyperlink` variable (enclosed in quotes)<br/>
b. Put the text you want the link to appear as in [the same](data/prize.txt) file in the `hyperlink_text` variable (enclosed in quotes)<br/>

3. Simple image from another website<br/>
a. Put the link in [this](data/prize.txt) file in the `google_image_link` variable (enclosed in quotes)<br/>

## Owner
Saloni Goel, 2020

## Credits
Abhinav Nair and Shivom Thakkar, 2020

## References:
1. https://gist.github.com/wernsey/faaed0e409efb236642aa621f9e4e623
2. https://www.w3schools.com/
3. https://color.adobe.com/create/color-wheel
4. https://fonts.google.com/ 
5. https://fontawesome.com/