# SlidingFragmentActivity
侧边栏框架的使用


      1.在自己的activity上继承SlidingFragmentActivity

      2.加载主界面
          setContentView(R.layout.activity_home);

      3.设置侧边栏
		  setBehindContentView(R.layout.left_menu);
		
      4.得到slidingMenu对象
          SlidingMenu slidingMenu=getSlidingMenu();

      5.设置屏幕触摸
        slidingMenu.setTouchModeAbove(SlidingMenu.TOUCHMODE_FULLSCREEN);

      6.设置屏幕预留宽度
        slidingMenu.setBehindOffset(500);

      7.初始化fragment

         //得到fm对象
	    FragmentManager fm=getSupportFragmentManager();
	    FragmentTransaction transaction=fm.beginTransaction();//开启事务
			
		//替换侧边栏---repalce里面的参数
			transaction.replace(R.id.fl_left_menu, new LeftMenuFragment(), TAG_LEFT_MENU);
		//替换主界面
			transaction.replace(R.id.fl_content, new ContentFragment(), TAG_CONTRNT);
		//提交
			transaction.commit();
