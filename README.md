Landing Pages
==========

This is a framework for creating landing pages to be tested on github pages.

## Steps to create your own landing pages

* add a `CNAME` file, this will be the domain your pages will be at.
* push everything to a new branch called gh-pages

	git co -b gh-pages
	git push origin :gh-pages

* Edit the `_config.yml`; This file contains all the variables used to render pages.

## MailChimp Integration
You will need to setup mailchimp to capture the email addresses. Sign up for mailchimp and then watch this video on [how to create a naked form][1]. We are not going to create a naked form, we just need to know the URL to send the data to. DON'T GET PASTE HAPPY!!! We just need one thing from this.

Once you do this, you will see code that looks like this:

```
<!-- Begin MailChimp Signup Form -->
<div id="mc_embed_signup">
<form action="http://kolakube.us2.list-manage.com/subscribe/post?u=ba2d7d2ff28fe4f2581509340&amp;id=a355e20f0d" method="post" id="mc-embedded-subscribe-form" name="mc-embedded-subscribe-form" class="validate" target="_blank">
	<h2>Subscribe to our mailing list</h2>
<div class="indicates-required"><span class="asterisk">*</span> indicates required</div>
<div class="mc-field-group">
	<label for="mce-EMAIL">Email Address  <span class="asterisk">*</span>
</label>
	<input type="email" value="" name="EMAIL" class="required email" id="mce-EMAIL">
</div>
<div class="mc-field-group">
	<label for="mce-FNAME">First Name </label>
	<input type="text" value="" name="FNAME" class="" id="mce-FNAME">
</div>
	<div id="mce-responses" class="clear">
		<div class="response" id="mce-error-response" style="display:none"></div>
		<div class="response" id="mce-success-response" style="display:none"></div>
	</div>	<div class="clear"><input type="submit" value="Subscribe" name="subscribe" id="mc-embedded-subscribe" class="button"></div>
</form>
</div>
<!--End mc_embed_signup-->
```

We need the value in the `form` tag, under the `action` directive. Paste this into the `_config.yml` under mailchimp.

We will also need to create a group. To do this, go to your list, and click `GROUPS`, create a new group called `SOURCE`.

![Create a mailchimp group](http://cl.ly/image/360L452n1V2V/Screen%20Shot%202012-12-20%20at%202.33.38%20PM.png)

## Viewing before push
In order to view the end result, you will need to install `jekyll`

	gem install jekyll

Then run the jekyll server in the root directory:
	jekyll --server

Then point your browser to [http://localhost:4000/](http://localhost:4000/)

## MANY TESTS

You can use one repo to run many tests. Mailchimp will have a column called SOURCE that says where the signup came from. To do this...

* Just copy the `/landing` directory to a new folder:

	cp -r landing/ new_landing_page/

* Edit the yaml front matter of the index.html for you're benefits.
* Point your adds to http://site.com/new_landing_page/



[1]: http://kb.mailchimp.com/article/how-can-i-add-my-signup-form-on-my-website