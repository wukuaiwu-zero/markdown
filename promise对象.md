## Promise 对象用于表示一个异步操作的最终完成 (或失败)及其结果值

#### Promise 对象代表一个在这个 promise 被创建出来时不一定已知的值

##### 它让您能够把异步操作最终的成功返回值或者失败原因和相应的处理程序关联起来。这样使得异步方法可以像同步方法那样返回值：异步方法并不会立即返回最终的值，而是会返回一个 promise，以便在未来某个时候把值交给使用者。

    var promise = new Promise(function(resolve,reject){
            var greet = "hello  world";
            resolve(greet);  // 成功调用函数
        });
