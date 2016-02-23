# Create Burp Suite automator script

Create new [Application] in Automator
   > Select [Run Shell Script]

Run latest Burp Suite version .jar file with max memory 2GB, min memory 2GB, disable SNIExtension.
Replace BURP_SUITE_DIR with your burp suite information.

```bash
export BURP_SUITE_DIR=/Applications/BurpSuite/
java -jar -Xmx2G -Xms2G -Djsse.enableSNIExtension=false -jar $(ls -t $BURP_SUITE_DIR/burpsuite*.jar | head -1)
```

Debug by [Run].

Export apllication File > Export > [Where you want to place it].

