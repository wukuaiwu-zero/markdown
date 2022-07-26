### call和apply调用方法的应用

    This is code 🌐

    const userInfo={
        name:'wink',
        age:18,
        high:180,
        weight:80,
        getIBM(){
            const IBM=(this.high-110)/this.weight
            return IBM
        }
    }
    userInfo.getIBM()
    // 0.875

    const userInfo={
        name:'wink',
        age:18,
        high:180,
        weight:80,
        getIBM(){
            const IBM=(this.high-110)/this.weight
            return IBM
        }
    }
    const getIbm=userInfo.getIBM
    getIbm()
    // NaN

此时getIbm虽然被定义为getIBM方法，但无法获取到外层userInfo中的信息  
userInfo.getIBM为对象中的方法，不是全局的方法，所以getIbm无法继承  
this，也从而没有值进行函数内部的运算处理

### call()方法重用

对象内的方法只属于该对象，其他对象调用该对象中的方法获取不到该方法  
内部中的值，call()方法可以调用所有者对象为参数的方法  
call()第一个参数为指定调用内部参数的对象名

    This is code 🌐

    const userInfo={
        name:'wink',
        age:18,
        high:180,
        weight:80,
        getIBM(){
            const IBM=(this.high-110)/this.weight
            return IBM
        }
    }

    const userMessage={
        name:'wink',
        age:18,
        high:180,
        weight:80
    }
    const getIbm=userInfo.getIBM
    getIbm.call(userMessage)
    // 0.875

### apply()方法重用

和call方法类似，call方法接受的参数为分别指定参数的值而apply  
接收的参数为一个数组
This is code 🌐

    const userInfo={
        name:'wink',
        age:18,
        high:180,
        weight:80,
        getIBM(name,age){
            const IBM=(this.high-110)/this.weight

            return `${name}的年龄为${age}，IBM为${IBM}`
        }
    }

    const userMessage={
        name:'wink',
        age:18,
        high:180,
        weight:80
    }
    const getIbm=userInfo.getIBM
    getIbm.call(userMessage,'Jane','20')
    // 0.875

    const HanneMessage={
        name:'wink',
        age:18,
        high:180,
        weight:80
    }
    const info=['Hanne','25']
    getIbm.call(HanneMessage,info)
    // 'Hanne的年龄为25，IBM为0.875'

### 扩展

call方法应用场景比apply更广泛或更灵活，根据扩展运算符  
可将prop.apply(ObjName,['','',''.....])转变为prop.apply(ObjName,...[array])