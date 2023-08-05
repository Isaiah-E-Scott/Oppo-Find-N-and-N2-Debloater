# Oppo-Find-N-and-N2-Debloater
This is an automated Python script to debloat the Oppo Find N Series of phones. This can both uninstall the vast majority of unnecessary applications while also keeping most of the functionality of the phone. It can also reverse the de-bloat process if you need to perform an update.

All you need to use this is have Python 3.x installed on your machine as well as the Android Debugging Bridge (ADB).

I installed ADB using this XDA thread: https://forum.xda-developers.com/t/tool-minimal-adb-and-fastboot-2-9-18.2317790/

And here is the latest Pythin installation link: https://www.python.org/downloads/

## Applications and what they do:
com.android.bips - Default Print Service<br>
com.android.bookmarkprovider - Bookmark Provider<br>
com.android.cellbroadcastreceiver - Cell Broadcast Receiver<br>
com.android.cellbroadcastreceiver.overlay.common - Cell Broadcast Receiver Overlay<br>
com.android.printspooler - Print Spooler<br>
com.baidu.input_oppo - Default Oppo Chinese Keybooard<br>
com.coloros.activation - Oppo Activation (does not work in the USA)<br>
com.coloros.assistantscreen - Oppo Home Screen Shelf<br>
com.coloros.bootreg - Oppo Setup Wizard<br>
com.coloros.childrenspace - Children Space<br>
com.coloros.codebook - Oppo Password Manager<br>
com.coloros.colordirectservice - Oppo Screen Recognition<br>
com.coloros.directui /<br>
com.coloros.healthcheck /<br>
com.coloros.karaoke /<br>
com.coloros.mapcom.frame /<br>
com.coloros.ocrscanner /<br>
com.coloros.ocrservice /<br>
com.coloros.ocs.opencapabilityservice /<br>
com.coloros.operationManual /<br>
com.coloros.oshare /<br>
com.coloros.phonemanager /<br>
com.coloros.remoteguardservice /<br>
com.coloros.sceneservice /<br>
com.coloros.securepay /<br>
com.coloros.securityguard /<br>
com.coloros.translate.engine /<br>
com.coloros.video / Failure [not installed for 0]<br>
com.heytap.cloud /<br>
com.heytap.mydevices /<br>
com.heytap.opluscarlink /<br>
com.heytap.speechassist /<br>
com.iflytek.speechsuite /<br>
com.mobiletools.systemhelper /<br>
com.nearme.instant.platform /<br>
com.oplus.acc.gac / Failure [not installed for 0]<br>
com.oplus.aiunit /<br>
com.oplus.aod /<br>
com.oplus.appdetail /<br>
com.oplus.apprecover /<br>
com.oplus.cardigitalkey /<br>
com.oplus.cosa /
com.oplus.deepthinker /
com.oplus.encryption /
com.oplus.interconnectcollectkit /
com.oplus.linker /
com.oplus.metis /
com.oplus.ocar /
com.oplus.ocloud /
com.oplus.omoji /
com.oplus.onet /
com.oplus.ovoicemanager /
com.oplus.ovoicemanager.cmdwakeup /
com.oplus.ovoicemanager.wakeup /
com.oplus.owork / Failure [not installed for 0]
com.oplus.pantanal.ums / Failure [not installed for 0]
com.oplus.securitykeyboard / do not unnistall
com.oplus.smartengine /
com.oplus.stdsp /
com.oplus.synergy /
com.oplus.travelengine / Failure [not installed for 0]
com.oplus.upgradeguide /
com.oplus.viewtalk / Failure [not installed for 0]
com.oplus.vip /
com.opos.ads /
com.oppo.ctautoregist /
com.oppo.instant.local.service /
com.rongcard.eidapi /

