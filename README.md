# Multiple_RunTime_Request_Permission_In_Android
Multiple_RunTime_Request_Permission_In_Android

Step # 0
   <uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION"></uses-permission>
    <uses-permission android:name="android.permission.ACCESS_FINE_LOCATION"></uses-permission>
    <uses-permission android:name="android.permission.CALL_PHONE"></uses-permission>
    <uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE"></uses-permission>
    <uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE"></uses-permission>
    <uses-permission android:name="android.permission.CAMERA"></uses-permission>
    <uses-permission android:name="android.permission.GET_ACCOUNTS"></uses-permission>
    <uses-permission android:name="android.permission.READ_CALENDAR"></uses-permission>
    <uses-permission android:name="android.permission.WRITE_CALENDAR"></uses-permission>
    <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE"></uses-permission>
    <uses-permission android:name="android.permission.INTERNET"></uses-permission>
    <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE"></uses-permission>
    <uses-permission android:name="android.permission.BATTERY_STATS"></uses-permission>
    <uses-feature android:name="android.hardware.location.gps"></uses-feature>
    <uses-permission android:name="android.permission.ANSWER_PHONE_CALLS"></uses-permission>
    

Step # 1.........................................

int Permission_All = 1;

        String[] Permissions = {
                android.Manifest.permission.ACCESS_COARSE_LOCATION,
                android.Manifest.permission.ACCESS_FINE_LOCATION,
                android.Manifest.permission.CALL_PHONE,
                android.Manifest.permission.GET_ACCOUNTS,
                android.Manifest.permission.INTERNET,
                android.Manifest.permission.ACCESS_WIFI_STATE,
                android.Manifest.permission.ACCOUNT_MANAGER,
                android.Manifest.permission.BATTERY_STATS,
                Manifest.permission.ANSWER_PHONE_CALLS,
                android.Manifest.permission.WRITE_CALENDAR,
                android.Manifest.permission.READ_CALENDAR,
                android.Manifest.permission.MEDIA_CONTENT_CONTROL,
                android.Manifest.permission.CAMERA, };
                
                
 Step # 2........................................
 
 if(!hasPermissions(this, Permissions)){
            ActivityCompat.requestPermissions(this, Permissions, Permission_All);
        }

Step # 3.........................................

   public static boolean hasPermissions(Context context, String... permissions){

        if(Build.VERSION.SDK_INT>=Build.VERSION_CODES.M && context!=null && permissions!=null){
            for(String permission: permissions){
                if(ActivityCompat.checkSelfPermission(context, permission)!= PackageManager.PERMISSION_GRANTED){
                    return  false;
                }
            }
        }
        return true;
    }
