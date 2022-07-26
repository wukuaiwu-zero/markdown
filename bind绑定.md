### bind绑定方法

与call和apply不同，bind方法是返回一个新的函数而不是调用函数  
bind() 方法创建一个新的函数，在 bind() 被调用时，这个新函数  
的 this 被指定为 bind() 的第一个参数，而其余参数将作为新函数  
的参数，供调用时使用

    This is code 🌐

    const userInfo={
        name:'Anna',
        age:18,
        height:173,
        getUserInfo(company,address,size){
            return `${company}公司提供的结果：${this.name}的身高是${this.height}cm,
            今年${this.age}岁，地址：${address}，类型：${size}`
        }
    }

    const mingInfo={
        name:'Ming',
        age:20,
        height:183,
    }

    const getInfo=userInfo.getUserInfo
    const ming=getInfo.bind(mingInfo,'中心医院',null,'大型')
    ming()