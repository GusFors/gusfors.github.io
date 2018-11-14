---
layout: post
comments: true
title:  "Svar på examination-1 frågor"
date:   2018-11-14 05:44:27 -0600
categories: exam-1
---

### What do you think of pre-compiling your CSS?
Jag tycker idén är väldigt smart och jag kan förstå hur det kan underlätta i längden med att kunna använda sig av t.ex variabler och nestling men hela upplevelsen med disqus och docker har varit väldigt strulig så jag har sett på det hela rätt så negativt men om jag skulle använda det separat skulle skulle jag förmodligen uppskattat det mer.

Jag använde mig av sass och provade på en del av funktionaliteten med variabler och att ändra fontstorleken med multiplikation men modifierade främst existerande kod.
Den största fördelen tycker jag är just den utökade funktionaliteten som jag förstår kan bli väldigt användbar när man vant sig vid det och kanske har ett större projekt att underhålla.
Den största nackdelen tyckte jag ändå var tiden det tog att sätta sig in i filerna och hur de fungerade. Det ökar även chansen för att det ska bli strul då man måste felsöka fler saker.
En annan är att debuggermeddelanden inte är exakta med sina radnummer vilket jag stötte på men det var jag ändå beredd på då Johan hade nämnt det.

### What do you think of static site generators?
Den första känslan var liknande den med ssgs, Varför ska man använda något som bara krånglar till syntaxen? Men när man väl fick sin första aha-upplevelse i hur man skulle använda t.ex "%- include head.html -%" i en layout så förstod jag. Det var dock ett jäkla krångel med att få blogposter till en annan sida än hemsidan vilket jag löste till slut. De lämpar sig bra för skalbara projekt där fart och säkerhet är viktiga och har även fördelen att allt material finns tillgängligt i git.

### What is robots.txt and how have you configure it for your site?
Robots.txt används för att instruera robotar, t.ex för att söktjänsters robotar inte ska gå till vissa sidor/filer på en webbplats. Anledningar kan vara att förhindra överbelastning och att undvika att inaktuella sidor ska dyka upp. Jag ställde in textfilen så att min sida inte ska indexeras av robotarna.
{% highlight ruby %} User-agent: * Disallow: / {% endhighlight %}

### What is humans.txt and how have you configure it for your site?

Humans.txt är en fil där allmän information om sidan och dess skapare finns. Det kan vara vilka personer som byggt sidan, vilka som designat den och sponsrat den etc. 
Jag fyllde i den med mitt namn, main email, var jag bor och när den senast uppdaterades.

### How did you implements comments to blog posts?
Jag började med att försöka med disqus som var rekommenderat, men det vägrade att fungera lokalt vilket gjorde det svårt att se om det fungerade. Jag hittade sedan alternativet "justcomments" som gick förhållandevis smärtfritt. Dock är det inte gratis så jag kommer överväga att prova disqus igen. Det var bara lägga in en scriptlänk och sedan en div där en apinyckel behövde läggas in.
{% highlight ruby %} <script async src="https://just-comments.com/w.js"></script>
 <div
    class="just-comments"
    data-allowguests="true"
    data-apikey="YOUR_API_KEY">
  </div> {% endhighlight %}

### What is Open Graph and how do you make use of it?
Open graph används när för att visa vad som ska visas när en sida länkas på t.ex sociala medier. Det implementeras genom att lägga till ett antal meta taggar i "head" i din HTML-fil.