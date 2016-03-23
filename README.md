![tools](/art/tools.png)

GWSDroidLibraryBuild
=====================

A set of gradle build scripts for android java application development. Lombok and retorlmabda are
not used with this set of build scripts. This set of build scripts also uses the more stable
android gradle 2.0.x series of the plugin rather than the newer one with Jack and Jill Tool Chain
enabled.

Its called GWSDroidLibraryBuild as I use it in the building of certain Android Libraries that I have
created.

# Usage

I deploy my libraries using Jitpack services so in your root build script:

```groovy
allprojects {
        repositories {
            jcenter()
            maven { url "https://jitpack.io" }
        }
   }
```

Than in the module buildscript:


```groovy
compile 'com.github.shareme:GWSDroidLibraryBuild:{latest-release-number}@aar'
```
the version number is located in the github releases tab at top of what your viewing and do not forget
to leave the at symbol and aar thing in place as it will not work without that suffix.

For this particular set of build scripts, just clone the github repo and modify for your own use.

# Set-UP

This set of build scripts and the other set that uses lombok and retrolambda are somewhat complex so
this set-up block details the settings of all the components used in this set of build scripts.

## App Signing Key

The general idea is that we do not store anything of value in local.properties or the gradle.properties
file at the user.home location. So for my demo apps of the libraries I store the demo key in the
buildsystem folder and access via gradle build scripts.

If it was a commercial app than if using a CI server I would pass everything encrypted using the
same SSH key I use for git provider access and the CI server would load that stuff as environment system
variables and than one would have to use gradle to read in those system environment variables to use
in the signing block.

## Espresso Instrumented Testing, System Animations

Rather than the whole set of narly work-arounds to disable system animations via gradle tasks and
some classes; i instead turn off system animations in all my test devices and emulators. It is somewhat
easier and is guaranteed to always work.

## Proguard Files

The proguard-matches-android-optimize.pro file is paired with the android-optimize. proguard file.
It still has the repackaging of a support library as we are still targeting 4.x devices with that
Samsung OEM goofup.

## Git Hash and Git Timestamp

In the app module build script we use the Git Hash and Git Timestamp as buildConfigFields
that way no matter what crash analytics packager is being used we can match up the crash
reports to the exact git commit.



# ChangeLog

* March 2016, first alpha release with Jack and Jill toolchain not enabled

# License

[Apache 2 License](http://www.apache.org/licenses/LICENSE-2.0)

# Credits

![GWS Logo](/art/gws_github_header.png)

[Fred Grott](https://gtihub.com/shareme/MyGithubProfile)

I Believe that diversity of culture combined with launching their lives wins in Android Mobile Application
development. Available for freelancing and other,remotely. Should not your start-up
Launch their Lives?

Only FUNDED start-ups and no recruiters(No recruiters, PLEASE!)

### Repos

[Github](https://github.com/shareme)
[Bitbucket](https://bitbucket.org/fredgrott)

### Social

[G+](https://plus.google.com/u/0/+FredGrott/about)
[Twitter](https://twitter.com/fredgrott)
[Facebook](http://www.facebook.com/fredgrott)
[Reddit](http://www.reddit.com./user/fredgrott/)
[GeekList](https://geekli.st/fredgrott)

### Bookmarks

[Delicious](https://delicious.com/shareme)

### Design

[DeviantArt](http://shareme.deviantart.com)
[BeHance](https://www.behance.net/gwsfredgrott)
[Dribbble](https://dribbble.com/FredGrott)

### StartUps

[AngelList](https://angel.co/fred-grott)
[BuiltINChicago](http://www.builtinchicago.org/member/fred-grott)
[HackerNews](https://news.ycombinator.com/user?id=fredgrott)
[FounderDating](http://members.founderdating.com/profile/6572)

### Freelancing

[GunIO](https://gun.io/accounts/shareme)

### Questions

[StackOverflow](http://stackoverflow.com/users/237740/fred-grott)
[Quora](http://www.quora.com/Fred-Grott)

### CV

[LinkedIN](http://www.linkedin.com/in/shareme/en)
[Xing](https://www.xing.com/profile/Fred_Grott?sc_o=mxb_p)

### Slides

[SlideShare](http://www.slideshare.net/shareme)
[SpeakerDeck](https://speakerdeck.com/fredgrott)

### Articles, Blogging

[Medium](https://medium.com/@fredgrott)
[Blogger blog](http://grottworkshop.blogspot.com)

### Video

[YouTube channel](https://www.youtube.com/channel/UCRQadYlHQ8DKRQ_WwUrfZ_w)
[Ustream](https://www.ustream.tv/manage-show/12940149)


### ProductHunt

[ProductHunt](https://www.producthunt.com/@fredgrott)



# Resources

[Google Android Developer Site](http://developer.android.com)

[Google Android Developer Tool Site](http://tools.android.com)

[Google Android Developer Blog](http://android-developers.blogspot.com/)

[CodeLabs](http://www.codelabs.io)

[StackOverflow Android Questions](http://stackoverflow.com/questions/tagged/android)

[Gradle](http://gradle.org)

[Reddit-androidev](http://reddit.com/r/androdev/)

[AndroidChat at Slack](https://androidchat.slack.com/messages/development/)

[Amazon Android Dev Site](https://developer.amazon.com/public)

[JavaRanch Android Forum](http://www.coderanch.com/forums/f-93/Android)

[Android Development Tools G+ community](https://plus.google.com/communities/114791428968349268860)

[Android Development G+ Community](https://plus.google.com/communities/105153134372062985968)

[Android Developers G+ Community](https://plus.google.com/+AndroidDevelopers/posts)

[Android Design G+ Community](https://plus.google.com/communities/113499773637471211070)

[UX Design for Developers](https://plus.google.com/communities/103651070366324568638)

[Android MVP G+ Community](https://plus.google.com/communities/114285790907815804707)



