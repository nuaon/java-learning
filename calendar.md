# Calendar

```java
// 指定使用香港时区
TimeZone zone = TimeZone.getTimeZone("Asia/Hong_Kong");
Calendar calendar = Calendar.getInstance(zone);

// Calendar calendar = Calendar.getInstance();
// TimeZone zone = TimeZone.getTimeZone("Asia/Hong_Kong");
// calendar.setTimeZone(zone);

Date date = calendar.getTime();
```

1、常用方法

```java
// 根据日历的规则，为给定的日历字段添加或减去指定的时间量。
abstract void add(int field, int amount)
// 判断此 Calendar 表示的时间是否在指定 Object 表示的时间之后，返回判断结果。
boolean after(Object when)
// 判断此 Calendar 表示的时间是否在指定 Object 表示的时间之前，返回判断结果。
boolean before(Object when)
// 给定此 Calendar 的时间值，返回指定日历字段可能拥有的最大值。
int getActualMaximum(int field)
// 给定此 Calendar 的时间值，返回指定日历字段可能拥有的最小值。
int getActualMinimum(int field)
// 获取一星期的第一天；例如，在美国，这一天是 SUNDAY，而在法国，这一天是 MONDAY。
int getFirstDayOfWeek()
// 返回此 Calendar 实例给定日历字段的最高的最小值。
abstract int getGreatestMinimum(int field)
// 使用默认时区和语言环境获得一个日历。
static Calendar getInstance()
// 使用默认时区和指定语言环境获得一个日历。
static Calendar getInstance(Locale aLocale)
// 使用指定时区和默认语言环境获得一个日历。
static Calendar getInstance(TimeZone zone)
// 使用指定时区和语言环境获得一个日历。
static Calendar getInstance(TimeZone zone, Locale aLocale)
// 返回此 Calendar 实例给定日历字段的最低的最大值。
abstract int getLeastMaximum(int field)
//返回此 Calendar 实例给定日历字段的最大值。
abstract int getMaximum(int field)
// 获取一年中第一个星期所需的最少天数，例如，如果定义第一个星期包含一年第一个月的第一天，则此方法将返回 1。
int getMinimalDaysInFirstWeek()
// 设置一星期的第一天是哪一天；例如，在美国，这一天是 SUNDAY，而在法国，这一天是 MONDAY。
void setFirstDayOfWeek(int value)
// 设置一年中第一个星期所需的最少天数，例如，如果定义第一个星期包含一年第一个月的第一天，则使用值 1 调用此方法。
void setMinimalDaysInFirstWeek(int value)
// 使用给定的 Date 设置此 Calendar 的时间。
void setTime(Date date)
// 用给定的 long 值设置此 Calendar 的当前时间值。
void setTimeInMillis(long millis)
```



2、获取值

```java
// 年
calendar.get(Calendar.YEAR);
// 月（必须要 + 1）
calendar.get(Calendar.MONTH) + 1;
// 日
calendar.get(Calendar.DATE);
// 时
calendar.get(Calendar.HOUR_OF_DAY);
// 分
calendar.get(Calendar.MINUTE);
// 秒
calendar.get(Calendar.SECOND);
// 星期（Locale.ENGLISH情况下，周日是1）
calendar.get(Calendar.DAY_OF_WEEK);
```

> 如果拿时间不是为了计算而是展示出来，肯定用SimpleDateFormart了，模式为yyyy-MM-dd HH:mm:ss

3、设置值

```java
// 年月日时分秒（月份0代表1月）
calendar.set(2013, 5, 4, 13, 44, 51);
// 年
calendar.set(Calendar.YEAR, 2014);
// 月（月份0代表1月）
calendar.set(Calendar.MONTH, 7);
// 日
calendar.set(Calendar.DATE, 11);
// 时
calendar.set(Calendar.HOUR_OF_DAY, 15);
// 分
calendar.set(Calendar.MINUTE, 33);
// 秒
calendar.set(Calendar.SECOND, 32);
```

4、运算值

```java
// 年
calendar.add(Calendar.YEAR, 1);
// 月
calendar.add(Calendar.MONTH, 1);
// 日
calendar.add(Calendar.DATE, 1);
// 时
calendar.add(Calendar.HOUR_OF_DAY, -1);
// 分
calendar.add(Calendar.MINUTE, 1);
// 秒
calendar.add(Calendar.SECOND, 1);
// 周
calendar.add(Calendar.DATE, 7);
```

