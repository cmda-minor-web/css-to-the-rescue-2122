# Rubiks Cube README

# Week 1

**Day 1**

On day 1 of this course, we were given a list of assignments which we could
chose from and were given a presentation with further detail of the assignments.
Now, since I am not that well experienced with CSS, the most logical thing to do
was to chose the "easiest" assignment. But I didn't do that, I wanted to challenge
myself and chose to do RubiksCube assignment. I chose it because it spoke to me and the other assignments seemed less fun to me.

So, where to start? The first thing for me was to sketch my ideas,
I had to think about how to create a cube, how to rotate it and a lot more challenging things.

In the first day, I had to create a single cube, which at it self was new for me. I created a cube using < ul > and < li > items.
It didn't quite work out too well and at the end of day 1 i had 6 list items that were placed in a sort of cube shape but not correct yet.
![First Sketches](https://github.com/ppijn/rubiks-cube/blob/Rubiks-Cube-version-4-day-1/rubikscube/img/firstsketch.jpg)
![First Sketches](https://github.com/ppijn/rubiks-cube/blob/Rubiks-Cube-version-4-day-1/rubikscube/img/lisketch.jpg)

**Day 2**  
Day 2 went a lot better, I managed to get a cube shape and copied them to make 3. I gave it a styling and called it a day. I also calculated how many turns i would need to have each side be at least turned once.
![image cube day 2](https://github.com/ppijn/rubiks-cube/blob/Rubiks-Cube-version-4-day-1/rubikscube/img/cubeday2.jpg)
Now the next challenge was bigger. Create 26 cubes and position them correctly...

```
Some challenges this day:
- create a correct cube
- create a 'sticker' like style

Some insights:
- use :before to create the sticker like overlay
```

I will show you the pictures of my progress and challenges that I had. You can find all my versions of my cube in the branches of my github page.

**Picture week 2 day 1**
![image cube day 3](https://github.com/ppijn/rubiks-cube/blob/Rubiks-Cube-version-4-day-1/rubikscube/img/cubeday3.jpg)

In week 2, I was positioning the cubes to its corresponding position in the rubiks cube. Using rotate and transform I managed to get each block in the correct spot. However, I did this wrong at first, I had created a cube but not with the correct transformations, my block were placed randomly and had no structure and thinking behind it.
![Perspective Cube](https://github.com/ppijn/rubiks-cube/blob/Rubiks-Cube-version-4-day-1/rubikscube/img/perspsketch.jpg)

```
Some challenges this day:
- positioning the cubes correctly
- starting over again for the first time

Some insights:
- learn about the perspective
- learned more about the selectors
```

**Pictures week 2 day 2**
![image cube day 4](https://github.com/ppijn/rubiks-cube/blob/Rubiks-Cube-version-4-day-1/rubikscube/img/cubeday4.jpg)

In week 2 day 2, I picked up were i left with the cubes, I still needed to do the center pieces of the cubes. I managed to put the cubes in the center pieces and when i had that, I wanted to add the 'Rotate Cube' funciton with some sort of interface for the rotations. In the picture you can see both the filled in cube and the labels for the rotations using input type: radiobox.
At the end of the day, because i wasn't doing the positioning correctly, I had 4 double blocks in my cube... It was extremely challenging for me to find these double cubes. I wrote them down and managed to find the double cubes after 2 hours.

![Double cubes](https://github.com/ppijn/rubiks-cube/blob/Rubiks-Cube-version-4-day-1/rubikscube/img/doublecube.jpg)

```
Some challenges this day:
- adding the animations for rotating the cube to the labels
- letting the icon switch from the 'pause' to the 'play' icon when clicking

Some insights:
- learned about input elements for the first time
- managed to get the cube to rotate with the corresponding arrows

```

**Pictures week 3 day 1**

![image cube day 5](https://github.com/ppijn/rubiks-cube/blob/Rubiks-Cube-version-4-day-1/rubikscube/img/cubeday5.jpg)
![image cube day 6](https://github.com/ppijn/rubiks-cube/blob/Rubiks-Cube-version-4-day-1/rubikscube/img/cubeday6.jpg)
![Correct x y z axis](https://github.com/ppijn/rubiks-cube/blob/Rubiks-Cube-version-4-day-1/rubikscube/img/xyzsketch.jpg)

I made 26 cubes and learned how to position them correctly, giving them a rotate and transform element. You first needed to rotate the cube so that the axis was pointing to the "center" cube of the correct layer as seen in the picture below.
I was thinking to myself what the best way to do it would be. And I came to the conclusion it is better to do it in layers then doing the corners first, then the side pieces etc. Doing it layer by layer helped me to do it vary easy. I used custom properties for the rotations of the cube to make it easier and make the code prettier.
It only took me 30 minutes to position them correctly, and then the next hard challenge came... Rotating the layers of the cube. I knew i had to have at least 12 rotations in order for it to look like a working cube. I managed to add the labels for the rotations of the cube layers but was struggeling together with the Friday Cry Club boys to make the cube rotate correctly. With some help of Sanne to give me a push in the right direction, i managed to easily rotate the bottom layer of the cube. like this:

![turns for the cube](https://github.com/ppijn/rubiks-cube/blob/Rubiks-Cube-version-4-day-1/rubikscube/img/turnsketch.jpg)

```
#right-bottom:hover ~ section ul:nth-child(-n + 9) {
  --rY: 90deg;
}
```

Let me explain this line of code (which is the foundation for the other layers too)
If you read the selector correctly, it says: 'Select the first 9 ul items of the section while hovering on the right bottom arrow' and we gave this the element of rotate the Y axis 90 degrees, meaning it turns to the right. -90 would mean it will turn to the left. I repeated this for all the other layers and came to the next issue. Horizontal rotations were easy since thats the way i positioned my cubes. The Bottom layer were cubes 1-9, the Middle layer 10-17 (Since the center cube is unnecessary) and the Top layer 18 - 26.
But how do we turn the Vertical layers? Since this would cause problems due to the positioning. The day after i tackled this problem further.

```
Some challenges this day:
- correctly positioning the cube
- adding rotations to the cube
- Getting the vertical layers to rotate

Some insights:
- custom properties are your friend and came in very usefull
- Its not hard if you think about it logically

```

**Pictures week 3 day 2**

In week 3 day 2 I was going to fix the vertical turn issue. Basically, to turn the first veritcal layer, you would need the first 3 cubes of every layer. If i wrote it down in code, it would look like this:

```
#up-right:hover ~ section ul:nth-child(3n) {
  --rX: 90deg;
}
```

The thing i found was causing the problem, was the fact that i didnt have the middle center cube... Once I went back in my code to add that cube, it all worked perfectly and I was able to do the other rotations pretty easily as well.

The next part of the day for me was creating some nice features like dark-mode etc.
I managed to get this done after some challenges like, if i want everything to change, do I put the input before the main or in. After having looked up different ways to do it and getting some help from my teacher I managed to fix it using this selector:

```
#mode:checked ~ *, #mode:checked ~ * * {
  ...
}
```

I also added a button to switch of the texture that was on the cube.

```
Some challenges this day:
- Making the cube layers rotate
- Finding out why it didnt work.
- Getting the dark-mode to work
- Getting the texture switching mechanism to work

Some insights:
- I learned a lot about selectors and how to read them
- Include every cube.

```

![Final Cube](https://github.com/ppijn/rubiks-cube/blob/Rubiks-Cube-version-4-day-1/rubikscube/img/finalcube.jpg)

**Pictures week 4 day 1 & 2**

Some other feature that I wanted to add was the ability to change to colour of the cube. I was looking everywhere on the internet to find if it was possible to change the color of something using only css. I found that there was a special input type called: Color, and using that, you get a special color picker. However, you can change the color of the input, but it doesnt do anything. In order to get the output of the input and then put it in the custom property of the cube color you had to use javaScript.
I thought it wasnt going to be possible. I later found a CodePen that used the input of color, and made it cover the whole screen and use the element: mix-blend-mode: color; to set it to as an overlay. In my head I found the perfect solution to the problem. I made the input bigger, had it cover the cube and i indeed was able to change the color of the cube. However, it stayed still while the cube rotated and when the layers rotated it only looked weird. But to my it was a good sign.

During the theme sessions of class, I wasn't really paying attention because in my head I was only thinking of how do I get this to work...
I came up with the idea to put the input tye="color" inside of the Li items in that contain the cube color. And indeed, the input moved together with the rotations and was working as an overlay function. I put the input in all of the cubes and set a value on them so that the starting colors were still the original cube colors.

```
<li>
            <input type="color" id="left-face" name="cube" value="#009b48" />
          </li>
```

The last day consisted of me fixing the responsiveness and changing the arrow sections to fit in a grid and making them responsive too.

```
Some challenges this week:
- adding the color function to the cube
- making it responsive

Some insights:
- I learned a new input type
- I failed to do it so that once you select one cube to change the color, it doesnt change the whole face of the cube. If i were to have more time I could fix it but for me this is already a great achievement

```

I learned so much during this course!!
From not knowing the basic css features to knowing what custom properties are, how to make a cube, adding animations, adding rotations, transformations, radioboxes, checkboxes, how to make it responsive, to working with the calc() elementc etc. etc. etc.

I learned a lot!!
