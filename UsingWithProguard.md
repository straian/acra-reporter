# Introduction #

This comes from my page http://www.winters.org.nz/acra-reporter

Please see that page - you need to change my "wintersacrareporter.appspot.com" with your application address

# Details #

Login and signup to your app engine, then add the application package, add the following class to your android application, you will need to make up the strings.

```
@ReportsCrashes(formKey = "",
  formUri="https://[YOURAPPID].appspot.com/acrareport",
  formUriBasicAuthLogin = "username", 
  formUriBasicAuthPassword = "password",
  mode = ReportingInteractionMode.DIALOG, 
  resNotifTickerText = R.string.crash_notif_ticker_text, 
  resNotifTitle = R.string.crash_notif_title, 
  resNotifText = R.string.crash_notif_text, 
  resNotifIcon = android.R.drawable.stat_notify_error,
  resDialogText = R.string.crash_dialog_text, 
  resDialogIcon = android.R.drawable.ic_dialog_info, 
  resDialogTitle = R.string.crash_dialog_title, 
  resDialogCommentPrompt = R.string.crash_dialog_comment_prompt, 
  resDialogOkToast = R.string.crash_dialog_ok_toast)
public class CrashAppWrapper extends Application
{
  @Override
  public void onCreate()
  {
    // The following line triggers the initialization of ACRA
    super.onCreate();
     try
    {
      ACRA.init(this);
    }catch(IllegalStateException e)
    {
      // ignore acra error
    }
  }
}
```