# FreeMarker

数字格式化(金额格式化)

```tex
${num?string('0.00')}
如果小数点后不足两位，用 0 代替

${num?string('#.##')}
如果小数点后多余两位，就只保留两位，否则输出实际值
输出为：1239765.46

${num?string(',###.00')}
输出为：1,239,765.46
整数部分每三位用 , 分割，并且保证小数点后保留两位，不足用 0 代替

${num?string(',###.##')}
输出为：1,239,765.46
整数部分每三位用 , 分割，并且小数点后多余两位就只保留两位，不足两位就取实际位数，可以不不包含小数点

${num?string('000.00')}
输出为：012.70
整数部分如果不足三位（000），前面用0补齐，否则取实际的整数位

${num?string('###.00')}
等价于
${num?string('#.00')}
输出为：12.70
整数取实际的位数

1.action 可能不存在或者action.name不存在，则取默认值为空

${(action.name)!''}

2.code 不存在，默认值为字符串123

${code!'123'}
```
