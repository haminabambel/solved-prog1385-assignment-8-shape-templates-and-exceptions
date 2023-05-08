Download Link: https://assignmentchef.com/product/solved-prog1385-assignment-8-shape-templates-and-exceptions
<br>
This set of assignments (A-04, A-07 and A-08) are meant to give you practice (once again) at developing class definitions from scratch – but in this final installment – you will be adding an exception handling strategy as well as templates to your existing classes.  The set of activities are broken down into a 3 stages.

<ul>

 <li>A-04 : Gets you to develop 3 classes (with inheritance and polymorphism) as well as a test harness</li>

 <li>A-07 : Gets you to use some operator overloading</li>

 <li>A-08 : Gets you to develop some template functions and exception handling</li>

</ul>




<h1>Commenting in Assign-04, Assign-07 and Assign-08</h1>

In order to give you practice creating and writing DOxygen style comments – I want you to comment these 3 assignments using DOxygen.  This means that all of your class header and method header comments must be written so that DOxygen can extract them and produce the set of online documentation.  As well, I want you to also have commented all of the different class’ datamembers and constant values (if any) to also be extracted by DOxygen.  You will want to revisit the DOxygen-Dog example from Module-06 to remind yourself how this is done.  One final DOxygen expectation … I want you to also have a main project page for the <strong>Shapes</strong> project.  You can place whatever you want on this main project page, but remember that the purpose of this page is to inform the reader about the project – what is the project all about? What is it modelling? Perhaps you could also tell the reader about what underlying OOP concepts and techniques are being used in the implementation?




<h1>STEP 1 – Connecting to your Source Repository and Extracting your Starting Point</h1>

<ol>

 <li>Since this exercise is based upon SM-03 – all you need to do is to sign-out your existing Shape code from your repository

  <ol>

   <li>Create a directory on the local machine – e.g. C:SETRepo</li>

   <li>Connect to your repository in the cloud (remembering your repository’s URL and your login credentials) using the Tortoise SVN client and perform an SVN Checkout.  What you should notice is that you have signed out your DisneyCharacter solution as well as your Shapes solution.</li>

  </ol></li>

 <li>If you like you can erase the DisneyCharacter subdirectory as you won’t be modifying that source in this exercise</li>

 <li>Once you have the Shapes solution – you are ready to begin this exercise … so let’s get into the requirements …</li>

</ol>







<h1>STEP 2 – The Requirements and Programming</h1>

In this exercise, you will take your existing classes from A-07 and add to them.  Also in this stage you will create a new class called <strong>CircleSquare</strong>.  An object of this type will be created whenever a Circle shape is added to a Square shape (or vice-versa) … if the conditions are right !!   There are 2 possible renderings of a CircleSquare object – depending on how they are created:

<ul>

 <li>You could have an instance of this object named “Circle-Square” which is created when a square object is being added to a circle object (see Figure 1)</li>

 <li>You could have an instance of this object named “Square-Circle” which is created when a circle object is being added to a square object (see Figure 2)</li>

</ul>










Figure  1                                 Figure  2

<h2>The Shape Class</h2>

<ul>

 <li>The Shape class should now also accept the names “<strong>Circle-Square</strong>” and “<strong>Square-Circle</strong>” as 2 more allowed shape names</li>

</ul>




<h2>The CircleSquare Class</h2>

<ul>

 <li>… Remember that this class is a child of the Shape class</li>

 <li>The class has the following data members o sideLength

  <ul>

   <li>a float data-type used to hold the side-length value (in centimeters) for the square</li>

   <li>allowed values are greater than or equal to 0.00 o radius</li>

   <li>a float data-type used to hold the circle’s radius value (in centimeters) &#x25aa; allowed values are greater than or equal to 0.00</li>

  </ul></li>

</ul>




<ul>

 <li>The class should have the following methods o SPECIAL NOTE</li>

</ul>




<ul>

 <li>When a circle-square object is being instantiated where a circle is being added to square – the name of the resultant object is “Square-Circle”</li>

 <li>When a circle-square object is instantiated where a square is added to a circle – the name of the resultant object is “Circle-Square”</li>

</ul>

<ul>

 <li>a constructor which takes values for the colour of the circle-square, its sideLength, the radius of the circle as well as the object’s name / type

  <ul>

   <li>need to ensure that the sideLength value is valid …</li>

   <li>need to ensure that the sideLength value is greater than or equal to the diameter (twice the radius) of the circle – otherwise, set the sideLength to 1.5 times the diameter of the circle</li>

   <li>need to ensure that the name is one of Circle-Square or Square-Circle</li>

   <li>no other input validation is necessary in this constructor o a default constructor</li>

   <li>sets the sideLength to a value of 0.00, the radius to a value of 0.00 and the name to “Circle-Square” and the colour to “undefined”</li>

  </ul></li>

 <li>a destructor that states “Closing the Circle-Square Ranch …”</li>

 <li>accessor for the data members o mutator for the data members

  <ul>

   <li>your mutators do not need to pass back a succeed / fail status</li>

   <li>but they do need to validate the input to ensure that it is proper for that data member and if it is not, then leave the attribute as it was</li>

   <li>also remember about the special validation between the sideLength and radius of the circle &#x263a; o since the CircleSquare inherits from Shape, it will need to implement the Perimeter() and Area() methods</li>

   <li>if the object is a Circle-Square – then the formula you implement is for the circle</li>

   <li>if the object is a Square-Circle – then the formula you implement is for the square o you will also need to implement the OverallDimension() method in this class</li>

   <li>as you will notice from the sample output below – the CircleSquare class is special</li>

   <li>depending on how it is created, it is either called a Circle-Square or a Square-Circle. The first shape in its name is the primary shape while the second part of its name indicates the secondary shape &#x25aa;        in implementing the OverallDimension() method – please <u>only implement it for the primary shape</u> o         a method called Show(void) which prints out the shape’s name, colour, radius, perimeter and area as in the following examples :</li>

  </ul></li>

