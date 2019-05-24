---
header-id: getting-ids-paths-and-sign-in-details-in-javascript
---

# Getting IDs, Paths, and Sign-in Details in JavaScript

In Java, developers are used to being able to find lots of context information
at runtime. You can learn about what user is browsing your application, what
page it's on, what site it's in, and lots more. Wouldn't it be great if you
could access that same information in JavaScript? You can! You can use Liferay's
`ThemeDisplay` JavaScript object!

It's a part of the `Liferay` global object that's automatically available to you
in Liferay at runtime. You can refer to the object as `Liferay.ThemeDisplay`.
The `ThemeDisplay` object provides information on many aspects of a portal.
It can identify the portal instance, the current user, the user's language, and
the user's navigational context. It can tell you the paths to a portlet's
scripts and images, a theme's images and files, and a portal's main folder. And
it lets you know if a user is signed in and if the user is being impersonated.
You can quickly assess your portal surroundings with `ThemeDisplay`. 

This tutorial describes some of the most commonly used `ThemeDisplay` methods
for getting IDs, paths, and user sign-in details. 

## Retrieving IDs

Using the `ThemeDisplay` methods below, you can grab IDs of various portal
elements: 

**getCompanyId:** Returns the
[company ID](/participate/liferaypedia/-/wiki/Main/Company+ID). 

**getLanguageId:** Returns the user's language ID. 

**getScopeGroupId:** Returns the
[group ID](/participate/liferaypedia/-/wiki/Main/Group+ID) of the current site. 

**getUserId:** Returns the
[user's ID](/participate/liferaypedia/-/wiki/Main/User+ID).

**getUserName:** Returns the user's name. 

Now that you know how to retrieve IDs of some of Liferay's key elements, you
can learn how to get paths to various deployed entities in the portal. 

## Retrieving File Paths

The `ThemeDisplay` object has methods for retrieving commonly used file paths.
Below are a few of the methods: 

**getPathImage:** Returns the relative path of the portlet's image directory. 

**getPathJavaScript:** Returns the relative path of the directory containing the
portlet's JavaScript source files. 

**getPathMain:** Returns the path of the portal instance's main directory. 

**getPathThemeImages:** Returns the path of the current theme's image directory. 

**getPathThemeRoot:** Returns the relative path of the current theme's root 
directory. 

Now that you know how to retrieve paths to Liferay's deployed entities, you can
next learn how to get information about the current user. 

## Retrieving Login Information

Here are a couple methods related to the current user. 

**isImpersonated:** Returns `true` if the current user is being impersonated.
Authorized administrative users can
[impersonate](/docs/6-2/user/-/knowledge_base/u/the-users-section-of-the-control-panel#user-management)
act as another user to test that user's account. 

**isSignedIn:** Returns `true` if the user is logged in to the portal. 

Below is JavaScript code that demonstrates using `ThemeDisplay`'s `isSignedIn`
method: 

    if(Liferay.ThemeDisplay.isSignedIn()){
        alert('Hello ' + Liferay.ThemeDisplay.getUserName() + '. Welcome Back.')
    }
    else {
        alert('Hello Guest.')
    }

The example above alerts a signed in user with a personalized greeting.
Otherwise, it defaults to a guest greeting. Although this is a basic example, it
shows how you can easily define unique user experiences with the `ThemeDisplay`
object. 

## Related Topics

[Getting Browser and Platform Details in JavaScript](/docs/6-2/tutorials/-/knowledge_base/t/getting-browser-and-platform-details-in-javascript)

[User Interfaces with AlloyUI](/docs/6-2/tutorials/-/knowledge_base/t/alloyui)

[User Interfaces with the Liferay UI Taglib](/docs/6-2/tutorials/-/knowledge_base/t/liferay-ui-taglibs)
