# Light level activated Smart light
The light level activated smart light runs on Arduino UNO and has a 5 Mohm LDR which senses when the ambient room or location's lighting decreases below a certain threshold and then activates a high brightness LED light for a set time. The Smart light also as a motion sensor that has 100 degrees of vision that turns the light on.
```HTML 
<!--- This is an HTML comment in Markdown -->
<!--- Anything between these symbols will not render on the published site -->
```

| **Engineer** | **School** | **Area of Interest** | **Grade** |
|:--:|:--:|:--:|:--:|
| Zach B | Georgetown Day School | Civil Engineering | Incoming Senior

**Replace the BlueStamp logo below with an image of yourself and your completed project. Follow the guide [here](https://tomcam.github.io/least-github-pages/adding-images-github-pages-site.html) if you need help.**

![Headstone Image](logo.svg)
  
# Final Milestone

**Don't forget to replace the text below with the embedding for your milestone video. Go to Youtube, click Share -> Embed, and copy and paste the code to replace what's below.**

<iframe width="560" height="315" src="https://www.youtube.com/embed/F7M7imOVGug" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

For your final milestone, explain the outcome of your project. Key details to include are:
- What you've accomplished since your previous milestone
- What your biggest challenges and triumphs were at BSE
- A summary of key topics you learned about
- What you hope to learn in the future after everything you've learned at BSE



# Second Milestone

**Don't forget to replace the text below with the embedding for your milestone video. Go to Youtube, click Share -> Embed, and copy and paste the code to replace what's below.**

<iframe width="560" height="315" src="https://www.youtube.com/watch?v=gePMNI_Xt3Y" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

For your second milestone, explain what you've worked on since your previous milestone. You can highlight:
- I add a motion sensor to the smart light and switch the LDR to a 2 mohm instead of 5 mohm to demo the light better
- I was most surprised on how simple the updates to the code and adding how the motion sensor was
- The biggest challenged of milestone two was wiring the motion sensor
- A cityscape for the light and a street light frame to hold the smart light

# First Milestone


<iframe width="560" height="315" src="https://www.youtube.com/embed/0gaEWjnTA8Q?si=mm6h9AmEpRWnqAah" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

For your first milestone, describe what your project is and how you plan to build it. You can include:
- The componets currently in use in the Smart light are a Arduino uno board, a high brightness LED, and a 5 Mohm LDR
- After completing the first milestone the progress on the Smart Street Light is it turns the LED on when the ambient light level are at a certain level 
- current challenges are the male to female wires connected to the light are too long and will be replaced with shorter wires 
- My plan is to shorten the male to female wires and test the affects of different Mohm LDR to see what changes they provide

# Schematics 
![Headstone Image](image_2026-07-30-103218151.png)

# Code
Here's where you'll put your code. The syntax below places it into a block of code. Follow the guide [here]([url](https://www.markdownguide.org/extended-syntax/)) to learn how to customize it to your project needs. 

```c++
const int ledpin = 13;
const int lightpin = A2;
const int motionPin = 2;     // PIR sensor output

const int LIGHT = 800;       // Light threshold

void setup() {
  Serial.begin(9600);

  pinMode(ledpin, OUTPUT);
  pinMode(lightpin, INPUT);
  pinMode(motionPin, INPUT);
  delay(30000);  // Start up delay
}

void loop() {
  int lightsens = analogRead(lightpin);
  int motion = digitalRead(motionPin);

  Serial.print("Light: ");
  Serial.print(lightsens);      // prints what the light sensors sees
  Serial.print("   Motion: "); // prints what the motion sensor sees
  Serial.println(motion);

  // Turn on LED only if it is dark AND motion is detected
  if (lightsens < LIGHT && motion == HIGH) {
    digitalWrite(ledpin, HIGH);
    delay(5000);  // keeps the light on for 5 sec
  }
  else {
    digitalWrite(ledpin, LOW);
  }

  delay(500);
}
```

# Bill of Materials
Here's where you'll list the parts in your project. To add more rows, just copy and paste the example rows below.
Don't forget to place the link of where to buy each component inside the quotation marks in the corresponding row after href =. Follow the guide [here]([url](https://www.markdownguide.org/extended-syntax/)) to learn how to customize this to your project needs. 

| **Part** | **Note** | **Price** | **Link** |
|:--:|:--:|:--:|:--:|
| The Most Complete Starter Kit UNO R3 Project| Has all the parts I used for base project with out modifications| 64.99| <a href="https://www.amazon.com/EL-KIT-001-Project-Complete-Starter-Tutorial/dp/B01CZTLHGE/"> Link </a> |
| Digital Multimeter | testing if the wires are live or not | 11.98 | <a href="https://www.amazon.com/Multimeter-Voltmeter-Continuity-Resistance-Electrical/dp/B0CXM242J1"> Link </a> |
| Amazon basics 8 pack 9v alkaline batteries| to power the Digital Multimeter| 12.69| <a href="https://www.amazon.com/Amazon-Basics-Performance-All-Purpose-Batteries/dp/B00MH4QM1S"> Link </a> |
|WWZMDiB 5Pcs AM312 Mini Pir Motion Sensor Module HC-SR312 IR Human Sensor for Arduino| The Motion sensors I used for the second milestone|9.99| <a href="https://www.amazon.com/WWZMDiB-AM312-Motion-HC-SR312-Arduino/dp/B0CCF52DVJ/"> Link </a> |
|Chanzon 20pcs 5537-1 GL5537-1 5mm 2 Ω ohm Photoresistor LDR| The LDR I switched to during milestone 2|5.99| <a href="https://www.amazon.com/dp/B08QS6L7F5"> Link </a> |

# Other Resources/Examples
One of the best parts about Github is that you can view how other people set up their own work. Here are some past BSE portfolios that are awesome examples. You can view how they set up their portfolio, and you can view their index.md files to understand how they implemented different portfolio components.
- [Example 1](https://trashytuber.github.io/YimingJiaBlueStamp/)
- [Example 2](https://sviatil0.github.io/Sviatoslav_BSE/)
- [Example 3](https://arneshkumar.github.io/arneshbluestamp/)

To watch the BSE tutorial on how to create a portfolio, click here.
