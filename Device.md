* [1.屏幕亮度](#screen_bightness)

	* [1.1 获取当前屏幕亮度](#get_screen_bightness_this)

	* [1.2 获取当前屏幕模式](#get_screen_bightness_mode)

	* [1.1 设置当前界面亮度](#set_screen_bightness_this)

	* [1.2 设置系统亮度](#set_screen_bightness_sys)


<h1 id="screen_bightness">屏幕亮度</h1>	

[参考连接](http://blog.5ibc.net/p/65720.html)

	分为当前界面亮度和系统亮度两种类型.
	亮度模式有自动调节和手动调节两种模式
	亮度的范围 0~256
	
* <h3 id="get_screen_bightness_this">获取当前屏幕亮度</h3> 

		long screenBrightness = Settings.System.getInt(getContentResolver(), Settings.System.SCREEN_BRIGHTNESS);
	
* <h3 id="get_screen_bightness_mode">获取当前屏幕模式</h3>

		long screenMode = Settings.System.getInt(getContentResolver(), Settings.System.SCREEN_BRIGHTNESS_MODE);
		
* <h3 id="set_screen_bightness_this">设置当前界面亮度</h3> 

		private void setLight(Activity context, int brightness) {
	        WindowManager.LayoutParams lp = context.getWindow().getAttributes();
	        lp.screenBrightness = Float.valueOf(brightness) * (1f / 255f);
	        context.getWindow().setAttributes(lp);
		}
		
* <h3 id="set_screen_bightness_sys">设置系统亮度</h3> 

		public void saveBrightness(Activity activity, int brightness) {
			Uri uri = Settings.System.getUriFor(Settings.System.SCREEN_BRIGHTNESS);
			Settings.System.putInt(contentResolver, Settings.System.SCREEN_BRIGHTNESS, brightness);
			activity.getContentResolver().notifyChange(uri, null);
		}


