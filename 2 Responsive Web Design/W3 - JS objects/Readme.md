# Week 3 References

## Video: Separating Structure and content
---
* [JS Reference site](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference)

## Video: JS Objects
---

```Javascript
<!-- set the variable -->
> var image1Name="Image 1"
```

```Javascript
<!-- Use the variable -->
> $("#title").html(image1Name);
```

* Wrap text variable in quotes
* Variable = Content
* HTML = Structure

### JS object
General Format:
```Javascript
var image1Data = {
    title: "Image 1", value
    author: "Tuxyso"
}
```
How to use an object:
```Javascript
image1Data.title
```
* *Javascript Does not have classes! Very different from other OOP languages


**Practice Quiz**

1. What are objects useful for?
<br> **A:** They let you combine lots of related variables into one thing
2. Correctly defined object:
<br>
```Javascript
console.log(student.name);
```
3. How to print the member variable "name" of the object "student"?
```Javascript
console.log(students.name);
```
## Handlebar templates resources
---
[http://handlebarsjs.com](http://handlebarsjs.com)

## Video: JS templates w/ Handlebars
---

* Handlebars lets you buld semantic templates effectively with no frustrations

Template Example:

```
<script id="image-template" type="text/x-handlebars-template">

<h1>{{title}}</h1>

<h3 class="author">{{author}}</h3>

<img style="height:200" src="{{src}}">
<script>
```
* NOT JS or HTML
* {{placeholders}} for title, author, src

**Practice Quiz**

1. Did you spot the error in my slides? It was this bit of code:
```
<script id="image-template" type="text/x-handlebars-template">      <div class="title">		    
        <h1>{{title}}</h1>    		
        <h3 class="author"> {{author}} </h3>		    
        <img style="height:200" src="{{src}}"/>      
     </div>    
</script>
```
**A:** There are no units in the value of the height

2. Handlebars matches data to templates based on the name of member variables in an object.<br>
**A:** True

## Adding Data
___
Code format (HTML):
```HTML
<div id="content"></div>

<script id="image-template" type="text/x-handlebars-template">
        <div class="title">
            <h1>{{title}}</h1>
            <h3 class="author">{{author}}</h3>
            <img style="height:600" src="{{src}}">
        </div>
    </script>
```
Code format (JS):
```Javascript
<script type="text/javascript">
    
    var source = $("#image-template").html();

    var template = Handlebars.compile(source);

    var data = {
        src: "https://upload.wikimedia.org/example.jpg",
        title: "The Earth Seen from A17",
        author:"Ed g3s"
    };

    var html = template(data);

    $('#content').html(html);

    </script>
```


**Practice Quiz**

1. The result of compiling a template is:
<br>
**A:** JavaScript- compiling is the process of taking Handlebars template code and turning it into javaScript that can generate HTM

2. The result of instantiating a template with data is
<br>
**A:** HTML - templates generate HTML that can then be put into the web page

3. What do you use to put the output of a template into your web page?
<br>
**A:** Handlebars - jQuery is the library you use for interacting with the DOM

## Displaying Different Data with the same template
---
**Source Code**
[download](https://d3c33hcgiwev3.cloudfront.net/_465480ed492c1ecb38ad501366738e67_2.3.5.zip?Expires=1539993600&Signature=CAJODdWJF6w8X8ieOKCgMdV4atJWgXVEXeKBLl7d32pR998MT40W0KpaBcULAY-JR7YZ~tJEywUsSubI549uTPdzLlHq-CTqR8Z9a6rBLWXofjTwhx4VI5FyyK7QwOkgmu49Cn~ZNlMsel0gh24J8OBYdNd2Pdr-91gqac65C-s_&Key-Pair-Id=APKAJLTNE6QMUY6HBC5A)
<br>
<br>
<b>Practice Quiz</b>
1. To layout two javaScript objects you need:
<br> <b>A:</b> One Template - the power of templates, is that once you have a template you can re-use it with as many data objects as you like

2. When you render two objects with a single template, which of these do you only have to do once?
<br>
<b>A:</b> Compile the Template - compilation only depends on the template and since you only have one template you only have to do it once
## Displaying the Same Data with Different Templates, Use a Bootstrap Modal
[Download Source Code](https://d396qusza40orc.cloudfront.net/phoenixassets/Jackie%27s%20folder/2.3.6_final.zip)

<b>Practice Quiz</b>
1. How many template expressions does a template need? <br>
<b>A:</b> One for each piece of data you want to display - you only need expressions for the variables you want to show

2. What is a modal?
<br>
<b>A:</b> A pop up dialog within HTML - modal refers to user interface elements that appear in front of the main interface and prevent you from interacting with it until you have dealt with the modal

3. When do you call this?
```Javascript
$("#imageModal").modal('show'); 
```
<b>A:</b> After rendering the template - the modal does not exist until you render the template so you cannot show it