# Create Burp Suite automator script

Create new [Application] in Automator
Select [Run Shell Script]

Run latest Burp Suite version .jar file with max memory 2GB, min memory 2GB, disable SNIExtension

```bash
export BURP_SUITE_DIR=/Applications/BurpSuite/
export BURP_SUITE_VERSION=burpsuite_pro
java -jar -Xmx2G -Xms2G -Djsse.enableSNIExtension=false -jar $(ls -t $BURP_SUITE_DIR/$BURP_SUITE_VERSION*.jar | head -1)
```

Replace BURP_SUITE_DIR, $BURP_SUITE_VERSION with your burp suite information.

Debug by [Run]

Export apllication File > Export > Where you want to place it

