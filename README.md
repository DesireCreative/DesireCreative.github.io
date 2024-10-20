<!DOCTYPE html>
<html lang="en">
  <head>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/p5.js/1.10.0/p5.js"></script>
    <meta charset="utf-8" />
  </head>
  <body>
    <main></main>
    <script>
      let logoImage = "https://i.imgur.com/fRflgW3.png";
	  let rayLogoImage = "https://i.imgur.com/HfwCq8j.png";
      let logo;
	  let rayLogo;
      let button2, button;
      let mouseClick = false;
      let showLogo = true;
      let gamesPageShow = false;
	  let funkyMonkeyIcon;
	  let copyRight = "copyright of desire creative and ray game 2024";
	  let controllerImage = "https://i.imgur.com/X3031nS.png";
	  let controller;
	  let W_W = 1280;
	  let W_H = 720;

      function preload() {
        logo = loadImage(logoImage);
		rayLogo = loadImage(rayLogoImage);
		funkyMonkeyIcon = loadImage("https://i.imgur.com/FJcXedj.png");
		controller = loadImage(controllerImage);
      }

      function setup() {
        createCanvas(1280, 720);
        logo.resize(190, 143);
        gamesButton();
        appsButton();
      }

      function draw() {
        background(204, 204, 204);
		homeButton();
        
        if (showLogo) {
          button2.show();
		  button.show();
		  showLogo = true;
		  rayGameLogo();
        }

        if (mouseClick) {
          button2.hide();
          button.hide();
          showLogo = false;
        }

        if (gamesPageShow) {
          fill(255);
          textSize(32);
          text("Funky Monkey", 260, 157); 
		  image(funkyMonkeyIcon, 256, 316);
		  funkyMonkeyIcon.resize(382, 287);
        }
		drawController();
      }

      function gamesButton() {
        button2 = createButton('Games');
        button2.position(333, 221);
        button2.mousePressed(() => {
          mouseClick = true;
          gamesPageShow = true;
          handleClick();
        });
      }

      function appsButton() {
        button = createButton('Apps');
        button.position(582, 221);
        button.mousePressed(() => {
          mouseClick = true;
          handleClick();
        });
      }
	  
	  function homeButton(){
		let button3 = createButton("");
		button3.position(0, 0); 
		button3.size(logo.width, logo.height); 
		button3.style('background-color', 'transparent');
		button3.style('border', 'none');
		button3.elt.appendChild(logo.canvas);
		showLogo = true;
	  }
	  
	  function rayGameLogo(){
		image(rayLogo, 2/2, 5/2);
		rayLogo.resize(305, 229);
	  }
	  
	  function drawController(){
		image(controller, W_W/2, W_H/2);
		controller.resize(243, 136.7);
	  }

      function handleClick() {
        console.log("Button clicked!");
      }
    </script>
  </body>
</html>