 * we've all used the web
 * typed in an address to get to a certain page
 * clicked on links to go to other pages etc

 * what is actually happening behinds the scenes to make the internet & and web work
 * actually quite a lot
 * but the good news is that it's all in layers and you don't need to know all of it

 * as a web developer you don't need to know that much to get started
 * most of it you only really need a rough idea
 * and then you learn the little bits of it when you have a specific problem
 * you don't have to learn all of it to start
 * you learn it as you need it

 * So the core thing we are going to learn in this workshop is how to make simple webpages
 * we do this with two languages, HTML (HyperText Markup Language) & CSS (Cascading Style Sheets)

* but before we get onto that, lets do a quick rough overview of how the web works  

 1. you type an address into your browser (or you click on a link)
    *  This address is called a URL, and it has three parts:
        * examples
        1. protocol (usually http or https for webpages)
        2. a computer (or host) name
        3. path
2. You browser sends a request:
    * to the computer with that name (AKA the web server)
    * using the specified protocol (protocol is a set of rules about how to structure the request and the reply)
    * for the file at the specific path
3. The web server receives the request, and if it has a file at that path, it sends it back, otherwise an error message
4. Your browser receives the file and will display it for you according to the HTML / CSS contained in it.

That is the simplest case.  The reality today is that the server doesn't always actually have a actual file on disk for every URL.  

What the server does is it has software that looks at the incoming requests and assembles the page on the fly to send back to you.  
That might sound very fancy and complicated, but if you've ever done a mail-merge to create letters to send to customers, it's the same idea.

You aren't going to be running your own server in this workshop though.  

You can use the protocol `file:` to open webpages on your own computer.
That is what we will be doing.
So not as fancy as facebook or google BUT the underlying HTML & CSS is the same.

So lets get on with it.
