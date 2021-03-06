--- 
layout: post
title: Set up Postfix to send from Gmail
published: true
meta: 
  _edit_last: "1"
  blogger_author: Ryanhttp://www.blogger.com/profile/13005743548475422193noreply@blogger.com
  blogger_blog: tech.theschuetzlers.com
  blogger_permalink: /2009/12/set-up-postfix-to-send-from-gmail.html
tags: 
- dovecot
- email
- gmail
- How to
- postfix
- smtp
type: post
status: publish
comments: true
sharing: true
---
Alternate title: How to send 9,000 emails from a Gmail address

To preface this, I want to say that I am currently in charge of online activity for an honor society at school. As part of those responsibilities, I needed to send emails to over 9,000 prospective members to invite them to join the organization. We use Gmail addresses for our organizations email, but Google shuts off an email address after sending about 500 emails, and it shuts off an IP address after you send about 1,500 (using three different accounts).

To solve this problem, I installed an SMTP server (<a href="http://www.postfix.org/">Postfix</a>) on my computer at home so I could send that many emails. I couldn't find any free email provider who allows that many emails. Here are the steps to create the server:<!--more-->
<ol>
	<li>Create an MX record with your DNS</li>
	<li>I used this <a href="http://jonsview.com/2009/03/26/how-to-setup-email-services-on-ubuntu-using-postfix-tlssasl-and-dovecot">tutorial</a> to set up Postfix and <a href="http://www.dovecot.org/">Dovecot</a> for SMTP and IMAP. It provides a great walkthrough for setting up a secured SMTP server (a must unless you want any Joe Shmoe to send spam through your computer).</li>
	<li>Open up ports 25 (SMTP), 143 &amp; 993 (IMAP) in whatever network devices you need to</li>
</ol>
Once you have that set up, it's a piece of cake to set up Outlook or your favorite mail client to send mail through your SMTP server.
<ol>
	<li>Create a new email account in your mail client</li>
	<li>Set up the incoming and outgoing servers to direct to your domain (example.com)</li>
	<li>Your email account for both incoming and outgoing mail will require secure authentication. Use the username and password for your user account on the server</li>
	<li>Your email address on the server will be user@example.com</li>
	<li>For the "email address" section of the account setup, just enter your Gmail (or other) address</li>
	<li>Proceed to send mail</li>
</ol>
<div>The emails you send will appear to come from your Gmail address instead of user@example.com. This way you can use a Gmail address to send mass mail and receive responses.</div>
