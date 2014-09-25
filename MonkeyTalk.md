1.Create new folder called : `monkeyTalk` or whatever you want

2.Copy and paste `monkeytalk-agent-2.0.8.jar` and `monkeytalkpro-ant-2.0.8.beta.jar` to `monkeyTalk`

3.Create `build.xml` inside that folder

```xml
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns:mt="antlib:com.gorillalogic.monkeytalk.ant">

    <target name="instru">
        <mt:instrument
            srcfile="app-debug.apk"
            destfile="myapp-post-instrumented.apk"
            agent="monkeytalk-agent-2.0.8.jar"
            androidsdk="/Users/luckymancvp/adt-bundle-mac-x86_64-20140321/sdk"
            androidtarget="android-19"
            log="log.txt"
            verbose="true" />
        </target>

</project>
```

4.Install `ant` build system. with `brew install ant`

5.Run ant build command to export monkeyTalk angent apk file.
`ant instru -lib monkeytalkpro-ant-2.0.8.beta.jar`
