# Bitcoin Tipping Browser Extension

##Part 1: Make text or linked bitcoin addresses in the browser easier to tip.

Use regex to detect bitcoin addresses in the browser.  

Next to each bitcoin address, place a button that says "Tip!" and a bitcoin icon.  
When the tip button is pressed, a small menu comes up with Bitcoin amounts ("Tip 0.1000", "Tip 0.0500", "Tip 0.0100", "Tip 0.0050", "Tip 0.0025")

Each of those will be a bitcoin link that opens their wallet.  
  
So if the address is "1qwertyuiopasdfghjklzxcvbnm" The first link will look like <a href='bitcoin:address=1qwertyuiopasdfghjklzxcvbnm&amount=0.1&label=webpage title'>Tip 0.1000</a>

Support bitcoin links also. So if <a href='bitcoin:1sdlfkjewrlkj&amount=0.1&label=blah'>Tip me please!</a> is detected, put the Tip button/icon next to the linked text "Tip me please!".

Example:

![](http://imgur.com/t3csynO.png)






##Part 2: Add a "Tip Later" option and keep track of these internally and remind the user to tip later.

When the user clicks on "Tip Later", all of the tip details should be stored for later:
 * contact type (bitcoin)
 * contact info (the bitcoin address)
 * current date
 * webpage url
 * webpage title
 * webpage favicon
 * status (tipped, not tipped yet, or cancelled)
	
Once a week, the extension should notify the user if they have any tips with the status of "not tipped". Allow the user to choose "Tip Later" to put it off another week or "Tip Now" to see the list of items on the "Tipping Page".

The "Tipping Page" will allow a user to set an amount to tip and then use sliders to adjust the amounts going to each item.

Next to each item, there will be a bitcoin link that has the item's bitcoin address, webpage title, and the adjusted amount chosen by the user. The "Tip" link will open their bitcoin wallet.  When that "Tip" link is clicked, the extension should mark the item's status as tipped so the user won't accidentally tip the same thing twice.

Example Tipping Page: 

![](http://imgur.com/RvkWzKP.png)





##Part 3: Add a tip button to the address bar of select pages to tip the page owner.

Try to find a bitcoin address in the metadata.  If it has it, add a Tip button to the address bar.  This will behave exactly like the tip button next to bitcoin addresses.

Design for a few special cases on social media websites like youtube.com, twitter, and facebook.  If no meta tag is found on the page, search only the video description or profile for a bitcoin address.  If one is found, treat it like the meta address and add the tip button to the address bar.






##Part 4: If tipping isn't available, send a tip request via email/social media.

This basically makes asking someone to accept bitcoin as easy as a click.

If we are on a special case page, and no bitcoin address was found in the description, change the function of the tip button to send the user a message asking them to get a bitcoin address and put it on their profile.

Example: I want to tip @ErikVoorhees on twitter.  I go to his twitter page https://twitter.com/ErikVoorhees.  The extension scans only his profile for a bitcoin address.  None is found.  The tip icon still appears in the address bar.  If "Tip Later" is chosen, the contact type is set to "twitter" and the contact info is set to "ErikVoorhees" in the table of tipped items being stored for later.  If an amount is chosen like "Tip 0.0100", then that is actually a link that leads the user to send a message to Erik saying they want to tip him but couldn't find a bitcoin address.

https://twitter.com/intent/tweet?text=%40ErikVoorhees%20I%20want%20to%20tip%20you%20X%20bitcoin%2C%20but%20couldn%27t%20find%20an%20address%20in%20your%20profile.%20%20If%20you%20get%20one%20let%20me%20know. 

Ex: <a href='https://twitter.com/intent/tweet?text=%40ErikVoorhees%20I%20want%20to%20tip%20you%20X%20bitcoin%2C%20but%20couldn%27t%20find%20an%20address%20in%20your%20profile.%20%20If%20you%20get%20one%20let%20me%20know. '>Tip 0.0100</a>

And the same can be done for email addresses, youtube, facebook, tumblr. Any website that let's users have a profile and allows the sending of messages.  

I think this is the most important part because it encourages each person to get a bitcoin address and publicly display it on the profile.  And the bitcoin icon might encourage those who have installed it to tip, even though the user didn't put the button there themselves.





