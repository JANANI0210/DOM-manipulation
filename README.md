# DOM-MANIPULATION USING JS

### AIM :
 
    To create a full screen carousel, featuring a HTML picker on themiddleofthescreen. 
    Upon the user selecting a specific colour, the backgroundcolour of thecurrent carousel slide should turn into that specific colour. 

### ALGORITHM :
    Step 1: Create a new html document and name it as index.html
    Step 2: Create a new assets as folder inside the folder add the create twofolder. 
    Step 3: Name the two folder as CSS and JS inside the folder create script.jsfile.
    Step 4: Link the script tag within the body tag in html by mention the pathinsrc.
    Step 5: Write the Corresponding code in css and js file using the DOMManipulation.
    Step 6: The output will be displayed in the browser screen.
    
### PROGRAM :
  
    index.html
    
        <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Document</title>
    </head>
    <body>
        <input id="picker1" type="color">
        <input id="picker2" type="color">
        <input id="picker3" type="color">
        <button id="less">&lt</button>
        <button id="great">&gt</button>
        <script src="assets/js/script.js"></script>
    </body>
    </html>
    
    script.js
    
    const cp1 = document.getElementById('picker1')
    const cp2 = document.getElementById('picker2')
    const cp3 = document.getElementById('picker3')
    const less =  document.getElementById('less')
    const great =  document.getElementById('great')
    var pos = 0

    var colorsSet = [
        {
            selector:"cp1",
            selectedColor:"#ffffff"
        },
        {   selector:"cp2",
            selectedColor:"#ffffff"
        },
        {   selector:"cp3",
            selectedColor:"#ffffff"
        }


    ]
    // console.log(cp1);
    cp2.style.display = 'none';
    cp3.style.display = 'none';

    less.addEventListener("click",()=>{
         if(pos===0)
             pos = 2
        else if(pos==1 || pos==2)
            pos = pos-1
        const lessSelectorFunc = (pos)=>{
            const currSelector = colorsSet[pos].selector;
            const currColor = colorsSet[pos].selectedColor;
            switch(currSelector){
                case 'cp1':
                    cp1.style.display = 'block'
                    cp2.style.display = 'none'
                    cp3.style.display = 'none'
                    document.body.style.backgroundColor = currColor;
                    break;
                case 'cp2':
                    cp2.style.display = 'block'
                    cp1.style.display = 'none'
                    cp3.style.display = 'none'
                    document.body.style.backgroundColor = currColor;
                    break;
                case 'cp3':
                    cp3.style.display = 'block'
                    cp1.style.display = 'none'
                    cp2.style.display = 'none'
                    document.body.style.backgroundColor = currColor;
                    break;
            }
            // currSelector.style.display='block';



        }
        lessSelectorFunc(pos);

    })

    great.addEventListener("click",()=>{
        if(pos===2)
            pos = 0
        else if(pos===0 || pos===1)
            pos = pos+1        
            const greatSelectorFunc = (pos)=>{
                const currSelector = colorsSet[pos].selector;
                const currColor = colorsSet[pos].selectedColor;
                switch(currSelector){
                    case 'cp1':
                        cp1.style.display = 'block'
                        cp2.style.display = 'none'
                        cp3.style.display = 'none'
                        document.body.style.backgroundColor = currColor;
                        break;
                    case 'cp2':
                        cp2.style.display = 'block'
                        cp1.style.display = 'none'
                        cp3.style.display = 'none'
                        document.body.style.backgroundColor = currColor;
                        break;
                    case 'cp3':
                        cp3.style.display = 'block'
                        cp1.style.display = 'none'
                        cp2.style.display = 'none'
                        document.body.style.backgroundColor = currColor;
                        break;
                }
    }
    greatSelectorFunc(pos);

    })

    console.log(colorsSet);


    cp1.addEventListener("change",(e)=>{
         const color = e.target.value
         //colorsSet.cp1 = color;
         if(colorsSet[0]){
            colorsSet[0].selectedColor = color;
         }
         console.log(colorsSet);
         document.body.style.backgroundColor=color;

    })
    cp2.addEventListener("change",(e)=>{
        const color = e.target.value
        if(colorsSet[1]){
            colorsSet[1].selectedColor = color;
         }

        console.log(colorsSet);
        document.body.style.backgroundColor=color;
    })
    cp3.addEventListener("change",(e)=>{
        const color = e.target.value
        colorsSet.cp3 = color;
        if(colorsSet[2]){
            colorsSet[2].selectedColor = color;
         }
        console.log(colorsSet);
        document.body.style.backgroundColor=color;
    })
    
### OUTPUT :

![Screenshot (415)](https://github.com/JANANI0210/DOM-manipulation/assets/86832944/3ec9c962-281e-49f6-9fdd-259723252a32)

### RESULT :
        Thus, the HTML picker on the middle of the screen. Upon the user selectingaspecific colour is created using javascript and output is verified.
