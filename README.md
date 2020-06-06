# birthday-bingo
Play a game of Birthday Bingo! 

## Select your bingo

Select what kind of bingo you want! Current offerings are: (descriptions are in this document, to help you choose)
1. [Song Bingo](#Song-Bingo) -> `song`
2. [Quote Bingo](#Quote-Bingo) -> `quote`
3. [Photo Bingo](#Photo-Bingo) -> `photo`

Steps to really select it: 
1. Navigate to this section of your `index.html`, `bingo.html`, and `prize.html` one at a time.
```html
    <!-- include data -->
    <script src="data/songs.txt"></script>
```
2. Replace the `songs.txt` file with the name of the file matching your bingo selection. Eg: Quote Bingo has `quotes.txt`

3. Save all three files!

## Song Bingo
Friends will choose songs for the birthday boy/girl to guess. The birthday boy/girl can share their screen and guess the person who chose the song for them, and unlock the final [prize](#Configuring-the-prize) once they BINGO!<br/>
eg: birthday-bingo.azurewebsites.net

### Steps to configure:

1. Make sure you have selected the right bingo by following [this](#Select-your-bingo)

2. Collect a json array of data from friends and family with the following recommended fields: 

```json
{
    "friend": "name-of-person-choosing-song",
    "song": "name-of-song",
    "artist": "songs-artist",
    "quote": "a-quote-from-the-song",
    "link": "youtube-hash"
}
```

3. Populate [this](data/songs.txt) file <br/>
    a. put the json array under `data1` <br/>
    b. the number of columns in the bingo grid under `N1` <br/>
    c. the number of rows in the bingo grid under `M1` <br/>
    d. put the number of wrong guesses you would like to allow before the person is asked if they want to give up under `wrong_guess_max1`<br/>
    e. OPTIONAL: If you would like to change the theme of the website, tackle [this](data/songs.css) file.
    f. OPTIONAL: If you are interested, you can also change values in the self explanatory fields `wrong_guess_color`, `correct_guess_color`, `specific_instructions1`

4. [Configure a prize!](#Configuring-the-prize)

5. Upload this code to a web app server (we chose [Microsoft Azure](https://portal.azure.com))

6. BINGO! Send your website link to the birthday boy/girl and get on a video call, ask them to share their screen, and play this game of bingo!

## Quote Bingo
Friends will choose quotes for the birthday boy/girl to guess. The birthday boy/girl can share their screen and guess the person who chose the quote for them, and unlock the final [prize](#Configuring-the-prize) once they BINGO!<br/>
eg: quote-bingo.azurewebsites.net

### Steps to configure:

1. Make sure you have selected the right bingo by following [this](#Select-your-bingo)

2. Collect a json array of data from friends and family with the following recommended fields: 

```json
{
    "friend": "Nair",
    "quote": "\"Long walks can mend anything\""
}
```

3. Populate [this](data/quotes.txt) file <br/>
    a. put the json array under `data1` <br/>
    b. the number of columns in the bingo grid under `N1` <br/>
    c. the number of rows in the bingo grid under `M1` <br/>
    d. put the number of wrong guesses you would like to allow before the person is asked if they want to give up under `wrong_guess_max1`<br/>
    e. OPTIONAL: If you would like to change the theme of the website, tackle [this](data/quotes.css) file.
    f. OPTIONAL: If you are interested, you can also change values in the self explanatory fields `wrong_guess_color`, `correct_guess_color`, `specific_instructions1`

4. [Configure a prize!](#Configuring-the-prize)

5. Upload this code to a web app server (we chose [Microsoft Azure](https://portal.azure.com))

6. BINGO! Send your website link to the birthday boy/girl and get on a video call, ask them to share their screen, and play this game of bingo!

## Photo Bingo
Friends will choose photos of themselves with the birthday boy/girl, and also save a version in which they have cropped themselves out. Pretty simple, the birthday boy/girl can share their screen and guess the person who was in that picture with them, and unlock the final [prize](#Configuring-the-prize) once they BINGO!<br/>
eg: photo-bingo.azurewebsites.net

### Steps to configure:

1. Make sure you have selected the right bingo by following [this](#Select-your-bingo)

2. Collect a json array of data from friends and family with the following recommended fields: 

```json
{
    "friend": "Isha",
    "photo_cropped": "data/images/Isha_cropped.jpg",
    "photo_full": "data/images/Isha_full.jpg"
}
```

3. Populate [this](data/photos.txt) file <br/>
    a. put the json array under `data1` <br/>
    b. the number of columns in the bingo grid under `N1` <br/>
    c. the number of rows in the bingo grid under `M1` <br/>
    d. put the number of wrong guesses you would like to allow before the person is asked if they want to give up under `wrong_guess_max1`<br/>
    e. OPTIONAL: If you would like to change the theme of the website, tackle [this](data/songs.css) file.
    f. OPTIONAL: If you are interested, you can also change values in the self explanatory fields `wrong_guess_color`, `correct_guess_color`, `specific_instructions1`

4. [Configure a prize!](#Configuring-the-prize)

5. Upload this code to a web app server (we chose [Microsoft Azure](https://portal.azure.com))

6. BINGO! Send your website link to the birthday boy/girl and get on a video call, ask them to share their screen, and play this game of bingo!

## Configuring the prize

Your prize can be a youtube video, and/or a google drive video or picture, and/or a simple link to another webpage, and/or an image used from any online website (Be cautious of copyright issues). It can be one or two or all of them. Exactly how to configure this is described below.

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
