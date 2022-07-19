const paintBlock = document.querySelector('.paint')
paintBlock.width = window.innerWidth
paintBlock.height = window.innerHeight

const c = paintBlock.getContext('2d');



class Circles {
    constructor(x, y, radius, dx, dy, colorsArr){
        this.x = x;
        this.y = y;
        this.radius = radius;
        this.dx = dx;
        this.dy = dy;
        this.colorsArr = colorsArr
    }
    render(){
        c.beginPath();
        c.arc(this.x, this.y, this.radius, 0, Math.PI * 2, false);
        c.strokeStyle = '#333';
        c.fillStyle = this.colorsArr
        c.fill();
        c.stroke();
        this.updateValue();
    }

    updateValue(){
        if(this.x + this.radius > window.innerWidth || this.x - this.radius < 0 ){
            this.dx = -this.dx;
        }
        if(this.y + this.radius > window.innerHeight || this.y -this.radius < 0){
            this.dy = -this.dy
        }
    this.x += this.dx;
    this.y += this.dy;
    }
}  

randomNum = (min, max) => Math.floor(Math.random() * (max - min +1)) + min;

const colorsArr = [
    '#e26a6a',
    '#e94a6a',
    '#FF00FF',
    '#FFFF00',
    '#008080',
    '#7fff00',
    '#dc143c',
    '#7fff00',
    '#008b8b',
    '#f4a460'
];

const circleArr =[];


for(let i = 0; i < 1000; i++){
    let radius = 10;
    
    let x = Math.random() * (window.innerWidth - radius + 2) + radius;
    let y = Math.random() * (window.innerHeight - radius + 2) + radius; 

    let dx = (Math.random() - 0.5) * 2;
    let dy = (Math.random() - 0.5) * 2;
    const colorIndex = randomNum(1, colorsArr.length - 1) 
    circleArr.push(new Circles(x, y, radius, dx, dy, colorsArr[colorIndex]));

}
console.log(circleArr)


function animation(){
    requestAnimationFrame(animation);

    c.clearRect(0, 0, window.innerWidth, window.innerHeight)
    for (let i = 0 ; i < circleArr.length; i++){
        circleArr[i].render()
    }

}
animation();
