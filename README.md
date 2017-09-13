# NCalendar
一款仿miui日历，月视图，周视图滑动切换，时间从1901-01-01到2099-12-31


## 效果图

![](https://github.com/yannecer/NCalendar/blob/master/app/nclendar2.gif)

## 使用方法


### Gradle
```
compile 'com.necer.ncalendar:ncalendar:2.0.0'
```
### 注意：ncalendar：1.0.x 的日历不能升级到 2.0.0，ncalendar:2.0.0是全新的日历

### 仿miui日历交互

```
   <RelativeLayout
        android:layout_width="match_parent"
        android:layout_height="match_parent">

        <com.necer.ncalendar.calendar.NCalendar
            android:id="@+id/ncalendar"
            android:layout_width="match_parent"
            android:layout_height="match_parent"
            app:defaultCalendar="Month"
            app:firstDayOfWeek="Sunday"
            app:selectCircleColor="#3388ff">

            <android.support.v7.widget.RecyclerView
                android:id="@+id/recyclerView"
                android:layout_width="match_parent"
                android:layout_height="match_parent" />

        </com.necer.ncalendar.calendar.NCalendar>
    </RelativeLayout>


ncalendar包含一个月日类NMonthCalendar，一个周日历NWeekCalendar和一个滑动切换不同视图的NCalendar，
单一日历请使用NMonthCalendar或者NWeekCalendar。

NCalendar日历包含了周日历和月日历，通过滑动切换不同的视图，交互效果仿miui日历，尽可能的实现miui的交互逻辑。

NCalendar在布局文件中需要一个RelativeLayout作为父布局，内部需要一个实现了NestedScrollingChild的view，RecyclerView，NestedScrollView都可以。
 
```
### 主要Api

```
1、监听
ncalendar.setOnCalendarChangeListener(new OnCalendarChangeListener() {
            @Override
            public void onClickCalendar(DateTime dateTime) {
                //日历点击回调
            }

            @Override
            public void onCalendarPageChanged(DateTime dateTime) {
                //日历翻页回调
            }
        });

2、跳转日期
ncalendar.setDate(int year, int month, int day); 

3、月-->周  周-->月
ncalendar.toMonth();
ncalendar.toWeek();

4、支持自定义属性，设置NCalendar默认视图、一周的第一天是周日还是周一等

//NCalendar默认视图,Month 或者 Week，默认是 Month
app:defaultCalendar="Month"
app:defaultCalendar="Week"

//设置一周开始是周一还是周日，Sunday 或者 Monday ，默认是周日Sunday
app:firstDayOfWeek="Sunday"
app:firstDayOfWeek="Monday" 
```
### 支持的属性：

| 属性| 描述|
|:---|:---|
| solarTextColor| 公历日期的文本颜色 |
| lunarTextColor| 农历日期的文本颜色 |
| solarTextSize| 公历日期的文本大小 |
| lunarTextSize| 农历日期的文本大小 |
| hintColor|不是本月的日期文本颜色 |
| selectCircleColor| 选中日期和当天的圆颜色 |
| selectCircleRadius| 选中和当天圆环半径 |
| isShowLunar| 是否显示农历 |
| pointSize| 圆点指示器大小 |
| pointcolor| 圆点指示器颜色 |
| hollowCircleColor| 选中空心圆中间的颜色|
| hollowCircleStroke| 选中空心圆圆环粗细 |
| calendarHeight|日历高度，在NCalendar中使用 |
| defaultCalendar|NCalendar日历默认视图|
| firstDayOfWeek|每周第一天是周日还是周一|
| duration|自动折叠时间|


### 联系我加qq ：619008099

### View的绘制过程参见：http://blog.csdn.net/y12345654321/article/details/73331253 
### 滑动处理参见：http://blog.csdn.net/y12345654321/article/details/73801681


