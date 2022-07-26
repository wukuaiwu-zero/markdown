### String字符串

    This is code 🌐

    const personnel='Jonas'
    const company='Wink Fo Internet Company'

    personnel[0]  // 'p'
    'Marry'[0]  // 'M'
    personnel.length  // 5

    personnel.indexOf('o')  // 1
    personnel.lastIndexOf('o')  // 1
    personnel.indexOf('nas')  // 2

    personnel.slice(2)  // 'nas'
    personnel.slice(1,3)  // 'ona'
    personnel.slice(-2)  // 'as'
    personnel.slice(1,-1)  // 'ona'

    personnel.toLowerCase()  // jonas
    personnel.toUpperCase()  // JONAS
    'Jonas'.toUpperCase()  // JONAS
    ' Jonas '.trim()  // Jonas

    const a = 'first+second+third'
    a.split('+') // ['first','second','third']

    const number = '13563448569'
    const head= number.slice(0,3)
    const foot= number.slice(8)
    const fainaly = head+foot.padStart(8,'+')
    fainaly // '135+++++569'

字符串方法概览:  
 1.字符串.lenght为字符串长度  
 2.字符串+[]下标为某个字符  
 3.indexOf()查找字符串中首次出现的位置  
 4.lastIndexOf()查找字符串中最后出现的位置  
 5.indexOf()可查找连贯的多个字符  
 6.slice()传入一个数字则从传入数字的位置截取至最后  
 7.传入两个数字则截取数字之间的字符  
 8.传入负数则从后截取至最后一位  
 9.传入正数和负数则从正数位置截取至负数位置  
 10.toLowerCase()将该字符串全部小写  
 11.toUpperCase()将该字符串全部大写  
 12.trim()将字符串的首位空格去除  
 13.split()将指定字符截取并将结果以数组形式呈现  
 14.padStart()传入两个参数分别为将该字符串填充至多少位和填充的字符  