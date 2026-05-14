CSS Selector
--

CSS - Cascading Style Sheets


tag id			tag#id
tag class		tag.classname
tag attribute   	tag[attribute="value"]
tag class attribute 	tag.classname[attribute="value"]


driver.findElement(By.cssSelector("input#small-searchterms")).sendKeys("Pants");


2. if we need to use double qouts inside value we can give 
driver.findElement(By.cssSelector("input[placeholder=\"Search store"\)"])

3.selectorHub extention
