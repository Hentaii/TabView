#WeexTabLayout
include WeexTabLayout and WeexVpTabLayout
##DEMO

- WeexTabLayout

![image](https://github.com/Hentaii/TabView/blob/master/app/src/main/res/drawable/show.gif?raw=true)

- WeexVpTabLayout
 

![image](https://github.com/Hentaii/TabView/blob/master/app/src/main/res/drawable/vpdemo.gif?raw=true)

##Attributes


| Attributes    |     format|   description|
| :-------- | --------:| :------: |
| text_color|   color| set tab text color |
| text_selected_color|   color| set tab selected text color |
| backgroud_color|   color| set tab background color |
| text_size|   dimension| set tab text size |

##Import

 Add the dependency:

```
dependencies {
  compile 'com.wallstreetcn.weex:WeexTabLayout:1.1.0'
}
```

##Usage

- usage of WeexTabLayout

Define your WeexTabLayout under your xml :
```
<com.weextablayout.WeexTabLayout
    android:id="@+id/tv_view"
    android:layout_width="match_parent"
    app:text_color="@color/colorPrimary"
    app:text_selected_color="#ffffff"
    app:backgroud_color="@color/colorAccent"
    app:text_size="12sp"
    android:layout_height="50dp">
```

setTabList under your java :

```
List<String> list = new ArrayList<>();
        list.add("1");
        list.add("2");
        list.add("3");
        list.add("4");
        mTbView.setTextList(list);
```

set and add your indicator :

```
		
        ImageView imageView = new ImageView(this);
        imageView.setImageResource(R.drawable.line);
        LinearLayout.LayoutParams lp = new LinearLayout.LayoutParams(120, 20);
        lp.gravity = Gravity.BOTTOM;
        imageView.setLayoutParams(lp);
        //添加indicator
        mTbView.addLineView(imageView);
```

setOnTabClickListener under your java :

```
mTbView.setOnTabClickListener(new WeexTabLayout.TabClickListener() {
            @Override
            public void onTabClick(int index) {
                Toast.makeText(MainActivity.this, "index --->" + index, Toast.LENGTH_SHORT).show();
            }
        });
```



you can also set your own animator :

```
 //添加动画
	  mTbView.setTabViewAnim(new WeexTabLayout.TabViewAnim() {
            @Override
            public void setTabViewAnim(final float startValue, final float endValue, final View view) {

            }
        });
```

- usage of WeexVpTabLayout
 
setViewPager on WeexVpLayout

```
mTlVp.setViewPager(mViewPager);
```

setOnTabClickListener to switch page

```
mTlVp.setOnTabClickListener(new WeexTabLayout.TabClickListener() {
            @Override
            public void onTabClick(int index) {
                mViewPager.setCurrentItem(index);
            }
        });
```


