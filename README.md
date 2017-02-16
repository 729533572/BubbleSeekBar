[![](https://jitpack.io/v/woxingxiao/BubbleSeekBar.svg)](https://jitpack.io/#woxingxiao/BubbleSeekBar)

[**中文说明**](https://github.com/woxingxiao/BubbleSeekBar/blob/master/README_zh.md)

**A beautiful Android custom seekbar, which has a bubble view with progress appearing upon when seeking. Highly customizable, mostly demands has been considered. `star` or `pull request` will be welcomed**
****
##Screenshot
![demo](https://github.com/woxingxiao/BubbleSeekBar/blob/master/demo.gif)

[**sample.apk**](https://github.com/woxingxiao/BubbleSeekBar/raw/master/apk/sample.apk)
##Download
root project:`build.gradle`
```groovy
  allprojects {
	 repositories {
		...
		maven { url "https://jitpack.io" }
	 }
  }
```
app:`build.gradle`
```groovy
  dependencies {
     compile 'com.github.woxingxiao:BubbleSeekBar:v1.8'
  }
```
##Attributes
attr | format | description
-------- | ---|---
bsb_min|int|min value, `Integer.MIN_VALUE` <= min < max, default: 0
bsb_max|int|max value, min < max <= `Integer.MAX_VALUE`, default: 100
bsb_progress|int|real time progress value
bsb_track_size|dimension|height of _right-track_(on the right of _thumb_), default: 2dp
bsb_second_track_size|dimension|height of _left-track_(on the left of _thumb_), default: 2dp higher than _right-track_'s height
bsb_thumb_radius|dimension|radius of _thumb_, default: 2dp higher than _left-track_'s height
bsb_thumb_radius_on_dragging|dimension|radius of _thumb_ when be dragging, default: 2 times of _left-track_'s height
bsb_section_count|int|shares of whole progress(max - min), default: 10
bsb_show_section_mark|boolean|show demarcation points or not, default: false
bsb_auto_adjust_section_mark|boolean|auto scroll to nearly _section_mark_ or not, default: false
bsb_track_color|int|color of _right-track_, default: R.color.colorPrimary
bsb_second_track_color|int|color of _left-track_, default: R.color.colorAccent
bsb_thumb_color|int|color of _thumb_, default: same as _left-track_'s color
bsb_show_text|boolean|show _min-text_ and _max-text_ or not, default: false
bsb_text_size|dimension|text size of _min-text_ and _max-text_, default: 14sp
bsb_text_color|int|text color of _min-text_ and _max-text_, default: same as _right-track_'s color
bsb_text_position|enum|text position of _min-text_ and _max-text_ relative to _track_, `SIDES` or `BOTTOM`, default: `SIDES`
bsb_show_thumb_text|boolean|show real time _progress-text_ under _thumb_ or not, default: false
bsb_thumb_text_size|dimension|text size of _progress-text_, default: 14sp
bsb_thumb_text_color|int|text color of _progress-text_, default: same as _left-track_'s color
bsb_show_progress_in_float|boolean|show _bubble-progress_ in float or not, default: false
bsb_bubble_color|int|color of bubble, default: same as _left-track_'s color
bsb_bubble_text_size|dimension|text size of _bubble-progress_, default: 14sp
bsb_bubble_text_color|int|text color of _bubble-progress_, default: #ffffffff
bsb_anim_duration|int|duration of animation, default: 200ms  

##Usage
```xml
   <com.xw.repo.BubbleSeekBar
        android:id="@+id/bubble_seek_bar_0"
        android:layout_width="match_parent"
        android:layout_height="16dp"
        android:layout_marginTop="32dp"/>

    <com.xw.repo.BubbleSeekBar
        android:id="@+id/bubble_seek_bar_1"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginTop="32dp"
        app:bsb_progress="50"
        app:bsb_second_track_color="@color/color_green"
        app:bsb_show_section_mark="true"
        app:bsb_track_color="@color/color_gray"/>

    <com.xw.repo.BubbleSeekBar
        android:id="@+id/bubble_seek_bar_2"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginTop="32dp"
        app:bsb_max="500"
        app:bsb_min="100"
        app:bsb_progress="200"
        app:bsb_second_track_color="@color/color_green"
        app:bsb_track_color="@color/color_gray"
        app:bsb_track_size="4dp"/>

    <com.xw.repo.BubbleSeekBar
        android:id="@+id/bubble_seek_bar_3"
        android:layout_width="match_parent"
        android:layout_height="16dp"
        android:layout_marginTop="32dp"
        app:bsb_show_progress_in_float="true"
        app:bsb_show_section_mark="true"
        app:bsb_show_text="true"
        app:bsb_show_thumb_text="true"/>

    <com.xw.repo.BubbleSeekBar
        android:id="@+id/bubble_seek_bar_4"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginTop="32dp"
        app:bsb_auto_adjust_section_mark="true"
        app:bsb_bubble_color="@color/color_red_light"
        app:bsb_bubble_text_color="@color/colorPrimaryDark"
        app:bsb_bubble_text_size="10sp"
        app:bsb_max="50"
        app:bsb_min="-50"
        app:bsb_second_track_color="@color/color_red"
        app:bsb_show_section_mark="true"
        app:bsb_show_text="true"
        app:bsb_show_thumb_text="true"
        app:bsb_text_position="bottom"
        app:bsb_track_color="@color/color_red_light"/>

    <com.xw.repo.BubbleSeekBar
        android:id="@+id/bubble_seek_bar_5"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginTop="32dp"
        app:bsb_auto_adjust_section_mark="true"
        app:bsb_second_track_color="@color/color_blue"
        app:bsb_section_count="5"
        app:bsb_show_progress_in_float="true"
        app:bsb_show_section_mark="true"
        app:bsb_show_text="true"
        app:bsb_show_thumb_text="true"
        app:bsb_text_position="bottom"
        app:bsb_thumb_text_color="@color/colorPrimary"
        app:bsb_thumb_text_size="18sp"/>
```
You must correct the offsets by setting `ScrollListener` when `BubbleSeekBar`'s parent view is scrollable, otherwise the position of bubble appears maybe be wrong. For example:
```java
   mContainer.setOnYourContainerScrollListener(new OnYourContainerScrollListener() {
       @Override
       public void onScroll() {
           // call this method to correct offsets
           mBubbleSeekBar.correctOffsetWhenContainerOnScrolling();
       }
   });
```

##License
```
The MIT License (MIT)

Copyright (c) 2017 woxingxiao

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```