</ul>

<u>Shape Information</u>

Name            : Circle-Square

Colour          : blue

<u>Circle</u>

Radius        : 7.50 cm

Circumference : 47.12 cm

Area          : 176.71 square cm

<u>Contained Square</u>

Side-Length   : 10.50 cm

Perimeter     : 42.00 cm

Area          : 110.25 square cm




<u>Shape Information</u>

Name            : Square-Circle

Colour          : orange

<u>Square</u>

Side-Length   : 10.50 cm

Perimeter     : 42.00 cm

Area          : 110.25 square cm

<u>Contained Circle</u>

Radius        : 3.75 cm

Circumference : 23.56 cm

Area          : 44.18 square cm




<ul>

 <li>Note that part of the CircleSquare’s output is to also show the perimeter and area for the contained shape (i.e. the secondary shape of the object)

  <ul>

   <li>How can you do this you ask ? Easy ! You’ll need to know what type (CircleSquare or</li>

  </ul></li>

</ul>

SquareCiricle) object you are dealing with to know what the “contained” shape is

o     CircleSquare contains a square o        SquareCircle contains a circle

<ul>

 <li>And you’ll need to implement a method to determine the Perimeter() and Area() of the contained shape</li>

 <li>Add the following methods to this class – watch best practices !! o An overloaded + operation</li>

</ul>

<ul>

 <li>When adding one circle-square to another, the resultant circle-square will take on the colour of the left-hand operand (the LHS)</li>

 <li>The resultant radius and sideLength are the sum of the left and right operand’s radii and sideLengths o An overloaded = operation – again following best practices</li>

</ul>




<u>The Circle Class</u>

<ul>

 <li>No changes</li>

</ul>




<h2>The Square Class</h2>

<ul>

 <li>Add the following methods to this class – watch best practices !! o Another overloaded + operation

  <ul>

   <li>Which will be called when the left-hand operand is a square, and the right-hand operand is a circle – this overloaded operator produces a circle-square object (the type is Square-Circle)</li>

  </ul></li>

 <li>This means that the Square class needs to know about the Circle class and the CircleSquare class … hmmm …

  <ul>

   <li>When adding a circle to a square, the resultant circle-square will take on the colour of the square</li>

   <li>The resultant circle-square object will have its sideLength be that of the square (the LHS) and its radius be that of the circle (the RHS)</li>

   <li>It is important that this overloaded + operator check to make sure that sideLength is greater than or equal to the <strong><u>diameter</u></strong> of the circle (remember that the diameter is twice the radius) – if it is not, then throw an exception (can just be a string if you like) from this overloaded operator</li>

  </ul></li>

</ul>







<h2>The myShape Main</h2>

<ul>

 <li>Modify your testHarness to create the following shapes o CircleSquare shape called “playARoundSquare” – instantiated with the default constructor of the CircleSquare class</li>

 <li>Add the following template functions to your myShape source module o CombineShape() which is capable of taking 2 objects of the same shape class and combining them (using the</li>

</ul>

“+” operation) and returning the new resultant shape o CombineDifferentShape() which is capable of taking a square object, a circle object and produces a circlesquare object (using the new “+” operation developed in the Square class)

<ul>

 <li>Change your previous code which added square1 to square2 to use the CombineShape() template function instead o Make sure that playASquare is set to the result from this template function call</li>

 <li>Add the following calls to the end of your program o             Call the CombineDifferentShape() template with square2 and round1 objects in order to produce and set the playARoundSquare object values             (i.e. we want square2 + round1)

  <ul>

   <li>If no exception resulted – then print out the particulars of playARoundSquare</li>

   <li>If an exception occurred – then</li>

  </ul></li>

 <li>print the exception message</li>

</ul>

o      Then call the CombineDifferentShape() template with square1 and round2 objects in order to produce and set the playARoundSquare object values again            (i.e. we want square1 + round2) &#x25aa;          If no exception resulted – then print out the particulars of playARoundSquare

&#x25aa;   If an exception occurred – then

<ul>

 <li>print the exception message</li>

</ul>










<h1>STEP 3 – Putting your Code back into the Repository</h1>

When you have made these changes to your class definitions and mainline – you can simply save your VS Solution and commit your files.

<ul>

 <li>Start by saving all files in solution and existing Visual Studio.</li>

 <li>In the previous exercise – you were reminded of repository best-practices o                Where each source file needs to be committed individually with its own custom / specific comment o           So locate all of your source files (.H files and .CPP files) and commit them one-by-one</li>

 <li>After committing the source files – you return to the C:SETRepo directory where you do a final commit on the Shapes folder to pick up any stray files that also need to be committed</li>

</ul>