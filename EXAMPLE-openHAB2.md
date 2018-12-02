# openHAB 2 and pilight 
Sync all your devices into openHAB 2 via mqtt and trigger updates from openHAB 2. 

items/pilights.items
```
   Switch swCeilingLivingRoom "Living Room" {mqtt="<[broker:pilight/status/swCeilingLivingRoom/STATE:state:MAP(states.map)], >[broker:pilight/set/swCeilingLivingRoom/STATE:command:*:JS(lower.js)"} 
   
   Switch swCeilingFrederik "Frederiks Room" {mqtt="<[broker:pilight/status/swCeilingFrederik/STATE:state:MAP(states.map)], >[broker:pilight/set/swCeilingFrederik/STATE:command:*:JS(lower.js)"} 
```

sitemaps/pilight.sitemap
```
   sitemap main label="Main MAP" {
       Frame label="Test"
       {
           Switch item=swCeilingLivingRoom label="Livingroom"
           Switch item=swCeilingFrederik label="Frederiks light"
       }
   } 
```

transform/lower.js
```
   (function(i) {
       return i.toString().toLowerCase();
   })(input)
```

transform/states.map
```
   on=ON
   1=ON
   off=OFF
   0=OFF
```

It would be wise to use a map or javascript for both transformations. 


More details: https://www.openhab.org/addons/bindings/mqtt1/
