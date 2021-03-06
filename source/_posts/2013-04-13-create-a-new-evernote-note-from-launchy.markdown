---
layout: post
title: Create a new Evernote note from Launchy
categories:
- How to
tags:
- how to
status: publish
type: post
published: true
meta:
  _publicize_pending: '1'
comments: true
sharing: true
---
<p>I love <a href="http://evernote.com/">Evernote</a>. And I love <a href="http://www.launchy.net/">Launchy</a>. But it turns out that combining the two was more difficult than I expected. All I wanted was a way to add a new note to Evernote from Launchy without having to open up Evernote's whole interface and do all sorts of clicking and such. After a bunch of digging, and a little bit of scripting, I finally created a way to do it.</p><p>Take the <a href="https://gist.github.com/rschuetzler/5380448">evernoteadd.bat script</a> and place it anywhere you want. Replace my <code>"_INBOX"</code> with whatever default folder you want these notes to go to. Then simply create a Launchy action in Runner with this batch file as the program, and <code>"$$" "$$"</code> as the arguments. To create a new note from Launchy, type the name of the action you created, hit TAB, type the title of the note TAB text of the note RETURN.</p><p><a href="https://gist.github.com/rschuetzler/5380448/raw/5a7c7d478199d0232c8290e83c6f6f0446f0a04a/evernoteadd.bat">Download the script</a></p><p>UPDATE: Thanks to <a href="http://stackoverflow.com/questions/15994824/faking-standard-input-on-the-windows-command-line">StackOverflow</a>, I figured out a way to make the script work without a temp file. I've updated the script accordingly</p>
