# Java 8

```java
List<String> lists = new ArrayList<String>();
lists.add("ddd2");
lists.add("aaa2");
lists.add("bbb1");
lists.add("aaa1");
lists.add("bbb3");
lists.add("ccc1");
lists.add("bbb2");
lists.add("ddd1");

// 过滤 只要以a开头的字符串
logger.info("过滤只要以a开头的字符串");
lists.stream().filter((s) -> s.startsWith("a")).forEach(System.out::println);

// 默认排序
logger.info("默认排序");
lists.stream().filter((s) -> s.startsWith("a")).sorted().forEach(System.out::println);

// 将元素根据指定的Function接口来依次将元素转成另外的对象
logger.info("将元素根据指定的Function接口来依次将元素转成另外的对象");
lists.stream().map(String::toUpperCase).sorted((a, b) -> {
    return a.compareTo(b);
}).forEach(logger::info);

List<String> lists2 = lists.stream().map(String::toUpperCase).sorted(String::compareTo).collect(Collectors.toList());
logger.info(lists2.toString());
```