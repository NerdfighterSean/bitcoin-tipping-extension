# Special Cases 

How to get the bitcoin address from social media websites and how to format the contact link for them.

##Default Page (Metadata bitcoin)

###Where to get the bitcoin address


##Twitter


###Page URL

http://twitter.com/NerdfighterSean

###Where to get the bitcoin address

<p class="bio profile-field">Twitter User Description here. 12CEuFuAXLPQLe679ZHEsXqYgMfzT1p9qn</p>

### No address found? Replace tip links with contact link

//get user from the page
var user = "<span class="screen-name"><s>@</s>NerdfighterSean</span>"

//form the message
var message = " I want to tip you "+amount+" bitcoins but couldn't find an address on your profile. Let me know if you get one."

//the url to compose the message
var url = "https://twitter.com/intent/tweet?text="

//put it all together and url encode it
var href = url + "@" + user + message

https://twitter.com/intent/tweet?text=%40ErikVoorhees%20I%20want%20to%20tip%20you%20X%20bitcoin%2C%20but%20couldn%27t%20find%20an%20address%20in%20your%20profile.%20%20If%20you%20get%20one%20let%20me%20know. 



##Youtube


###Page URL

https://www.youtube.com/watch?v=kGxPaXOLNos

###Where to get the bitcoin address

<meta name="description" content="feedback@edandethan.com http://feeds.feedburner.com/EdAndEthanBitcoinCast http://www.EdandEthan.com Donate bitcoins at: 12CEuFuAXLPQLe679ZHEsXqYgMfzT1p9qn - ...">

### No address found? Replace tip links with contact link

//get user from the page
var user = "<link itemprop="url" href="http://www.youtube.com/user/EdandEthan">"

//get video title
var videotitle =     "<meta itemprop="name" content="Ed and Ethan&#39;s Bitcoin cast #18">"


//form the message
var message = "Hey, I wanted to tip you "+amount+" bitcoins for the video "+ videotitle +" but didn't see a bitcoin address in the description. Let me know if you get one."

//the url to compose the message
var url = "https://www.youtube.com/inbox?action_compose=1"

//put it all together and url encode it
var href = url + "&to_users=" + user + "to_subject=Bitcoin Address?&to_message=" + message 

https://www.youtube.com/inbox?action_compose=1&to_users=EdandEthan&to_subject=x&to_message=x

//This requires special handling.  When on this page, https://www.youtube.com/inbox?action_compose=1 

//see if the url contains the parameter to_subject.  If so, take the parameter from the url and fill out the field.
//<input type="text" class="compose_input yt-uix-form-input-text" id="compose_subject" onkeyup="goog.i18n.bidi.setDirAttribute(event,this)" />

//see if the url contains the parameter to_message.  If so, take the parameter from the url and fill out the field.
//<textarea rows="16" class="compose_input yt-uix-form-input-textarea" id="compose_message" onkeyup="goog.i18n.bidi.setDirAttribute(event,this)"></textarea>


