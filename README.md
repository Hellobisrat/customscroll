# custom scroll project

first getting the height

height = document.documentElement.scrollHeight - document.documentElement.clientHeight 


how much scrolled

howMuchScrolled = document.body.scrollTop  or document.documentElement.scrollTop;


defining scroll percentage

ScrollPercentage = howMuchScrolled/height*100


# using useEffect it add scroll event listener and remove the event listner

useEffect(() => {
  // Add the scroll event listener
  window.addEventListener('scroll', handleScrollPercentage);

  // Cleanup function to remove the event listener
  return () => {
    window.removeEventListener('scroll', handleScrollPercentage);
  };
}, []);


# we can also define the scrollPercentage 

function handleScrollPercentage() {
  const scrollTop = window.scrollY;
  const docHeight = document.documentElement.scrollHeight - window.innerHeight;
  const scrollPercentage = (scrollTop / docHeight) * 100;

}


# setting the progress container width with scroll percentage
<div 
      className='current-progress-bar'
      style={{width:`${scrollPercentage}%`}}>
      </div>

      
