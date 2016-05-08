# collisiondetection

var puck_x = 210;
var puck_y = 210;
var puck = document.getElementById('puck');
var speed = 50;

puck.style.left = puck_x+'px';
puck.style.top = puck_y+'px';

function logCoordinates() {
    console.log('x:'+puck_x+' y:'+puck_y);
}
function checkCollision() {
    if (puck_x > 250 && puck_x < 350 && puck_y > 150  && puck_y < 250) {
        document.getElementById('gap').style.backgroundColor = 'red';
    }
    else {
        document.getElementById('gap').style.backgroundColor = 'white';
    }
   
};


document.getElementById('right').addEventListener('click', function() {
    puck_x += speed;
    puck.style.left = puck_x+'px';
    logCoordinates();
    checkCollision();
    if (puck_x > 540) {
      puck_x = 510;
    }
    
    
});

document.getElementById('left').addEventListener('click', function() {
    puck_x -= speed;
    puck.style.left = puck_x+'px';
    logCoordinates();
    checkCollision();
      if (puck_x < 50) {
        puck_x = 60;
        
    }
});

document.getElementById('up').addEventListener('click', function() {
    puck_y -= speed;
    puck.style.top = puck_y+'px';
    logCoordinates();
    checkCollision();
      if (puck_y <= 10) {
        puck_y = 60;
    
    }
});

document.getElementById('down').addEventListener('click', function() {
    puck_y += speed;
    puck.style.top = puck_y+'px';
    logCoordinates();
    checkCollision();
      if (puck_y > 340) {
        puck_y = 310;
        
    }
});
