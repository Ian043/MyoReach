# MyoReach
By Ian Kim

### Introduction
  5000 years. That's roughly how long we've been working with mechanics, which is minuscule compared to the hundreds of millions of years nature has had in perfecting biomechanics. MyoReach is a biomimetic robotic hand that utilizes a small understanding of our own biomechanics, muscles and tendons. My inspiration and interest for prosthetics all started with a fictional character. Spider-Man, a hero recognized by most of the world, is the embodiment of community, innovation and valor. Whilst playing the Spider-man PS4 game, where Peter Parker (Spider-Man) blends technology and empathy to create a positive impact. I was inspired by this idea of helping people who have lost a part of themselves serving, from disease, genetics and unfortunate accidents through prosthetics. 

  I started working on my [first prototype](https://drive.google.com/file/d/191Oo7Ml_8PpCRKEl4oRl7nUMozBNuhZv/view?usp=drivesdk), a folding retractable mechanical arm with three fingers/claws. In the first iteration, the fingers/claws were directly attached to the servos for predictable and unhindered movement. Though it was able to grab objects with stability, I felt it lacked the human dexterity required for more delicate tasks. [See performance here](https://drive.google.com/file/d/1FCV47Mdx2rV2zw4nP2uJiQcjS7VA9Hfq/view?usp=drivesdk). I also considered how the design's appearance might affect its approachability. What is the buyers main concern when purchasing this type of product? When it comes to restoring functionality that people have lost, most people don't dwell on effective, they want familiar. The second iteration would begin with hopes of designing a biomimetic hand, that could function similarly to my own and successfully handle a range of everyday objects. Keeping my inspiration at heart, a vital goal of this project was keeping it affordable yet capable.

### Features:
- Controlled by Arduino microcontroller
- Servo-driven finger movements
- Tendon-like pulley mechanism
- Rubber grip pads ("skin")
- Approachable aesthetic
- 5V-7V and 2.5A-5A

### Key Code Snippets:

#### Servo Setup
This section sets up the servos and buttons that control the fingers. Each servo is attached to a pin, and each button is assigned to an input pin on the Arduino:

```cpp
#include <Servo.h>  // Include the Servo library to control the servos

// Declaring 5 Servo objects, one for each finger
Servo finger1;
Servo finger2;
Servo finger3;
Servo finger4;
Servo finger5;

// Assigning each button to a specific pin on the Arduino
int button1 = 2;
int button2 = 3;
int button3 = 4;
int button4 = 5;
int button5 = 6;

void setup() {
  // Attaching each servo object to a PWM pin on the Arduino
  finger1.attach(9);  
  finger2.attach(10);
  finger3.attach(11);
  finger4.attach(12);
  finger5.attach(13);

  // Each button pin set as an input
  pinMode(button1, INPUT);
  pinMode(button2, INPUT);
  pinMode(button3, INPUT);
  pinMode(button4, INPUT);
  pinMode(button5, INPUT);
}
```
#### Finger Control Logic
This loop continuously checks if a button is pressed. When a button is pressed, the corresponding finger closes. When the button is released, the finger opens:
```
void loop() {
  // Finger 1 control
  if (digitalRead(button1) == HIGH) {  // Button pressed
    finger1.write(0);  // Close finger
  } else {  // Button not pressed
    finger1.write(180);  // Open finger
  }

  // Finger 2 control
  if (digitalRead(button2) == HIGH) {
    finger2.write(0);  // Close finger
  } else {
    finger2.write(180);  // Open finger
  }

  // Finger 3 control
  if (digitalRead(button3) == HIGH) {
    finger3.write(0);  // Close finger
  } else {
    finger3.write(180);  // Open finger
  }

  // Finger 4 control
  if (digitalRead(button4) == HIGH) {
    finger4.write(0);  // Close finger
  } else {
    finger4.write(180);  // Open finger
  }

  // Finger 5 control
  if (digitalRead(button5) == HIGH) {
    finger5.write(0);  // Close finger
  } else {
    finger5.write(180);  // Open finger
  }
}
```
### Components:
- Custom plastic molded hand structure
- Arduino Uno R4 WiFi
- Liquid cast elastic Platinum Silicone rubber
- Momentary push button switch
- Jumper wires
- Stainless steel wire

### Cost Breakdown:
- **Arduino Uno R4 WiFi** | 1 unit | $24
- **Servos (Miuzei MG996R)** | 5 servos | $23
- **Stainless steel wire rope** | 1.3 meters | $0.20
- **Silicone liquid** | 2 oz | $2.4
- **Jumper wires** | 15 wires | $1.50
- **Polymorph biodegradable thermoplastic** | 15 oz | $16
---
**Total Approx. Cost: $67**


### Design and Creation Process:
  As with all inventions, the first step in my project was the design. I sketched a [blueprint](https://drive.google.com/file/d/1KAcDJhHuzG2HDkgqS8i72pVI0NaVCGIB/view?usp=drivesdk) of what I hoped the final product would look like. I started working on the code I would upload to the arduino, making sure each servo would efficiently operate the fingers in accordance with button signals. After the measurements were taken, I molded [five fingers](https://drive.google.com/file/d/1wxc7gABFK62nokfQz6sR0y9gMw02pZmb/view?usp=drivesdk) with a supporting wire in the middle of each finger segment. These wires were separate from the ones used in the pulley mechanisms, which were positioned facing inward. Each finger had three segments with a gap of half a milimeter for range of motion. The fingers were attached to the [top palm frame](https://drive.google.com/file/d/1mBh9lKcbcAfAKHdrXKPlzIwo4kGc7Mls/view?usp=drivesdk) and the servo wires fastened as to esure the pulley wires remained straight and didn't bend during servo movement. The [bottom palm frame](https://drive.google.com/file/d/18sPkFjZ_lt4Ik2g7O8LM7kWzrUy4z7dI/view?usp=drivesdk) was molded and assembled, keeping the palm itself hollow and light. With the frame complete, I began testing [servo/dexterity](https://drive.google.com/file/d/1o4LcCowCidxtdcKZj3kutI4AjlL-rLgh/view?usp=drivesdk). The pulley wires that extended beyond the palm frame were fastened with straws, maintaining predictable movement of the fingers. I then began [testing each finger individually](https://drive.google.com/file/d/1Nwwm9ss7vFfqEPAdvjBI0EOlBfXAxrn-/view?usp=drivesdk). The arduino was hooked up with accompanying momentary push buttons for each finger. To make control easier, I attached all five buttons to a small carboard box and labeled them as to not get confused during testing. [Check the setup here](https://drive.google.com/file/d/19v2fjyHqynihuisz0XAgHlieq01nuYPd/view?usp=drivesdk). The first object handled in testing was a rectangular box of straws. [See testing video here](https://drive.google.com/file/d/1jV3LzWMtzXkp8CmdkTSbtoonH-oE5Y1M/view?usp=drivesdk). The hand was able to pick up the box and gently set it down. The smooth and responsive movements of the servo-driven fingers managed without applying excessive force. The second phase of testing was with a heavier and larger object, a shaker bottle. The hand had failed to successfully grasp the item and so I looked back at my blueprint. Though the hexagonal texture application was an exciting concept, it would be little to no added value considering the tacky texture of the silicone rubber. I poured out two ounces of liquid silicone rubber and let gravity expand it out. [View finished texture here](https://drive.google.com/file/d/1goqixkMn51Jm6vPPqFrcDRn8eYvwIYZO/view?usp=drivesdk). The silicone was then cut accordingly and molded to the tip of each finger and the palm, as glue didn't apply well, to the silicone. 
[See layout here](https://drive.google.com/file/d/1A92DBwEOgFQ5kPHDrchAwH5kXuvd0dji/view?usp=drivesdk). The silicone skin has vastly improved the hand's friction and was able to grab the shaker with ease. [See testing video here](https://drive.google.com/file/d/1jS7FxoiRBOZUIswcqvdePFKeaTsZOwDr/view?usp=drivesdk). The heaviest object to be successfully lifted was a 750 ml bottle of cleaning spray, which definitely wiped my expectations [Scoff at pun and see the action here](https://drive.google.com/file/d/1nCUwnhEs2CO1R_GBKnQ5s0hsF5HLF5ey/view?usp=drivesdk). To conclude my tests, I made a few friendly gestures (and a few unprofessional ones off record) [See here](https://drive.google.com/file/d/1J6GY3HbRTU-hsjta2yf4Iu-f0Sr55E1q/view?usp=drivesdk). 

### The End?:

  After 67 dollars, a mess of plastics and wires, an impatient passion for creative action, two weeks and 17 unrelated hours replaying Spider-Man for the nostalgia, the project was complete. MyoReach, a humble beginning accompanying my ongoing engineering degree was a success in my opinion, being able to manipulate the weight and size range of most household items. It's also to say that almost all of the materials used are reusable/recyclable with the exception of the plastic parts of the jumper wires. The heart of this project wasn't testing academic prowess or fulfilling a requirement, it was the exploration of resilience. At the core of science is exploration, curiosity, shock and awe, a persistence built atop trial and error to be backed by the beauty of what we can reach for. Continually striving for improvement and for the betterment of people's lives is the true spark of innovation. Our reach should never settle on anything and be content with 'good enough', for once we grasp anything fully, we stop reaching.

### Reaching Farther
  Innovation is improving whether our designs work optimally or don't. The possibilities for future improvements are vast.

- Enhanced dexterity: Improvements on finger precision by incorporating more sensors/feedback systems
- Material: Exploring advanced materials such as lightweight carbon fiber, grid pattern skin for better grip
- Wireless control: Implementing Bluetooth or WiFi remote control of the hand
- Electromyography (EMG): Integrating electrodes and EMG controllers for natural movements in response to arm muscles
- Full arm integration: Expanding to include the wrist and full arm with rotational capabilities
- Touch/haptic feedback: Touch or pressure based sensors for better grip strength control
- Calculations: This second prototype focused on design and functionality. Future iterations will include torque, power efficiency, and material stress calculations.
- Energy: The hand currently run off a type c usb wall charger cable. Finding an affordable and rechargable alternative power source is essential for real life applications.
