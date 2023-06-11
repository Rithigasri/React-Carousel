# EXPERIMENT 07:DEVELOP A CAROUSEL USING REACT FRAMEWORK

## AIM:
To develop a carousel using react framework.
## ALGORITHM:
1. Define a state variable to track the active slide index.
2. Render a container element with the desired layout for the carousel.
3. Map over an array of slide data and render each slide component, passing the necessary props such as image, title, or content.
4. Implement functions to handle previous and next slide actions, updating the active slide index accordingly.
5. Add navigation controls (e.g., buttons or indicators) that trigger the previous and next slide actions when clicked.
## PROGRAM:
```
DEVELOPED BY:RITHIGA SRI.B
REGISTER NUMBER:212221230083
```
### Carousel.js
```
import React from 'react';
import './Carousel.css';

function Carousel() {
  const [currentImage, setCurrentImage] = React.useState(0);

  const images = [
    'https://i.pinimg.com/236x/e0/dc/7e/e0dc7e9d2f900b5d6ed75531ea2b618d.jpg',
    'https://i.pinimg.com/236x/da/b2/43/dab243211b6c63019622db5760db6fd4.jpg',
    'https://i.pinimg.com/236x/37/e3/ab/37e3abb2741a1b86f3841a39c5ea751f.jpg',
    'https://i.pinimg.com/236x/8a/7d/9e/8a7d9eb25c5444329caffe1bdf52c43b.jpg',
  ];

  const handlePrevClick = () => {
    setCurrentImage((prevIndex) => (prevIndex > 0 ? prevIndex - 1 : images.length - 1));
  };

  const handleNextClick = () => {
    setCurrentImage((prevIndex) => (prevIndex < images.length - 1 ? prevIndex + 1 : 0));
  };

  return (

   <body>
    <h1>CAROUSEL IN REACT</h1>
    <div className="carousel">
        
      <button className="arrow left" onClick={handlePrevClick}>
        &lt;
      </button>
      <img src={images[currentImage]} alt=" "/>
      <button className="arrow right" onClick={handleNextClick}>
        &gt;
      </button>
    </div>
    </body>
   
  );
}

export default Carousel;
```
### Carousel.css
```
body {
    background-color: #000;
    margin: 0;
    padding: 0;
  }
  
  .App {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
  }
  
  .carousel {
    display: flex;
    justify-content: center;
    align-items: flex-start; /* Lifts up the image */
    position: relative;
    height: 500px;
    width: 500px;
    overflow: hidden;
  }
  
  .carousel img {
    height: 100%;
    width: 100%;
    object-fit:contain;
    box-shadow: 0px 4px 10px red;
  }
  
  .arrow {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    background-color: transparent;
    border: none;
    outline: none;
    font-size: 2rem;
    color: #fff;
    cursor: pointer;
  }
  
  .arrow.left {
    left: 10px;
  }
  
  .arrow.right {
    right: 10px;
  }
  h1{
    color:white;
    text-align: center;
  }
```
### App.js
```
import React from 'react';
import Carousel from './Carousel';

function App() {
  return (
    <div className="App">
      <Carousel />
    </div>
  );
}

export default App;
```
## OUTPUT:
![image](https://github.com/Rithigasri/React-Carousel/assets/93427256/3f8ec185-300e-4149-a525-7c1f2c5b05c6)

## RESULT:
Thus, a carousel using react framework is developed successfully.
