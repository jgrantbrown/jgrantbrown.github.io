---
layout: post
title:  "An Outstanding and Overdue look at the .toLocaleString() method.""
date:   2017-04-04 03:06:34 +0000
---


https://2old2code.wordpress.com/
In search of a blogpost, I dug deep into the Javascript methods. I found one that I had not come across before an thought it needed some love. Since, writing technical blogs has not been my strength at this point in my programming career, why not try something completely out of my comfort zone.

So, with out further ado, lets look at:

Date.prototype.toLocaleString()

dateObj.toLocaleString([locales[, options]])
Running the below Date method

new Date();

Returns the date in the following default format of current location.
DayofWeek-Month-Day-Year-Hour-Minute-Second-GreenwichMeanTime/Offset and Current time zone
=> Mon Apr 03 2017 21:38:51 GMT-0400 (EDT)

We can use the .toLocaleString method and pass a locales code.
A few sample codes and link to a full list:
Language codes of interest:

Type: language
Subtag: ar
Description: Arabic

Subtag: ca
Description: Catalan

Subtag: de
Description: German

Subtag: el
Description: Modern Greek (1453-)

Subtag: en
Description: English

Subtag: es
Description: Spanish
http://www.iana.org/assignments/language-subtag-registry/language-subtag-registry

I tested passing both a language and region code:

var date =new Date();
console.log(date.toLocaleString('en-US'));

4/3/2017, 10:45:53 PM
OR with passing en-GB

var date =new Date();
console.log(date.toLocaleString('en-GB'));

03/04/2017, 22:47:06
Also available are several options that can be passed.

Using English as language US as region and several of the options arguments:

console.log(date.toLocaleString('en-US', { hour12: false }));
console.log(date.toLocaleString('en-US', { hour12: true }));
console.log(date.toLocaleString('en', {weekday: 'long', year: 'numeric', month: 'long', day: 'numeric'}));

4/3/2017, 22:51:49
4/3/2017, 10:51:49 PM
Monday, April 3, 2017
Using German as language Germany as region:

console.log(date.toLocaleString('de', { hour12: true }));
console.log(date.toLocaleString('de-DE', { weekday: 'long', year: 'numeric', month: 'long', day: 'numeric' }));
console.log(date.toLocaleString('de-DE'));

3.4.2017, 10:51:49 nachm.
Montag, 3. April 2017
3.4.2017, 22:51:49
BONUS

Using arabic:

console.log(date.toLocaleString('ar',{ weekday: 'long', year: 'numeric', month: 'long', day: 'numeric' }));

Returns:

الاثنين، ٣ أبريل، ٢٠١٧

tumblr_m1tsnyMX4A1rqfhi2o1_400


