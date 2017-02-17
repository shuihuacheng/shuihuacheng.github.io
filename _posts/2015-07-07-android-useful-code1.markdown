---
layout: post
keywords: blog
description: blog
title: "Android实用代码一"
categories: [Android]
tags: [Android实用代码]
group: Android

---
{% include codepiano/setup %}


## Android实用代码
### 1.根据手机的分辨率 dp 和 px 转换
  {% highlight java %}
  	/**
     * 根据手机的分辨率从 dp 的单位 转成为 px(像素)
     */
    public static int dip2px(final Context context, final float dpValue) {
        final DisplayMetrics metrics = context.getResources().getDisplayMetrics();
        final float scale = metrics.density;
        return (int) ((dpValue * scale) + 0.5f);
    }
    
   /**
     * 根据手机的分辨率从 px(像素) 的单位 转成为 dp
     */
    public static int px2dip(final Context context, final float pxValue) {
        final DisplayMetrics metrics = context.getResources().getDisplayMetrics();
        final float scale = metrics.density;
        return (int) ((pxValue / scale) + 0.5f);
    }
   {% endhighlight %}
   
### 2.显示和隐藏键盘
  {% highlight java %}
	    public static final class SoftInput {
        public static void hide(Context context, IBinder windowToken) {
            InputMethodManager imm = (InputMethodManager) context
                    .getSystemService(Context.INPUT_METHOD_SERVICE);
            if (imm != null) {
                imm.hideSoftInputFromWindow(windowToken, 0);
            }
        }

        public static void show(Context context, View view) {
            InputMethodManager imm = (InputMethodManager) context
                    .getSystemService(Context.INPUT_METHOD_SERVICE);
            if (imm != null) {
                imm.showSoftInput(view, 0);
            }
        }
    }
   {% endhighlight %}
    