 I impacted four files when I created this solution. 
 
 So in my index.html static page, I added an anchor to go to our guests page. 
 I then went into the reservations service and I added a method to list the hotel guests, 
 and I did it very similar to the way that we have done it before. 
 So I got a list of iterable guests, created an array list from that, 
 and then sorted those guests based on their last name, 
 and then returned that guest list to the caller. 
 
 I then created a guest controller and the guest controller responds and slash guests. 
 It has a reservation service injected into it. 
 It then has a get method with a get guests method signature that also takes in a model, 
 and I simply populate the guests with the call from the reservation service. 
 
 Now you'll notice that I return hotel hyphen guests. 
 If you return just guests here, you may get a circular reference, 
 and I may have struggled with that, it's one of those things that you will remember down the road, 
 having experienced it once. 
 But if you didn't experience it, then most likely you didn't name your request URL the same as your response page itself. 
 
 So now let's go into that page. 
 So I imported Thymeleaf. 
 I called this "Landon Hotel: Guests" as the title.
 I created all of the elements from the requirements, simply from an iteration across guests. 
 So now it's time to run the application and we'll jump into a web browser.
 You'll see that I have room reservations, which still functionally works. 
 I have guests that are now sorted by last name and it goes through the entire list. 
 
 And that's how I solved this challenge on building web pages.