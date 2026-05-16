1.xpath-->xml kind of language


2.DOM-->document object model->when lanching of the page the dom is created then testing will work on the dom

3.types of xpath

   2 types of xpath
-----------
1) Absolute xpath(full xpath)
	Ex: 	/html/body/header/div/div/div[2]/div/input

2) Relative xpath(partial xpath)
	Ex: //*[@name="search"]

Which xpath will be prefered?
Relative xpath.


Difference between Absolute & Relative xpaths?
------------------
1) Absolute xpath starts with  /     ---> represents root node
  Relative xpath starts with  //

2) Abosulate xpath do not use attributes
  Relative xpath works with attribute

3) Absolute xpath traverse through each node till it finds element
   Relative xpath directly jump and find the element by using attribute


//img[@title='Your Store']
/html[1]/body[1]/header[1]/div[1]/div[1]/div[1]/div[1]/a[1]/img[1]


syntax:
----
//tagname[@attribute='value']
//*[@attribute='value']

//img[@title='MacBook']

xpath with inner text - text()
-----------
//a[text()='Desktops']
//a[text()='MacBook']


<a href="https://xyz.com"> Click Me </a>
	
linktext = yes
inner text = yes

<div>welcome</div>
linktext= no
innertext= yes


xpath with contains()
---------------------
//input[contains(@placeholder,'Sea')]


handling dynamic attributes
-------------

//*[@id='start' or @id='stop']
//*[contains(@id,'st')]
//*[starts-with(@id,'st')]


name=xyz001  xyz002   xyz 003 xyz004 xyz001 xyz 002

//*[contains(@name,'xyz')]
//*[contains(@name,'00')]
//*[starts-with(@name,'xyz')]


name= 1xyz 2xyz 3xyz 4xyz 1xyz
	//*[contains(@name,'xyz')]


name=101xyz  201xyz  301xyz  401xyz
	//*[contains(@name,' xyz')]
	//*[contains(@name,' 01')]

chained xpath
---------------
//div[@id='logo']/a/img



<div></div>

//div[contains(text(),'')]
//[contains(.,’ ‘)] 

