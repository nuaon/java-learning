# TreeMap

- TreeMap使用的存储结构是平衡二叉树，也称为红黑树。

```java
// 默认按字典升序排序
Map<String, String> treeMap = new TreeMap<>();

// 自定义排序
Map<String, String> treeMap = new TreeMap<>(String::compareTo);

// 按字典升序排序 新字符串为o1，前一个字符串为o2
Map<String, String> treeMap = new TreeMap<>((o1, o2) -> o1.compareTo(o2));

// 按字典降序排序
Map<String, String> treeMap = new TreeMap<>((o1, o2) -> o2.compareTo(o1));

// 按字典降序排序
Map<String, String> treeMap = new TreeMap<>(Comparator.reverseOrder());

// 不排序，按照放入顺序存储 -> 后面的元素永远比前一个大
Map<String, String> treeMap = new TreeMap<>((o1, o2) -> 1);
```

- 示例

```java
Map<String, String> treeMap = new TreeMap<>();
treeMap.put("2", "1");
treeMap.put("9", "1");
treeMap.put("18", "1");
treeMap.put("7", "1");
treeMap.put("1", "1");

System.out.println(treeMap);
for(Map.Entry<String, String> entry : treeMap.entrySet())
{
	System.out.println(entry.getKey() + " => " + entry.getValue());
}

// Out
{1=1, 18=1, 2=1, 7=1, 9=1}
1 => 1
18 => 1
2 => 1
7 => 1
9 => 1
```

#### 注意

当修改 TreeSet/TreeMap默认排序规则时候，必须有0的返回，否则可能删除不掉元素。