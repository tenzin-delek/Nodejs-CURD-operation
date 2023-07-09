const fs = require('fs');

//create file
var pytxt = 'This is new python string.'
fs.writeFile('python.txt',pytxt,(err)=>{
    if(err) throw err;
});

//Reading file
fs.readFile('python.txt',(err,data)=>{
    var oldString = String(data);
    //Updating file
    var newString = oldString.replace('old', 'new');
    console.log(newString); 
    fs.writeFile('myText.txt',newString,(err)=>{
        console.log('sucessfully updated!')
    });
    //Deleting file
    fs.unlink('python.txt',()=>{
        console.log('Python deleted')
    });
});
