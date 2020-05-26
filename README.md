# birthday-bingo
Play a game of Birthday Bingo! 

## Song Bingo
Friends will choose songs for the birthday boy/girl to guess. The birthday boy/girl can share their screen and guess the person who chose the song for them, and unlock the final prize(usually a video) once you BINGO!

### Steps to configure:
1. Collect a json array of data from friends and family with the following recommended fields: 

```json
{
    "friend": "name-of-person-choosing-song",
    "song": "name-of-song",
    "artist": "songs-artist",
    "quote": "a-quote-from-the-song",
    "link": "youtube-hash"
}
```

2. Populate [this](data/songs.txt) file <br/>
    a. put the json array under `data1` <br/>
    b. the number of rows and columns in the bingo grid under `N1` (For this version, number of rows = number of columns)<br/>
    c. put the number of wrong guesses you would like to allow before the person is asked if they want to give up under `wrong_guess_max1`<br/>

3. Configure a prize! Put the embedded code for the prize video in the iframe in [this](prize.html) file

4. Upload this code to a web app server (we chose [Microsoft Azure](https://portal.azure.com))

5. BINGO! Send your website link to the birthday boy/girl and get on a video call, ask them to share their screen, and play this game of bingo!

## Credits
Saloni Goel and Abhinav Nair, 2020

## References:
1. https://gist.github.com/wernsey/faaed0e409efb236642aa621f9e4e623
2. https://www.w3schools.com/
3. https://color.adobe.com/create/color-wheel
4. https://fonts.google.com/ 
5. https://fontawesome.com/
