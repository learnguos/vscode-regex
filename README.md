## 说明

- 一个正则表达式代码片段插件
- 正则表达式包括：数字类正则、字符类正则、特殊类正则
- 支持的页面：javascript、vue、html
- Github仓库：https://github.com/learnguos/vscode-regex



## 使用教程

- 按两次 **`S`** 键 呼出校验数字的正则表达式
- 按两次 **`Z`** 键 呼出校验字符的正则表达式
- 按两次 **`T`** 键 呼出特殊需求的正则表达式



## 示范

![GIF](https://cdn.jsdelivr.net/gh/GuoLearn/Figure-bed/vscode-regexg.gif)



## 校验数字的正则表达式

m到n位的数字

```javascript
/^\d{m,n}$/
```

n位的数字

```javascript
/^\d{n}$/
```

带1到2位小数的正数或负数

```javascript
/^(\-)?\d+(\.\d{1,2})?$/
```

数字

```javascript
/^\d+$/
```

有1~3位小数的正实数

```javascript
/^[0-9]+(.[0-9]{1,3})?$/
```

有两位小数的正实数

```javascript
/^[0-9]+(.[0-9]{2})?$/
```

正数、负数、和小数

```javascript
/^(\-|\+)?\d+(\.\d+)?$/
```

正浮点数

```javascript
/^[1-9]\d*\.\d*|0\.\d*[1-9]\d*$/
```

浮点数

```javascript
/^(-?\d+)(\.\d+)?$/
```

至少n位的数字

```javascript
/^\d{n,}$/
```

负浮点数

```javascript
/^-([1-9]\d*\.\d*|0\.\d*[1-9]\d*)$/
```

零和非零开头的数字

```javascript
/^(0|[1-9][0-9]*)$/
```

非正整数

```javascript
/^-[1-9]\d*|0$/
```

非正浮点数

```javascript
/^((-\d+(\.\d+)?)|(0+(\.0+)?))$/
```

非负整数

```javascript
/^\d+$/
```

非负浮点数

```javascript
/^\d+(\.\d+)?$/
```

非零开头的最多带两位小数的数字

```javascript
/^([1-9][0-9]*)+(.[0-9]{1,2})?$/
```

非零的正整数

```javascript
/^[1-9]\d*$/
```

非零的负整数

```javascript
/^-[1-9]\d*$/
```



## 校验字符的正则表达式

汉字

```javascript
/^(?:[\u3400-\u4DB5\u4E00-\u9FEA\uFA0E\uFA0F\uFA11\uFA13\uFA14\uFA1F\uFA21\uFA23\uFA24\uFA27-\uFA29]|[\uD840-\uD868\uD86A-\uD86C\uD86F-\uD872\uD874-\uD879][\uDC00-\uDFFF]|\uD869[\uDC00-\uDED6\uDF00-\uDFFF]|\uD86D[\uDC00-\uDF34\uDF40-\uDFFF]|\uD86E[\uDC00-\uDC1D\uDC20-\uDFFF]|\uD873[\uDC00-\uDEA1\uDEB0-\uDFFF]|\uD87A[\uDC00-\uDFE0])+$/
```

由英文、数字、汉字组成且字符长度在m到n之间

```javascript
/^[\u4E00-\u9FA5A-Za-z0-9]{m,n}$/
```

由英文开头且由英文、数字、下划线组成且字符长度在m到n之间

```javascript
/^[A-Za-z][A-Za-z0-9_]{m,n}$/
```

由英文、数字、特殊字符组成且至少包括1个大写字母、1个小写字母、1个数字、1个特殊字符且字符长度在m到n之间

```javascript
/^\S*(?=\S{m,n})(?=\S*\d)(?=\S*[A-Z])(?=\S*[a-z])(?=\S*[!@#$%^&*? ])\S*$/
```

英文字母 (大写)

```javascript
/^[A-Z]+$/
```

英文字母 (小写)

```javascript
/^[a-z]+$/
```

英文字母

```javascript
/^[A-Za-z]+$/
```

数字和字母组成

```javascript
/^[A-Za-z0-9]+$/
```

长度在m到n位的字符

```javascript
/^.{3,20}$/
```

由数字、英文、下划线组成

```javascript
/^\w+$/
```

由中文、英文、数字、下划线组成

```javascript
/^[\u4E00-\u9FA5A-Za-z0-9_]+$/
```



## 特殊需求的正则表达式

护照 (包含香港、澳门)

```javascript
/(^[EeKkGgDdSsPpHh]\d{8}$)|(^(([Ee][a-fA-F])|([DdSsPp][Ee])|([Kk][Jj])|([Mm][Aa])|(1[45]))\d{7}$)/
```

邮政编码 (中国)

```javascript
/^(0[1-7]|1[0-356]|2[0-7]|3[0-6]|4[0-7]|5[1-7]|6[1-7]|7[0-5]|8[013-6])\d{4}$/
```

车牌号 (新能源 + 非新能源)

```javascript
/^[京津沪渝冀豫云辽黑湘皖鲁新苏浙赣鄂桂甘晋蒙陕吉闽贵粤青藏川宁琼使领][A-HJ-NP-Z][A-HJ-NP-Z0-9]{4,5}[A-HJ-NP-Z0-9挂学警港澳]$/
```

车牌号 (非新能源)

```javascript
/^[京津沪渝冀豫云辽黑湘皖鲁新苏浙赣鄂桂甘晋蒙陕吉闽贵粤青藏川宁琼使领][A-HJ-NP-Z][A-HJ-NP-Z0-9]{4}[A-HJ-NP-Z0-9挂学警港澳]$/
```

车牌号 (新能源)

```javascript
/^[京津沪渝冀豫云辽黑湘皖鲁新苏浙赣鄂桂甘晋蒙陕吉闽贵粤青藏川宁琼使领][A-HJ-NP-Z](?:((\d{5}[A-HJK])|([A-HJK][A-HJ-NP-Z0-9][0-9]{4}))|[A-HJ-NP-Z0-9]{4}[A-HJ-NP-Z0-9挂学警港澳])$/
```

银行卡号 (10到30位覆盖对公、私账户 参照微信)

```javascript
/^[1-9]\d{9,29}$/
```

手机号码 (最宽松)

```javascript
/^(?:(?:\+|00)86)?1\d{10}$/
```

手机号码 (宽松)

```javascript
/^(?:(?:\+|00)86)?1[3-9]\d{9}$/
```

手机号码 (严谨)

```javascript
/^(?:(?:\+|00)86)?1(?:(?:3[\d])|(?:4[5-79])|(?:5[0-35-9])|(?:6[5-7])|(?:7[0-8])|(?:8[\d])|(?:9[189]))\d{8}$/
```

Email地址

```javascript
/\w+([-+.]\w+)*@\w+([-.]\w+)*\.\w+([-.]\w+)*/
```

身份证号 (澳门)

```javascript
/^[1|5|7]\d{6}\(\d\)$/
```

身份证号 (香港)

```javascript
/^[a-zA-Z]\d{6}\([\dA]\)$/
```

身份证号 (台湾)

```javascript
/^[a-zA-Z][0-9]{9}$/
```

身份证号 (1代 + 2代)

```javascript
/^\d{6}((((((19|20)\d{2})(0[13-9]|1[012])(0[1-9]|[12]\d|30))|(((19|20)\d{2})(0[13578]|1[02])31)|((19|20)\d{2})02(0[1-9]|1\d|2[0-8])|((((19|20)([13579][26]|[2468][048]|0[48]))|(2000))0229))\d{3})|((((\d{2})(0[13-9]|1[012])(0[1-9]|[12]\d|30))|((\d{2})(0[13578]|1[02])31)|((\d{2})02(0[1-9]|1\d|2[0-8]))|(([13579][26]|[2468][048]|0[048])0229))\d{2}))(\d|X|x)$/
```

身份证号 (2代)

```javascript
/^[1-9]\d{5}(?:18|19|20)\d{2}(?:0[1-9]|10|11|12)(?:0[1-9]|[1-2]\d|30|31)\d{3}[\dXx]$/
```

身份证号 (1代)

```javascript
/^[1-9]\d{7}(?:0\d|10|11|12)(?:0[1-9]|[1-2][\d]|30|31)\d{3}$/
```

火车车次

```javascript
/^[GCDZTSPKXLY1-9]\d{1,4}$/
```

手机机身码(IMEI)

```javascript
/^\d{15,17}$/
```

必须带端口号的网址

```javascript
/^((ht|f)tps?:\/\/)?[\w-]+(\.[\w-]+)+:\d{1,5}\/?$/
```

网址

```javascript
/^(((ht|f)tps?):\/\/)?([^!@#$%^&*?.\s-]([^!@#$%^&*?.\s]{0,63}[^!@#$%^&*?.\s])?\.)+[a-z]{2,6}\/?/
```

统一社会信用代码

```javascript
/^[0-9A-HJ-NPQRTUWXY]{2}\d{6}[0-9A-HJ-NPQRTUWXY]{10}$/
```

迅雷链接

```javascript
/^thunderx?:\/\/[a-zA-Z\d]+=$/
```

ed2k链接

```javascript
/^ed2k:\/\/\|file\|.+\|\/$/
```

磁力链接

```javascript
/^magnet:\?xt=urn:btih:[0-9a-fA-F]{40,}.*$/
```

子网掩码

```javascript
/^(254|252|248|240|224|192|128)\.0\.0\.0|255\.(254|252|248|240|224|192|128|0)\.0\.0|255\.255\.(254|252|248|240|224|192|128|0)\.0|255\.255\.255\.(255|254|252|248|240|224|192|128|0)$/
```

html注释

```javascript
/<!--[\s\S]*?-->/g
```

股票代码 (A股)

```javascript
/^(s[hz]|S[HZ])(000[\d]{3}|002[\d]{3}|300[\d]{3}|600[\d]{3}|60[\d]{4})$/
```

32位MD5格式

```javascript
/^([a-f\d]{32}|[A-F\d]{32})$/
```

GUID或UUID

```javascript
/^[a-f\d]{4}(?:[a-f\d]{4}-){4}[a-f\d]{12}$/i
```

24小时制时间

```javascript
/^(?:[01]\d|2[0-3]):[0-5]\d:[0-5]\d$/
```

12小时制时间

```javascript
/^(?:1[0-2]|0?[1-9]):[0-5]\d:[0-5]\d$/
```

base64格式

```javascript
/^\s*data:(?:[a-z]+\/[a-z0-9-+.]+(?:;[a-z-]+=[a-z0-9-]+)?)?(?:;base64)?,([a-z0-9!$&',()*+;=\-._~:@/?%\s]*?)\s*$/i
```

QQ号码

```javascript
/^[1-9][0-9]{4,10}$/
```

中国省份

```javascript
/^浙江|上海|北京|天津|重庆|黑龙江|吉林|辽宁|内蒙古|河北|新疆|甘肃|青海|陕西|宁夏|河南|山东|山西|安徽|湖北|湖南|江苏|四川|贵州|云南|广西|西藏|江西|广东|福建|台湾|海南|香港|澳门$/
```