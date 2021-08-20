```
Spotify PodCast power-up for Discord RPC Client. 

This tool will show you what music you're listening to in your Discord bio, Album - Podcast - Artist data.
adds them all to your situation. The languages used are Node.JS (JavaScript) and C#.
This tool is completely legal and in no way violates Spotify's rules, privacy policy.
and data usage information does not cause damage or loss. For Spotify's developers
Music played instantly on the device (Computer) via the WebAPI it has published
The device where Discord is located via Developer Tools by getting the information and podcast details.
transmits it to the server as Rich Presence data. 
```

```
The person who made this powerup possible : @MuhammedMGS (yes, you're welcome <3)

macesdev role : Founder
Instagram : @muhammedmgs
Twitter : @muhammedmgs
Discord : MuhammedMGS#1881 
```

```
Use of

After downloading the program, you can start your installation with the spotipod_setup.exe (valid for Windows*) file.
you can do it easily. Open your Discord and Spotify apps, Discord > User Settings > Connections
After syncing your Spotify account with your Discord account from the tab, "Display Spotify status on profile"
Activate "View" option. Then click RPC > Run from the Windows Tray
you can activate. Now the application will transfer the music you listen to instantly to Spotify. If you have a problem
you can create a request from the project/Issues tab.
```

```
Requirements (Software Required)

.NET Framework 4.2.7 (https://dotnet.microsoft.com/download/dotnet-framework/net472 - minimum version : 4.2.7),
Node.JS (https://nodejs.org/en/download/current/ - minimum version : 16.7.0).

If you do the installations
If you are living, you can create a request from the project/Issues tab. 
```

```
Config (JSON) Detailing and WebAPI Configuration

Warning! : This article contains technical details. If you do not have much knowledge, it is recommended not to play with the settings.

If we go through the ./spotipod/config/app.json file through the directory where you installed the application, we can save our data.
And let's take a closer look at what they do. 
```

```json
Draft

{
     "webapiLocation": "/webapi",
     "webapiRunCommand": "node webapi.js",
     "webapiValueExractLocation": "/chace.json"
} 
```

```json
STRING : What is webapiLocation?

Spotify Developer Tools, which the program uses to receive data through the Spotify application, is only
Incompatibility because it is programmed with the main application (C#) language, as it can communicate
with the JavaScript language will occur. Therefore, the main application (C#) can use JavaScript 
(cmd snippet) to receive data from WebAPI.NodeJS is preferred because it is possible to pull data with) 
will create data and send it as a json will write to the file. main application (C#) can activate RPC
by reading this json file. This data too It is responsible for revealing the location of the WebAPI.

E.g :

{
     "webapiLocation": "C:\\Program Files\\macesdev\\spotipod\\webapi",
} 
```

```json
STRING : What is webapiRunCommand?

wenapiLocation causes the main application (C#) to pull data by triggering JavaScript (NodeJS). Command developer
(macesdev) automatically sets it during installation. If you think WebAPI is not working, use this command as WebAPI.
You can decide whether data is obtained by running

E.g :

{
     "webapiRunCommand": "node webapi.js"
}

Here it gets data by triggering the webapi.js file in the webapiLocation folder, while C# reads it.
It helps to run RPC. 
```

```json
STRING : What is webapiValueExractLocation?

It is the location where the data obtained after the WebAPI is triggered is stored (stored). These data
changing the program properly
may cause it to not work. The chace file should be as follows.

{
    "audioPodcastName": "B16 - Bize Tavsiye Edebileceğiniz Filimler Var mı?",
    "mainPodcastName": "Bir Elit Bilim İnsanı: Prof. Dr. Celal Şengör",
    "podcastBannerURL": "https://i.scdn.co/image/465c4b24a397642055863081c83719c4992d006a",
    "audioPodcastTime": 4.02,
    "audioLatestTime": 1.05,
    "webapiSyntaxVersion": 1
}

Podcast information is random, has nothing to do with reality*
```

```
Thanks to Spotify Developer Tools and Discord Developer Portal for making this tool possible <3 
```
