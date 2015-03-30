---
category: home
layout: default
---

# What’s a Promise?

A [promise](http://wikipedia.org/wiki/Promise_%28programming%29) represents the future value of an asynchronous task.

# Sorry, What?

A promise is an object that wraps an asynchronous task. Pass that object around, and write clean, ordered code; a logical, simple, modular stream of progression from one asynchronous task to another.

{% highlight objective-c %}
[self login].then(^{

    // our login method wrapped an async task in a promise
    return [API fetchKittens];

}).then(^(NSArray *fetchedKittens){

    // our API class wraps our API and returns promises
    // fetchKittens returned a promise that resolves with an array of kittens
    self.kittens = fetchedKittens;
    [self.tableView reloadData];

}).catch(^(NSError *error){

    // any errors in any of the above promises land here
    [[[UIAlertView alloc] init…] show];

});
{% endhighlight %}

# Oh. Cool…?

Promises are neat because:

1. They make asynchronous operations chainable and standardized;
2. They clean up asynchronous spaghetti;
3. They simplify error handling;
4. Many objects can be notified about completion, not just one; and
5. They make your apps more robust.

# TL;DR?

Cocoa development can become a mess of asynchronous patterns, asynchronous boilerplate and flakey error handling. Promises solve these problems.

<div><a class="pagination" href="/then">Next: `then`</a></div>
