# PageRecyclerView
Custom recyclerView achieves page turning function and unlimited carousel[中文文档](README-ZH.md)。

## Effect
| carousel     | horizontal-grid-paging    | add-data    | remove-data  | vertical-linear-paging |
| ------------ | ------------------------- | ----------- | ------------ | -------------------- |
| ![](screenRecorder/Screenshot_1.gif) | ![](screenRecorder/Screenshot_2.gif) | ![](screenRecorder/Screenshot_3.gif) | ![](screenRecorder/Screenshot_4.gif) | ![](screenRecorder/Screenshot_5.gif) |

## Demo
[Download APK](apk/app-debug.apk)

## Dependencies
### add dependencies：
```
	dependencies {
		implementation 'ckrjfrog.Page:PageView:1.0.5'//gradle plugin 3.0 (inclusive) above used
		//compile 'ckrjfrog.Page:PageView:1.0.5'//gradle plugin 3.0 below used
	}
```

## Function and Use
### 1.layout reference
```
     <com.ckr.pageview.view.PageView
        android:id="@+id/pageView"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
	app:endless_loop="true"
        app:hide_indicator="false"
        app:indicator_group_height="@dimen/viewpager_indicator_group_height"
        app:indicator_margin="@dimen/viewpager_indicator_margin"
        app:layout_flag="grid"
        app:orientation="horizontal"
        app:page_column="four"
        app:page_row="two"
        app:selected_indicator_color="@color/viewpager_selected_indicator_color"
        app:selected_indicator_diameter="@dimen/viewpager_selected_indicator_diameter"
        app:selected_indicator_drawable="@drawable/shape_point_selected"
        app:unselected_indicator_color="@color/viewpager_unselected_indicator_color"
        app:unselected_indicator_diameter="@dimen/viewpager_unselected_indicator_diameter"
        app:unselected_indicator_drawable="@drawable/shape_point_unselected"/>
```
### 2.Attributes Description
| Attributes                     | Description                     | Type            | Defaults        |
| ---------------------------- | ----------------------------- | ----------------- | ---------------- |
| endless_loop                  | start an unlimited carousel(valid when there is only one item per page) | boolean  | false		|
| hide_indicator                | hide indicator  |			      boolean | false		 |
| indicator_group_heigt         | indicator parent container height |			    int     | 90		|
| indicator_margin		| indicator spacing  |			      int      |  15              |
| layout_flag			| mark linear layout or grid layout  |		   int      |  0(linear layout)       |
| orientation			| layout orientation  |				 int      |  0(horizontal)   |
| page_column			| the number of columns per page  |			        int       |  1		    |
| page_row			| the number of rows per page  |				int       |  1		    |
| selected_indicator_color      | indicator color for the current page  |		             int       |  Color.RED	 |
| selected_indicator_diameter   | indicator diameter for the current page  |			     int       |  15		 |
| selected_indicator_drawable   | indicator drawable for the current page(priority is higher than color) |     drawable  |  null	     |
| unselected_indicator_color	| indicator color for the non-current page  |			     int      | Color.BLACK      |
| unselected_indicator_diameter	| indicator diameter for the non-current page  |			     int      |  15 		 |
| selected_indicator_drawable   | indicator drawable for the non-current page(priority is higher than color) |    drawable |  null	     |

### 3.Code To Use
```
    mainAdapter = new MainAdapter(getContext(), itemLayoutId);//MainAdapter extend BasePageAdapter<T,ViewHolder>
    pageView.setAdapter(mainAdapter);
    pageView.updateAll(items);
```

License
-------

    Copyright 2018 ckrgithub

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
