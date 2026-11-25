---
layout: page
title: Subscribe
permalink: /subscribe/
description: Follow Locus Publicus with any feed reader. No account, no algorithm, no tracking.
---

No newsletter, no account, no algorithm deciding what you get to see. Just a feed: you add it to a feed reader once, and every new post lands there on its own.

## Your feed address

<div class="abo-feld">
  <input id="feed-url" type="text" readonly value="{{ '/feed.xml' | absolute_url }}" aria-label="Feed address" onclick="this.select()">
  <button class="abo-knopf" type="button" id="feed-kopieren">Copy</button>
</div>

Paste this address into your feed reader where it says "add feed" or "subscribe".

## One click in a reader

- [Feedly](https://feedly.com/i/subscription/feed/{{ '/feed.xml' | absolute_url | uri_escape }})
- [Inoreader](https://www.inoreader.com/?add_feed={{ '/feed.xml' | absolute_url | uri_escape }})
- [NewsBlur](https://www.newsblur.com/?url={{ '/feed.xml' | absolute_url | uri_escape }})
- [Open the feed directly]({{ '/feed.xml' | relative_url }}) (many browsers and reader apps pick it up from there)

## No feed reader yet?

A feed reader is a mailbox for websites: you decide who gets in, and nobody sorts it for you. Free options are [NetNewsWire](https://netnewswire.com/) for Mac and iPhone, [Feeder](https://f-droid.org/packages/com.nononsenseapps.feeder/) for Android, or the web readers above.

<script>
  (function () {
    var knopf = document.getElementById('feed-kopieren');
    var feld = document.getElementById('feed-url');
    knopf.addEventListener('click', function () {
      feld.select();
      var fertig = function () { knopf.textContent = 'Copied'; setTimeout(function () { knopf.textContent = 'Copy'; }, 2000); };
      if (navigator.clipboard) { navigator.clipboard.writeText(feld.value).then(fertig, function () { document.execCommand('copy'); fertig(); }); }
      else { document.execCommand('copy'); fertig(); }
    });
  })();
</script>
