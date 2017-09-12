## FAQ

### Android

<b> 1. Getting java.lang.IllegalStateException: Default FirebaseApp is not initialized in this process {your_package_name}. Make sure to call FirebaseApp.initializeApp(Context) first and the google-services.json has the GoogleServicesJson build action. If you have that set, then clean and build again, this is a known issue when using Firebase Component. More info and fix here: https://bugzilla.xamarin.com/show_bug.cgi?id=56108.</b>

<b> 2. Android initialization should be done on and Android Application class to be able to handle received notifications when application is closed. Since no activity exist when application is closed.</b>

<b> 3. You won't receive any push notifications if application is stopped while debugging, should reopen and close again for notifications to work when app closed. This is due to the application being on an unstable state when stopped while debugging.</b>

<b> 4. On some phones android background services might be blocked by some application. This is the case of ASUS Zenfone 3 that has an Auto-start manager, which disables background services by default. You need to make sure that your push notification service is not being blocked by some application like this one, since you won't receive push notifications when app is closed if so.</b>

<b> 5. Must compile against 21+ as plugin is using API 21 specific things. Here is a great breakdown: http://redth.codes/such-android-api-levels-much-confuse-wow/</b>

<b> 6. The package name of your Android aplication must <b>start with lower case</b> or you will get the build error: <code>Installation error: INSTALL_PARSE_FAILED_MANIFEST_MALFORMED</code> </b>

<b> 7. Make sure you have updated your Android SDK Manager libraries:</b>

![image](https://cloud.githubusercontent.com/assets/2547751/6440604/1b0afb64-c0b5-11e4-93b8-c496e2bfa588.png)

<b> 8. Topics are case sensitive so "test" and "Test" are different topics </b>

<b> 9. Error 1589 NotificationService Not posting notification without small icon </b><br>
	It happen when the message is received, but the notification isn't displayed. If you got this error, it mean you need to tell which one is your app icon on <b>Android Project Properties > Android Manifest > application Icon</b> or in the <b>AndroidManifext.xml file and put android:icon="@drawable/{replace with your icon file name}"</b> in the
	
	<application android:label="Test" android:icon="@drawable/{replace with your icon file name}">	
	...
	</application>

