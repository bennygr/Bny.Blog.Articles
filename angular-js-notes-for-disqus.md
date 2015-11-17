<!--
Title:"Disqus integration with AngularJS",
Date:"2015-11-16T19:19+0100",
Tags:"JavaScript, AngularJS, Disqus",
PreviewLength:"500",
PreviewCode:"6ab66dce-28bb-4746-b58a-90ec6e6172c8",
-->
Just a few notes for now:

- Put angular app in HTML5 mode
- Setup the the base URL using the base tag in the header
- Configure apache (See: https://github.com/angular-ui/ui-router/wiki/Frequently-Asked-Questions#how-to-configure-your-server-to-work-with-html5mode)
- Install https://github.com/michaelbromley/angularUtils/tree/master/src/directives/disqus
- Use ready-to-bind attribute
- ng-count: include jquery to execute scripts withing template
- ng-count: using jquery to load count script after the article has been loaded from resource

