### Map的定义

类似于对象的一种键值对的数据集，但与对象不同的是
对象的键名往往是字符串，而Map的键名则可以自定义为
任何数据类型 Map反映的往往是一种映射关系

    This is code 🌐

    const mapArr=new Map
    mapArr.set(1,'name')
    mapArr.set(true,'Yes')
    mapArr.set('sex','man')
    console.log(mapArr)

    // Map(3) {1 => 'name', true => 'Yes', 'sex' => 'man'}
        [[Entries]]
        0: {1 => "name"}
        1: {true => "Yes"}
        2: {"sex" => "man"}
        size: 3

### Map的方法

    .set(key，value) 添加键名key和该键值value

    .get(key) 根据键名key查找该键的键值

    .has(key) 根据键名key查找该键是否存在该Map中

    .delete(key) 根据键名key删除Map中的该键和值

    .clear() 清除该Map中的所有键值

    .size 检测该集合的大小

Map中可以使用数组及对象当作键名 但是查找的时候却无法通过
数组和对象查找到对应的键值 因为数组及对象存储的只是一个内
存地址 即使是两个相同的对象或数组其内存地址是不同的

Map同样可以使用扩展运算符将数据拆分成元素是键值对数组的二维数组