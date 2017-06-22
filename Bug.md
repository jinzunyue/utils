# EditText
  1. 光标  textCursorDrawable
     a. 必须设置图片
     b. 必须设置大小
     
  2. 下划线
      android:background="@null"
      
# Activity
  1.onCreate()
    代码一般不能写在 setContentView() 的前面
    
# PagerSlidingTabStrip
  需要先设置数据后，在设置 viewPager
  
# ListView
  1. 动态设置分割线
    listView.setDivider(new ColorDrawable(0xffd4d5d6));
    listView.setDividerHeight(2);
    顺序一定不能错
