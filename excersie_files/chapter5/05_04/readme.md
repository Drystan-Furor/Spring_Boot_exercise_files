my Solution to the RESTful Web Service. 

Let's start in our Web Service Controller. 

I added three methods to this, a GetMapping. 
Within Spring and some of the later versions of Spring Boot, 
they introduced these stereotypes of GetMapping, Post mapping, PutMapping, and Delete Mapping. 

So I didn't have to put a method in the Request Mapping annotation itself. 
I used the GetMapping at /guests, and I simply returned in that service, 
a list of hotel guests from the reservation service. 

I did the same to add a guest, doing a PostMapping at /guests. 
I then have a response status have created, because anytime you create an element in REST, 
you should return it to a one instead of a 200. 

Now, technically I should also populate the location header, which I did not do for this purposes, but I could have. 
It would have been as simple as returning the guests from the add guest method, 
getting that and then populating the location header before I responded out. 

But for this demo, this is fine. I take the guest in, I simply call a reservationService, 
addGuest method, which then saves it to the underlying database. 

And I did the same getRooms, responding at /rooms, and then returning the element from the reservation service. 
I already had the get hotel guests from a previous exercise. 

So I simply added the addGuest here on 83.
I validate that the object comes in is actually populated. 
If it's not, I throw a runtime exception, which will turn itself into a 500. 
If I really wanted to go all the way into this, I would actually return a custom exception that is mapped to a specific response code. 
Again, for demo purposes, just throwing a runtime exception is fine. 
It gets us a 500 to tell us there's a problem. 

I then simply take that guest element and call the underlying Save.  
This is a void method because I'm not returning anything. 

Again, if I wanted that location header, this Save method will return the object that is just saved, 
including its ID. I could take that ID and populate the location header. 
And then on getRooms on line 90, I did the same thing that I had done before on getGuests. 

I simply get them all, converted into array list, sort that, this time I'm sorting by room number, and then return that list. 
But since we are adding, we need to have some way to generate the ID. And we're going to use identity because that works with H2. 
That is the change that I've made to guests. 

So if I run this service, as it's written now, once this runs, we're going to jump into a terminal, and we're going to execute a few curl commands. 

We will do a curl on guests. Get a nice body of guests out. 
a curl -x. It's going to be a POST at http://localhost: 8080/api/guests. 
We were passing the content header. So Content-Type: application/json. 

a -d.  structure some JSON. 
So curl brace, quote, lastName:. We will call the Zenith because it starts with Z. 
This gentleman's name will be Adam. We will end with the curly brace and a single tick. 

The rest of its(indistinct) and populated. 