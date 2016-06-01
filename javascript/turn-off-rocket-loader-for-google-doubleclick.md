# Turn off Rocket Loader for Google DoubleClick

Ref: http://stackoverflow.com/questions/22921788/turn-off-rocket-loader-for-google-doubleclick

RocketLoader is affecting on GeoLocation and DoubleClick Ads is not working properly based on Geo Location because Rocket Loader is doing the code async. 
## Before
```
<script type='text/rocketscript'>
  googletag.defineSlot('/7229/test/general', [1, 1], 'div-gpt-ad-1362035459309-0').addService(googletag.pubads());
  ....
  googletag.enableServices();
</script>
```

## Solution
You can have Rocket Loader ignore individual scripts by adding the data-cfasync="false" attribute to the relevant script tag, for example: 
```
<script data-cfasync="false">
```

## After
```
<script data-cfasync="false">
  googletag.defineSlot('/7229/test/general', [1, 1], 'div-gpt-ad-1362035459309-0').addService(googletag.pubads());
  ....
  googletag.enableServices();
</script>
```
