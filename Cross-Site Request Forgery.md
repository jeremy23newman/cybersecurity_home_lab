# Cross-Site Request Forgery 

## Start-up/Installation 

I started off the lab by installing the websites and then starting them up. 
My target site was located at localhost:3000 whilst the malicious site was located at localhost:3001.
The beginning balance of Bob's account was 500 dollars with the target site only having the ability to transfer money between accounts. 

## Get Attack Summary

There were two differnt attacks showcased on the malicious website, one of them was a link that you would 
have to click in oorder for the request forgery to steal $25 dollars from bob's account and transfer it to alice's.
The second type of get attack was done using img src code which automatically ran everytime the page was opened. Img code 
usually is meant for images that are loaded at the request to open the website. Thus in this case instead of pointing to an img url, the code points
to a get request to transfer $15  dollars from Bob's account to Alice"s account.

## Main CSRF vulnerabilities in Website/Program

The inital code of the website uses GET requests to modify the balance of an account which allows for a lot of security breaches,
since a get request can be easily influenced by a user as explained by img src get request. Even when switching the program
to Post requests which are generally safer, it can still be manipulated. The best way to prevent a CSRF vulnerability in your website 
would be using Same-Site Cookies of Secret Tokens inside of the code to prevent cross-site request forgery from happening

## Post Attack Summary

The code for the post request uses hidden values and a function that sends a post request on the load of the malicious website.
This way the user would be entirely oblivious to what is being loaded during the background. For this example spefically, we hid the values of alice
and the amount transferred which was $10 so that user cannot see it but the request is sent through without any user interference. If the program incorporated 
a system like Secret Token, the server would realize the request is cross-site and would allow a foreign page to access the secret value. Secret Tokens embeds
a random secret value into each web page, making it easier for the server to recognize when a request is coming from a different site.


