### 关于Set

Set会将一组数据中重复的数据整合成一个数据并将其变
成一个没有重复数据的键值对形式的数组

同样，字符串也可以放入Set中从而将该字符串拆分并且
去除重复的字符

    This is code 🌐

    const setOrder=new Set(['first','second','third','first','second','third'])
    console.log(setOrder)
    // Set(3) {'first','second','third'}

    This is code 🌐

    const strOrder=new Set('toto')
    console.log(strOrder)
    // Set(2) {'t','o'}

### 关于Set的方法

通过.length的方式可以检测一个数组的长度，而对于
Set则是用.size的方法检测Set集合的大小

也可以用.has()的方法检测该元素是否存在于Set集合中
但无法通过类似数组下标的形式检测

使用.add()方法像Set集合中添加参数，使用.delete()
方法删除Set集合中的元素，使用.clear()清空集合

    This is code 🌐

    const setOrder=new Set(['first','second','third','first','second','third'])
    console.log(setOrder.size)
    // 3
    
    This is code 🌐

    console.log(setOrder.has('one'))
    console.log(setOrder.has('second'))
    // false
    // true

    This is code 🌐

    console.log(setOrder.add('one'))
    // Set (4) {'first','second','third','one'}

    console.log(setOrder.delete('second'))
    // Set (3) {'first','third','one'}

    console.log(setOrder.clear())
    // Set (0) {}

可以将取得的Set集合使用扩展运算符将其变成数组
    
    This is code 🌐

    const arr=[1,2,3,1,2,3]
    console.log(new Set(arr))
    // Set(3) {1,2,3}

    console.log([...new Set(arr)])
    // [1,2,3]