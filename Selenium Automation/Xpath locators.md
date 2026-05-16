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

