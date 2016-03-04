# Exception loading sessions from persistent storage

## Exception
While trying to run my spring application with serialVersionUID updating on Tomcat, i got this exception on startup:

Change UserModel from `serialVersionUID = 1L to serialVersionUID = 6137415488772104430L;`

```bash
04-Mar-2016 18:08:17.233 SEVERE [localhost-startStop-1] org.apache.catalina.session.StandardManager.startInternal Exception loading sessions from persistent storage
 java.io.InvalidClassException: jp.sample.bean.model.UserModel; local class incompatible: stream classdesc serialVersionUID = -2535179337713336941, local class serialVersionUID = 6137415488772104430
```

## Reason
Tomcat loads the serialVersionUID of UserModel from persistent storage (a session data of last deployed application)

## Solution
```
 Delete ${catalina.home}/work/Catalina/localhost/<your-app-name>/SESSION.ser
```

:beer: :beer:
