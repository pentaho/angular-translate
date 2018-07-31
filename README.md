# [![angular-translate](https://raw.github.com/angular-translate/angular-translate/canary/identity/logo/angular-translate-alternative/angular-translate_alternative_medium2.png)](http://angular-translate.github.io)

> i18n for your Angular app, made easy!

## Pentaho version

This fork of angular-translate was created to legalize a patched version of angular-translate that was developed to support
Data Profiling (which ended up never being shipped) 
(see https://github.com/pentaho/pentaho-data-profiling-ee/blob/master/rest/hdfs/text/master/src/main/resources/webview/js/create/app.js#L54).

The patch was needed so that angular-translate would support `.properties` resource files.

At the time, a JAR was manually uploaded into Pentaho's NEXUS:
```xml
<dependency>
  <groupId>angular-translate</groupId>
  <artifactId>angular-translate</artifactId>
  <version>2.2.0-canary-pentaho-modified</version>
</dependency>
```

Strangely, the content of that JAR does not match exactly the `canary` branch of this repository, 
although it does seem to be based on it...

At the time, a PR was issued to angular-translate, with a similar implementation of this feature (to the one in NEXUS):
https://github.com/angular-translate/angular-translate/pull/706.
However, they ended up implementing it in a different way, and the PR was closed.

The Common-UI project is currently unpacking this jar and including it in its web resources directory.
You can find angular translate in a Pentaho Server at the location:

`pentaho-server/pentaho-solutions/system/common-ui/resources/web/angular-translate`

Common-UI directly includes (checked in source control) a 
`.properties` files parser that is then hooked to angular-translate:
https://github.com/pentaho/pentaho-platform-plugin-common-ui/blob/master/impl/client/src/main/javascript/web/angular-translate/properties-parser.js.

The marketplace project is using angular-translate version 2.2.0, 
but then it bundles its own version of the patched static loader and properties parser:
https://github.com/pentaho/marketplace/blob/c1a4f706c984ba6e44517945daa635be2559efca/marketplace-core/src/main/resources/web/js/app.js#L21,
which seems to have been derived from common-ui's patched version...

Some investigation is needed to determine if there are still any projects using the Common-UI version
and, consequently, if this repository is of any use.
Ideally, any existing code using angular-translate would be upgraded to use its current latest version.

## Original Read Me

### Status
| Branch        | Status         |
| ------------- |:-------------:|
| master        | [![Build Status](https://travis-ci.org/angular-translate/angular-translate.png?branch=master)](https://travis-ci.org/angular-translate/angular-translate) |
| canary        |[![Build Status](https://travis-ci.org/angular-translate/angular-translate.png?branch=canary)](https://travis-ci.org/angular-translate/angular-translate)     |
| BitDeli       |[![Bitdeli Badge](https://d2weczhvl823v0.cloudfront.net/angular-translate/angular-translate/trend.png)](https://bitdeli.com/free "Bitdeli Badge")        |

### Presentation (Dutch AngularJS Meetup 2013)
[![angular-translate Talk](presentation.png)](https://www.youtube.com/watch?v=9CWifOK_Wi8)

### Presentation (Kod.io 2014)
[![angular-translate Talk](presentation2.png)](https://www.youtube.com/watch?v=C7xqaExvaQ4)

### Links
* Website [http://angular-translate.github.io](http://angular-translate.github.io/)
* API Reference [http://angular-translate.github.io/docs/#/api](http://angular-translate.github.io/docs/#/api)
* Plato report [http://angular-translate.github.io/docs/plato](http://angular-translate.github.io/docs/plato)
* [Contribution Guidelines](https://github.com/angular-translate/angular-translate/blob/master/CONTRIBUTING.md)

### Useful resources
There are some very useful things on the web that might be interesting for you,
so make sure to check this list.

- [Tutorial on ng-newsletter.com](http://ng-newsletter.com/posts/angular-translate.html)
- [Examples and demos](https://github.com/angular-translate/angular-translate/wiki/Demos) - Currently on plnkr.co
- [Tutorial on angularjs.de](http://angularjs.de/artikel/angularjs-i18n-ng-translate) - German article
- [Tutorial on neoskop.de](http://www.neoskop.de/blog/angular-translate) - German article
- [angular-translate on GitHub](http://github.com/angular-translate/angular-translate) - The GitHub repository
- [angular-translate on ngmodules.org](http://ngmodules.org/modules/angular-translate)
- [angular-translate mailinglist](https://groups.google.com/forum/#!forum/angular-translate) - Discuss, ask et al!

### Thank you, community!
We got a lot of great feedback from the community so far! More and more people
use this module and they are always thankful for it and the awesome support they
get. I just want to make sure that you guys know: All this wouldn't have been
possible without these [great contributors](http://github.com/angular-translate/angular-translate/contributors)
and everybody who comes with new ideas and feature requests! So **THANK YOU**!