## Code:
```python
import os
import subprocess

# Use this when you want to permnently use set the ADB directory
# directory = "C:\Program Files (x86)\Minimal ADB and Fastboot\"

# Use this when you want to input the ADB directory every time
directory = input('What is your ADB directory?')

install_commands = ['adb shell pm install-existing com.android.bookmarkprovider',
'adb shell pm install-existing com.android.cellbroadcastreceiver',
'adb shell pm install-existing com.android.cellbroadcastreceiver.overlay.common',
'adb shell pm install-existing com.android.printspooler',
'adb shell pm install-existing com.android.bips',
'adb shell pm install-existing com.nearme.instant.platform',
'adb shell pm install-existing com.mobiletools.systemhelper',
'adb shell pm install-existing com.baidu.input_oppo',
'adb shell pm install-existing com.coloros.childrenspace',
'adb shell pm install-existing com.coloros.healthcheck',
'adb shell pm install-existing com.coloros.translate.engine',
'adb shell pm install-existing com.coloros.operationManual',
'adb shell pm install-existing com.coloros.assistantscreen',
'adb shell pm install-existing com.coloros.phonemanager',
'adb shell pm install-existing com.coloros.directui',
'adb shell pm install-existing com.coloros.karaoke',
'adb shell pm install-existing com.coloros.remoteguardservice',
'adb shell pm install-existing com.coloros.bootreg',
'adb shell pm install-existing com.coloros.activation',
'adb shell pm install-existing com.coloros.mapcom.frame',
'adb shell pm install-existing com.coloros.securityguard',
'adb shell pm install-existing com.coloros.ocs.opencapabilityservice',
'adb shell pm install-existing com.coloros.ocrscanner',
'adb shell pm install-existing com.coloros.securepay',
'adb shell pm install-existing com.coloros.codebook',
'adb shell pm install-existing com.coloros.oshare',
'adb shell pm install-existing com.coloros.ocrservice',
'adb shell pm install-existing com.coloros.sceneservice',
'adb shell pm install-existing com.coloros.colordirectservice',
'adb shell pm install-existing com.coloros.video',
'adb shell pm install-existing com.oplus.ocar',
'adb shell pm install-existing com.oplus.omoji',
'adb shell pm install-existing com.oplus.securitykeyboard',
'adb shell pm install-existing com.oplus.ocloud',
'adb shell pm install-existing com.oplus.apprecover',
'adb shell pm install-existing com.oplus.interconnectcollectkit',
'adb shell pm install-existing com.oplus.linker',
'adb shell pm install-existing com.oplus.encryption',
'adb shell pm install-existing com.oplus.upgradeguide',
'adb shell pm install-existing com.oplus.smartengine',
'adb shell pm install-existing com.oplus.metis',
'adb shell pm install-existing com.oplus.cardigitalkey',
'adb shell pm install-existing com.oplus.ovoicemanager.wakeup',
'adb shell pm install-existing com.oplus.onet',
'adb shell pm install-existing com.oplus.ovoicemanager',
'adb shell pm install-existing com.oplus.deepthinker',
'adb shell pm install-existing com.oplus.synergy',
'adb shell pm install-existing com.oplus.appdetail',
'adb shell pm install-existing com.oplus.aiunit',
'adb shell pm install-existing com.oplus.cosa',
'adb shell pm install-existing com.oplus.stdsp',
'adb shell pm install-existing com.oplus.vip',
'adb shell pm install-existing com.oplus.pantanal.ums',
'adb shell pm install-existing com.oplus.ovoicemanager.cmdwakeup',
'adb shell pm install-existing com.oplus.owork',
'adb shell pm install-existing com.oplus.aod',
'adb shell pm install-existing com.oplus.travelengine',
'adb shell pm install-existing com.oplus.viewtalk',
'adb shell pm install-existing com.oplus.acc.gac',
'adb shell pm install-existing com.oppo.ctautoregist',
'adb shell pm install-existing com.oppo.instant.local.service',
'adb shell pm install-existing com.opos.ads',
'adb shell pm install-existing com.iflytek.speechsuite',
'adb shell pm install-existing com.rongcard.eidapi',
'adb shell pm install-existing com.heytap.cloud',
'adb shell pm install-existing com.heytap.speechassist',
'adb shell pm install-existing com.heytap.opluscarlink',
'adb shell pm install-existing com.heytap.mydevices',
'adb shell pm install-existing com.coloros.findmyphone',
'adb shell pm install-existing com.oplus.pay',
'adb shell pm install-existing com.heytap.browser',
'adb shell pm install-existing com.heytap.quicksearchbox',
'adb shell pm install-existing com.heytap.openid',
'adb shell pm install-existing com.heytap.pictorial',
'adb shell pm install-existing com.heytap.tas',
'adb shell pm install-existing com.heytap.market',
'adb shell pm install-existing com.heytap.htms',
'adb shell pm install-existing com.finshell.wallet',
'adb shell pm install-existing com.coloros.calendar',
'adb shell pm install-existing com.coloros.filemanager',
'adb shell pm install-existing com.heytap.music',
'adb shell pm install-existing com.heytap.themestore',
'adb shell pm install-existing com.heytap.yoli',
'pause']

uninstall_commands = ['adb shell pm uninstall -k --user 0 com.android.bookmarkprovider',
'adb shell pm uninstall -k --user 0 com.android.cellbroadcastreceiver',
'adb shell pm uninstall -k --user 0 com.android.cellbroadcastreceiver.overlay.common',
'adb shell pm uninstall -k --user 0 com.android.printspooler',
'adb shell pm uninstall -k --user 0 com.android.bips',
'adb shell pm uninstall -k --user 0 com.nearme.instant.platform',
'adb shell pm uninstall -k --user 0 com.mobiletools.systemhelper',
'adb shell pm uninstall -k --user 0 com.baidu.input_oppo',
'adb shell pm uninstall -k --user 0 com.coloros.childrenspace',
'adb shell pm uninstall -k --user 0 com.coloros.healthcheck',
'adb shell pm uninstall -k --user 0 com.coloros.translate.engine',
'adb shell pm uninstall -k --user 0 com.coloros.operationManual',
'adb shell pm uninstall -k --user 0 com.coloros.assistantscreen',
'adb shell pm uninstall -k --user 0 com.coloros.phonemanager',
'adb shell pm uninstall -k --user 0 com.coloros.directui',
'adb shell pm uninstall -k --user 0 com.coloros.karaoke',
'adb shell pm uninstall -k --user 0 com.coloros.remoteguardservice',
'adb shell pm uninstall -k --user 0 com.coloros.bootreg',
'adb shell pm uninstall -k --user 0 com.coloros.activation',
'adb shell pm uninstall -k --user 0 com.coloros.mapcom.frame',
'adb shell pm uninstall -k --user 0 com.coloros.securityguard',
'adb shell pm uninstall -k --user 0 com.coloros.ocs.opencapabilityservice',
'adb shell pm uninstall -k --user 0 com.coloros.ocrscanner',
'adb shell pm uninstall -k --user 0 com.coloros.securepay',
'adb shell pm uninstall -k --user 0 com.coloros.codebook',
'adb shell pm uninstall -k --user 0 com.coloros.oshare',
'adb shell pm uninstall -k --user 0 com.coloros.ocrservice',
'adb shell pm uninstall -k --user 0 com.coloros.sceneservice',
'adb shell pm uninstall -k --user 0 com.coloros.colordirectservice',
'adb shell pm uninstall -k --user 0 com.coloros.video',
'adb shell pm uninstall -k --user 0 com.oplus.ocar',
'adb shell pm uninstall -k --user 0 com.oplus.omoji',
'adb shell pm uninstall -k --user 0 com.oplus.securitykeyboard',
'adb shell pm uninstall -k --user 0 com.oplus.ocloud',
'adb shell pm uninstall -k --user 0 com.oplus.apprecover',
'adb shell pm uninstall -k --user 0 com.oplus.interconnectcollectkit',
'adb shell pm uninstall -k --user 0 com.oplus.linker',
'adb shell pm uninstall -k --user 0 com.oplus.encryption',
'adb shell pm uninstall -k --user 0 com.oplus.upgradeguide',
'adb shell pm uninstall -k --user 0 com.oplus.smartengine',
'adb shell pm uninstall -k --user 0 com.oplus.metis',
'adb shell pm uninstall -k --user 0 com.oplus.cardigitalkey',
'adb shell pm uninstall -k --user 0 com.oplus.ovoicemanager.wakeup',
'adb shell pm uninstall -k --user 0 com.oplus.onet',
'adb shell pm uninstall -k --user 0 com.oplus.ovoicemanager',
'adb shell pm uninstall -k --user 0 com.oplus.deepthinker',
'adb shell pm uninstall -k --user 0 com.oplus.synergy',
'adb shell pm uninstall -k --user 0 com.oplus.appdetail',
'adb shell pm uninstall -k --user 0 com.oplus.aiunit',
'adb shell pm uninstall -k --user 0 com.oplus.cosa',
'adb shell pm uninstall -k --user 0 com.oplus.stdsp',
'adb shell pm uninstall -k --user 0 com.oplus.vip',
'adb shell pm uninstall -k --user 0 com.oplus.pantanal.ums',
'adb shell pm uninstall -k --user 0 com.oplus.ovoicemanager.cmdwakeup',
'adb shell pm uninstall -k --user 0 com.oplus.owork',
'adb shell pm uninstall -k --user 0 com.oplus.aod',
'adb shell pm uninstall -k --user 0 com.oplus.travelengine',
'adb shell pm uninstall -k --user 0 com.oplus.viewtalk',
'adb shell pm uninstall -k --user 0 com.oplus.acc.gac',
'adb shell pm uninstall -k --user 0 com.oppo.ctautoregist',
'adb shell pm uninstall -k --user 0 com.oppo.instant.local.service',
'adb shell pm uninstall -k --user 0 com.opos.ads',
'adb shell pm uninstall -k --user 0 com.iflytek.speechsuite',
'adb shell pm uninstall -k --user 0 com.rongcard.eidapi',
'adb shell pm uninstall -k --user 0 com.heytap.cloud',
'adb shell pm uninstall -k --user 0 com.heytap.speechassist',
'adb shell pm uninstall -k --user 0 com.heytap.opluscarlink',
'adb shell pm uninstall -k --user 0 com.heytap.mydevices',
'adb shell service call package 131 s16 com.coloros.findmyphone i32 0 i32 0',
'adb shell service call package 131 s16 com.oplus.pay i32 0 i32 0',
'adb shell service call package 131 s16 com.heytap.browser i32 0 i32 0',
'adb shell service call package 131 s16 com.heytap.quicksearchbox i32 0 i32 0',
'adb shell service call package 131 s16 com.heytap.openid i32 0 i32 0',
'adb shell service call package 131 s16 com.heytap.pictorial i32 0 i32 0',
'adb shell service call package 131 s16 com.heytap.tas i32 0 i32 0',
'adb shell service call package 131 s16 com.heytap.market i32 0 i32 0',
'adb shell service call package 131 s16 com.heytap.htms i32 0 i32 0',
'adb shell pm disable-user --user 0 com.finshell.wallet',
'adb shell pm disable-user --user 0 com.coloros.calendar',
'adb shell pm disable-user --user 0 com.coloros.filemanager',
'adb shell pm disable-user --user 0 com.heytap.music',
'adb shell pm disable-user --user 0 com.heytap.themestore',
'adb shell pm disable-user --user 0 com.heytap.yoli',
'pause']

def get_choice(choices):
  choice = ""
  while choice not in choices:
      choice = input("Choose one Install[I] or Uninstall[U]: ")
  return choice

choice = get_choice(["Install", "install", "I", "i", "Uninstall", "uninstall", "U", "u"])

os.system('start cmd /c')
os.chdir(directory)

if choice.__eq__("Install") or choice.__eq__("install") or choice.__eq__("I") or choice.__eq__("i"):
    for y in install_commands:
        os.system(y)

if choice.__eq__("Uninstall") or choice.__eq__("uninstall") or choice.__eq__("U") or choice.__eq__("u"):
    for x in uninstall_commands:
        os.system(x)
```

## Q&A and Explanations:
The code sometimes returns Failure [not installed for 0]
- this just means that the application is not installed in your device. It has either already been uninstalled or it is an app on the other phone model or a previous ROM version.
