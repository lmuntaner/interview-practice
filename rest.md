# Definition of REST

Representational State Transfer (REST) has gained widespread acceptance across the Web as a simpler alternative to SOAP- and Web Services Description Language (WSDL)-based Web services. Key evidence of this shift in interface design is the adoption of REST by mainstream Web 2.0 service providers—including Yahoo, Google, and Facebook—who have deprecated or passed on SOAP and WSDL-based interfaces in favor of an easier-to-use, resource-oriented model to expose their services.

REST defines a set of architectural principles by which you can design Web services that focus on a system's resources, including how resource states are addressed and transferred over HTTP by a wide range of clients written in different languages.

Let's try to put the concepts of REST in plain English. To do that, we're going to borrow four basic design principles from IBM's developerWorks website, and explain what they mean.

- Use HTTP methods explicitly.
- Be stateless.
- Expose directory structure-like URIs.
- Transfer XML, JavaScript Object Notation (JSON), or both.

## Use HTTP Methods Explicitly

This one's pretty straightforward. To retrieve data, you use GET. To create data, you use POST. To update or change data, you use PUT (not used in this tutorial). To delete data you use DELETE. So for example, this once-common approach is not a good one:

http://www.domain.com/myservice/newuser.php?newuser=bob

That's an HTTP GET pretending to be a POST. You're GETting the web page and giving it data to store in a DB at the same time. Instead, create a NewUser service and POST to it.

## Be Stateless

This is a complicated concept but it boils down to “don't store state information on the server”. If you must save state, save it on the client side via cookies or other methods. A front-end framework like Angular (outside the scope of this tutorial, but stay tuned!) is particularly helpful here, as it creates an entire client-side MVC setup where you can save and manipulate the state of elements without hammering your server.

IBM gives a pagination example which is pretty good. A stateful design would hit a deliverPage service that's been keeping track of the page you're on, and delivers the next one. a Stateless design would populate prevPage, currPage, and nextPage data in the markup (hidden input fields, JavaScript variables, data- attributes, and so on), and then HTTP GET a newPage service using the nextPage parameter from the markup to request a specific page.

I've put together a quick JSFiddle illustrating what I'm talking about. Take a look and note that we're never storing any page data on the “server” side. We merely take the current page value from the DOM, and then when we get our new page, we update the DOM. That's simple, stateless programming.

## Expose directory structure-like URIs

This one's easy. Instead of:
http://app.com/getfile.php?type=video&game=skyrim&pid=68

You want:
http://app.com/files/video/skyrim/68

## Transfer XML, JavaScript Object Notation (JSON), or both

This one's easy too! Just make sure that your back-end is sending XML or JSON (I prefer JSON, especially in all-JavaScript setups like the one discussed in this tutorial). You can easily manipulate this data in your presentation layer without having to hit your servers, unless you need new data.

OK … so do we get the basics of REST? It's pretty straightforward, really. You've probably already worked within systems that use it.

## Bibligraphy

From [this](https://closebrace.com/tutorials/2017-03-02/creating-a-simple-restful-web-app-with-nodejs-express-and-mongodb) article.
