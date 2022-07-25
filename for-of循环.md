### for-of

用于便捷的循环遍历数组中的元素
在条件语句中定义一个变量使其在目标数组中循环
该变量则是目标数组的某一元素
    
    This is code 🌐

    const arr=[1,2,3,4,5]
    for(const item of arr){
        console.log(item)
    }
    // 1 2 3 4 5 

### entries()数组迭代器

将数组中的元素拆分为[ 下标,元素 ]的形式
    
    This is code 🌐

    const nameList=['ming','zhang','Jay','Joe']
    for(const item of nameList.entries()){
        console.log(item)
    }
    // [0,'ming'] [1,'zhang'] [2,'Jay'] [3,'Joe'] 