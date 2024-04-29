---
excerpt: '<img src="http://images17.newegg.com/is/image/newegg/16-119-023-TS?$S300W$"
  style="float: left"/> A brief review of a SATA backplane'
categories: []
title: A most excellent backplane
slug: most excellent backplane 
created: 1317605941
---
<div style="float: right; width: 20%; padding: 2%"/>
<img width="100%" src="http://images10.newegg.com/NeweggImage/ProductImageCompressAll300/17-119-404-05.jpg"/>
<p><a href="http://www.newegg.com/Product/Product.aspx?Item=N82E16817119404">Athena Power 4x SATA backplane with trays and individual power buttons.</a></p>
</div>

I've been a fan of the [4-in-3 Athena Power backplanes](http://www.newegg.com/Product/Product.aspx?Item=N82E16817119404) for a while.  They're drawback is they're a bit cheaply constructed, so it would be easy to break one (not that cheaply constructed -- I haven't yet broken one).  They also have trays.

<div style="clear: both"/>
<div style="float: right; width: 20%; padding: 2%"/>
<img width="100%" src="http://images17.newegg.com/is/image/newegg/16-119-023-TS?$S300W$"/>
<a href="http://www.newegg.com/Product/Product.aspx?Item=N82E16817119404">Athena Power 4x SATA backplane without trays or buttons.</a>
</div>
When I needed to replace a hard drive in my backup server and wanted to install one of these, NewEgg was out of stock (GASP!).  So, instead, I purchased [one of these](http://www.newegg.com/Product/Product.aspx?Item=N82E16816119023).  

I didn't read the description too carefully, but I noticed the lack of individual drive power buttons.  No biggie, I figured.

As it turns out, it's trayless.  Nice.  It also feels less flimsy than it's compatriot.

So, now there are two decent options.

Is it worth $90 to avoid having to open your computer?  I guess it depends.  My backup server has a [NXZT "Hush" case](http://www.newegg.com/Product/Product.aspx?Item=N82E16811146035), which I highly recommend (apparently still available, but not through NewEgg and more expensive).  It's very quiet (foam lined) and toolless, so replacing drives is quick...but I still have to pull it off the shelf, turn it off, open it up, monkey with wires on the inside.

On my primary server (running many virtual machines), turning off is a pain in the butt and usually results in my wife yelling "Is the mail server down?", so a hot-swap backplane is very nice.  The backup server, perhaps not as necessary, but still nice.

Of course, one big question is:  what does it do to drive temps?  Alas, I don't have a rigorous "before" temp, but I recall it being something around 34C for the top drive (a Maxtor STM3500630AS).  Currently (1 hr after boot, should be fairly stable) the drive temps for the Maxtors in top and next position is 38C.  Oddly enough, the 4th drive (an older Western Digital) is 32C and the newest drive 3rd down (also a WD) is at 31C.  I had pretty aggressive cooling before, with all 4 drives mounted right behind a front-mounted 120mm fan.

Temps on my primary server, with 2 of my earlier favorite backplane and all WD drives range from 33C to 35C.
