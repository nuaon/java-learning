# BigDecimal

```java
BigDecimal bignum1 = new BigDecimal("10");
BigDecimal bignum2 = new BigDecimal("5");
BigDecimal bignum3 = null;

// 加法
bignum3 = bignum1.add(bignum2);
System.out.println("和是：" + bignum3);

// 减法
bignum3 = bignum1.subtract(bignum2);
System.out.println("差是：" + bignum3);

// 乘法
bignum3 = bignum1.multiply(bignum2);
System.out.println("积是：" + bignum3);

// 除法
// 第二个参数表示的是：保留小数点之后多少位；通过BigDecimal的divide方法进行除法时当不整除，出现无限循环小数时，就会抛异常解决方法是：设置精确度;就是给divide设置精确的小数点
bignum3 = bignum1.divide(bignum2, 2, RoundingMode.HALF_UP);
System.out.println("商是：" + bignum3);
```



```java
BigDecimal totalFeeDecimal = new BigDecimal("10");
// 四舍五入保留两位小数
totalFeeDecimal.setScale(2, RoundingMode.HALF_UP);

// RoundingMode参数详解
RoundingMode.CEILING：取右边最近的整数
RoundingMode.DOWN：去掉小数部分取整，也就是正数取左边，负数取右边，相当于向原点靠近的方向取整
RoundingMode.FLOOR：取左边最近的正数
RoundingMode.HALF_DOWN: 五舍六入，负数先取绝对值再五舍六入再负数
RoundingMode.HALF_UP: 四舍五入，负数原理同上
RoundingMode.HALF_EVEN: 这个比较绕，整数位若是奇数则四舍五入，若是偶数则五舍六入
```

