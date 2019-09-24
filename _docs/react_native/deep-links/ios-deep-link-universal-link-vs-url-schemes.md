# iOS Deep Link: Universal Link vs URL Schemes‌

## [https://www.adjust.com/blog/universal-links-vs-deep-links/](https://www.adjust.com/blog/universal-links-vs-deep-links/) 

### What are 'Universal Links'? 

[Universal links](https://www.adjust.com/glossary/universal-linking/) are Apple’s way of launching apps on their operating system from a website, also known as a web view. They link to content inside an app or website, giving iOS users an integrated mobile experience.

Broadly, there aren’t many differences between [universal links](https://www.adjust.com/glossary/universal-linking/) and traditional [deep links](https://www.adjust.com/glossary/deep-linking/). However, universal links are exclusive to Apple devices, and have the ability to open a web page from an application

## [https://stackoverflow.com/questions/35522618/universal-links-on-ios-vs-deep-links-url-schemes](https://stackoverflow.com/questions/35522618/universal-links-on-ios-vs-deep-links-url-schemes) 

Universal links is the iOS's capability of sending web url request to a given app, instead of opening them in the browser.

URL-schemes is an apps ability to open in a given state, described by the url, and handled in code by the developer.

Say you have an app called "Cool App", and you've registed the **url-scheme** "coolapp". And your app have different areas like "Nice gadgets" and "Nice stuff". Now you can open your app with at link link `coolapp://nice-gadgets`. To make the app open on the nice gadget section, you have to implement the [`application(_:openURL:options:)`](https://developer.apple.com/library/ios/documentation/UIKit/Reference/UIApplicationDelegate_Protocol/index.html#//apple_ref/occ/intfm/UIApplicationDelegate/application:openURL:options:) method, and within this discover the requested url, and make the app open the requested view controller.

At the same time you have a website called `www.coolapp.com`. When browsing using an iOS device, and you come across a link to your site - say `www.coolapp.com/nice-gadgets`, and opening the link, it will open in the browser. By enabling universal links it will open the app instead by calling the [`application(_:continueUserActivity:restorationHandler:)`](https://developer.apple.com/library/ios/documentation/UIKit/Reference/UIApplicationDelegate_Protocol/index.html#//apple_ref/occ/intfm/UIApplicationDelegate/application:continueUserActivity:restorationHandler:) method given the url as parameter. From here you can use the same logic from the url scheme handling, to open the app in the requested state.

So will universal links replace url schemes? I doubt it, but they are going to compliments each other in a nice way.

Are universal links deep links? No, but they can initiate the process of using deep links within an app.

