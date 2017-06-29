#屏幕亮度	

[参考连接](http://blog.5ibc.net/p/65720.html)

	分为当前界面亮度和系统亮度两种类型
	
1. 当前亮度

		private void setLight(Activity context, int brightness) {
	        WindowManager.LayoutParams lp = context.getWindow().getAttributes();
	        lp.screenBrightness = Float.valueOf(brightness) * (1f / 255f);
	        context.getWindow().setAttributes(lp);
		}
2. 系统亮度

		public void saveBrightness(Activity activity, int brightness) {
			Uri uri = Settings.System.getUriFor(Settings.System.SCREEN_BRIGHTNESS);
			Settings.System.putInt(contentResolver, Settings.System.SCREEN_BRIGHTNESS, brightness);
			activity.getContentResolver().notifyChange(uri, null);
		}

* [1.语法示例](#1)

* [1.1图片](#1.1)

* [1.2换行](#1.2)

* [1.3强调](#1.3)

<h2 id="1.3">1.语法示例</h2>
skjfk
