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
