##可选类型的定义
- 如果有值，就是这个值。 
- 如果没值自动至为nil。

##可选类型使用具有安全性

- 在编译阶段就检查
    - 如果类型可选类型，无值，同时用这个值调用某个方法，就会报错。不会运行在报错。（第一要求解包，第二解包的值不为nil）
    
    
 ```swift
 NSString *stockCode = [self findStockCode:@"Facebook"]; // nil is returned
NSString *text = @"Stock Code - ";
NSString *message = [text stringByAppendingString:stockCode]; // runtime error
NSLog(@"%@", message);
    
```

##可选类型的使用

- 所以Swift中是推荐先检查可选类型是否有值, 然后再进行解包的!
###下面例子不推荐使用

````swift
var stockCode:String? = findStockCode("Facebook")
let text = "Stock Code - "
if stockCode {
    let message = text + stockCode!
    print(message)
}
````

###下面例子推荐使用

````swift
let text = "Stock Code - "
if var stockCode = findStockCode("Apple") {
    let message = text + stockCode
    print(message)
}

````
canc kao
