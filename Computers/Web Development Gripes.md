# Web Development Gripes

## Introduction

In 2015-6, I was tasked with extending a webapp for some company using a MS-centric stack. I shall overview some technologies, and complain about them.

## Introduction to databases

Databases are used to store large amounts of dynamic, structured data. They can be thought of as giant, supercharged spreadsheets with lots of rows and columns. Databases have rows and columns. Database tables can be thought of different sheets in a spreadsheet document (sometimes linked), and different databases can be thought of as different spreadsheet documents. Most modern, dynamic, or webapp websites are run by databases. Twitter and Facebook use the famous MySQL relational database software. By no means the best (in all metrics), it is one of the most popular and well-known. By relational, we mean there is an enforced relationship between the data.

## Introduction to MVC

MVC is a paradigm for making modern websites. It stands for Model-View-Controller.
* Model: A representation of the data, usually a representation of the database, but not the database itself. This defines the entities that you can manipulate from the programming language.
* View: This defines the layout and presentation of the data on the page, and to some extent controls what the user is allowed to see.
* Controller: This defines the interactions between the View and the Model.

![MVC](https://upload.wikimedia.org/wikipedia/commons/thumb/a/a0/MVC-Process.svg/436px-MVC-Process.svg.png "The model, view, and controller (MVC) pattern relative to the user")

In a more concrete example, let us propose we were to display a list of students and provide functionality to add and delete students. A model would contain a list of students, the view would contain layout and controls for how to display students, and buttons for adding & removing students, and the controller would be the actual coded methods for adding & removing students from the model.

These functions are split into three parts for modularity, reusability, with the aim of low coupling and high cohesion. These are all desirable aspects of good code. Low coupling means that the pieces are only loosely connected, or have a low amount of connections. High cohesion means that they are working together to accomplish one overall task, in our previous example, to display and manage students. In practice, the coupling may be higher, and the cohesion may be low, as one file highly depends and is bound to another file, and various functionality is found in files all over the place.

 

Issues with Team Foundation Services & Visual Studio
----

After a while using Team Foundation Services (TFS) and Visual Studio (VS), I had some very distinct gripes with it. Working in a team of 12 people with about 8 branches over 11 weeks has exposed a number of issues.

* Directly merging two children branches together, which would appear to be an intuitive way of sharing code, generates code conflicts for every change and is not the correct way to merge in TFS. The correct way to merge is to merge to the parent first. Thus, instead of 2 merges to share code between 2 branches, you need 4. As such, TFS is inferior to other systems due in terms of increased code merges. 
* TFS is remote-based, so with multiple team members working on code, each member needs to have their own individual branch if guaranteed saving of works is prioritized. This is in contrast to git, which is local-based, so there is less need for individual branches, as local work is guaranteed to be saved by fact of being local. Conflicts are solved later during remote push.
* Code moving up & down in a file isn't always reliably detected. It could be any one of the following: code add, code delete, or code conflict.
* Scrolling in VS is always very slow (0-1 fps) when comparing code, and significantly slows down code merging
* The CSproj file sometimes erraneously duplicates entries (including source files twice, which are actually the same file on-disk). This can only be fixed outside of VS, using a text editor such as Notepad++
* VS may show differences in whitespace as code conflicts, which nags for manual intervention. 
* One time, VS managed to insert one JS function in the middle of another JS function, leaving for a quite broken page. Probably because some of the boilerplate looked similar. 
* Randomly uncapitalizing things in a file, also resulting in a broken page 

I read a blog post titled ["Why you should abandon TFS and adopt Git"](http://www.continuousimprover.com/2015/06/why-you-should-abandon-tfs-source.html) (Doomen, 2015), and some of the comments (regarding merge conflicts) really resonated with me at the time that I was having lots of merge conflicts. Summarized to the gist, git's intelligent 3-way merges solve 'merge conflicts' that should never have been merge conflicts in the first place. To conclude, git could be used instead of TFS for a better source control experience.

The problem with ASP.NET MVC
----

ASP.NET MVC is a web framework using the well-known MVC paradigm. After spending a considerable amount of time developing in ASP.NET MVC, I was starting to feel the shortcomings of ASP.NET MVC. Some things worked while others mysteriously didn't. For example, converting to a currency format with decimal separators sometimes works and sometimes doesn't for no obvious reason. There were workarounds for ASP.NET MVC, CSS (bootstrap), and JS.

I eventually I found a page by Doomen on the internet. He writes "The biggest beef I have with .NET is that the One True Way leads you away from the ideal... This kind of focus results in the technical implementation bleeding through". In MVC, there is supposed to be clear separation between the Model, View, and the Controller, but during development we found roles of one leaking to another, which seemed wrong, but had to be kept due to time constraints.

In the C# ASP.NET MVC, you have your usual MVC (Model, View, Controller) entities. But in the controller, you may do some View-related things, and in the View, you can do some data preparation things, which should be reserved for the controller. In fact, you can put almost as much C# as you like in the view, instead of staying to mostly HTML/CSS. This is bad as the purpose of of a View is to display data, not to process it. Note, there is also some JS in the view. This is necessary to support instant user interaction. But then the logic for handling this data must be in the View, which also goes against MVC.

Also in C# ASP.NET MVC, the View format is cshtml, which means, you should write views in a mix of C# and HTML (and CSS/JS/etc). The parsing is a very critical part of the process, as its job is to differentiate between different languages and roles. Anything beyond simple can be hard to get right, as sometimes there had to be weird workarounds just to please the parser because C# and CSHTML syntax can be very similar. For example, a comment in one language could be a directive in another.

In contrast, Django (another MVC web framework) views are plain HTML. This means that you cannot simply place large amounts of arbitrary code into your views, avoiding the role abuse inclinations of ASP.NET MVC. To control the layout and content, Django uses special Django tags  which are very dissimilar to HTML or python. This means that the parsing is simpler, and easier to troubleshoot. 

In conclusion, you can develop websites with ASP.NET MVC, but there are various technical quirks, and it is easy to abuse roles. It has a proprietary ethos around it (although ASP.NET MVC is OS, it likes to run on windows). And hence, in my opinion, Django is a better first-resort than ASP.NET MVC for building web apps.

The problem with JavaScript
----

The problem with JavaScript is that the development form highly resembles the deployment form. So, anyone that views the page could potentially have a look at the source code. They could figure out weaknesses, and potentially start looking at how to use the page for malicious means. I had a look at JavaScript obfuscators, and ran the output through a JavaScript deobfuscator (the only real test), and found that the doubly-processed output have parts which were obviously reminiscent of the original. Therefore, one must take care when using JavaScript and be aware of possible security issues.

Problems with CSS
----

## CSS is hard to get right

The main problem with Cascading Style Sheets (CSS), and CSS frameworks like Bootstrap is that anything beyond extremely simple is hard to get right. The CSS framework that was used for this website is called Bootstrap, made by Twitter Inc. They quote "Bootstrap makes front-end web development faster and easier. It's made for folks of all skill levels, devices of all shapes, and projects of all sizes."

The basic idea behind bootstrap is a 12 column layout, and you assign a number of columns to various boxes (called ‘divs’). You can have nested column systems. Each div should not be sliced in half if the viewport is small (say on a mobile device), but subsequent divs may be. Each 12 columns should be enclosed in a row for clarity and layout purposes.

For many websites, you aim to pack a lot of information in a small area, but have that information structured as well, and presentable on varying screen sizes. But what if you have several column systems within another/s? What if you mix bootstrap columns and native CSS features? What if you mix bootstrap columns with fixed-width containers? Any non-trivial website is bound to have those features. When complex layout systems interact and different features are used, desired results are hard to achieve. And therefore, CSS and bootstrap can get complicated and hard to get looking right.

## CSS Overrides are necessary

Most of the time, we use the site styling without issue. But sometimes, other parts of site styling conflict with what our team is aiming to do. In some instances, we use a CSS override with inline CSS to attempt to accomplish what we want to do. While some things cannot be accomplished in inline CSS, we try to minimize the impact by implementing what we can and checking to see if it still looks acceptable.


DPI detection and handling is troublesome
----

There is no one way to detect the DPI of a device that will work across all platforms and all browsers. In addition, UI elements that are done using hardcoded pixel (px) values is bad practice, because pixel directives don't necessarily match physical device pixels, especially in the case of HiDPI (approx. &gt; 144DPI) devices. Such as, premium smartphones, many tablets, the increasing amount of 4K ~23" monitors, and premium laptops. In the case of 2:1 pixel density devices (such as the iPhone 4), an element with a hardcoded pixel size may appear 1/4 as large as it should (1/2^2 = 1/4), or the google nexus 6 with a 3.5:1 pixel density ratio, elements with a hardcoded pixel size may appear about 1/12th as large as it should.

I looked up some solutions online to detect pixel density, and there was no single solution that works on all browsers, on all platforms/devices. There is one solution called "CSS media query" from the ["Detecting the system DPI/PPI from JS/CSS?"](http://stackoverflow.com/questions/279749/) question on the StackOverflow site (Waite, 2011). However, it’s only supported by "Firefox ... Opera ... and IE 9". Non-desktop/mobile browsers were not checked. The same site also suggested to use the screen-relative units called 'em' via the ["How to access screen display's DPI settings via JavaScript?"](http://stackoverflow.com/questions/476815/) question (Fredric, 2009). The latter worked across more devices & apps, so the wishlist was refactored to use em.


Database triggers are hard to troubleshoot
----
Database triggers are procedures that you can add to a database that get automatically run when certain action(s) happen. The advantage of this is that wherever in your program code the database is changed, the relevant database trigger will always be executed, because it's a database-level thing. If you were to modify the trigger, you have to change it in one place only. Compare this to program code. If you were to implement it via program code, you would need to insert code in all the places that you do the relevant database calls. If you were to modify the behaviour, you would need to modify your database call everywhere you implemented it. You might set a trigger. A week later, you might change your database layout, then get strange errors, since you forgot that you set a trigger. In conclusion, avoid database triggers because they can be hard to troubleshoot - use program methods instead.

References
===
* Doomen, D (2015). "Why you should abandon TFS and adopt Git" http://www.continuousimprover.com/2015/06/why-you-should-abandon-tfs-source.html
* Fredric, K (2009) "How to access screen display's DPI settings via JavaScript?" http://stackoverflow.com/questions/476815/
* Twitter Inc (2017). "Bootstrap" via http://bootstrap.transferwise.com/
* Waite, P.D (2011) "Detecting the system DPI/PPI from JS/CSS?" http://stackoverflow.com/questions/279749/

 