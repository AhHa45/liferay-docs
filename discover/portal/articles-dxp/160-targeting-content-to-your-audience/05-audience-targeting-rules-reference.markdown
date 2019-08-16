---
header-id: liferay-audience-targeting-rules
---

# Liferay Audience Targeting Rules

Rules enable Audience Targeting administrators to define how users are
classified into the user segments they create.

Basically, a rule evaluates if the current user matches or not one or several
conditions. Rules can be configured and combined differently for each user
segment to create a very specific classification algorithm. A user must match
all rules in a user segment to be classified into it.

## Behavior Rules

These rules allow to classify users based on their navigation behavior.

These rules will not work properly if content tracking or page tracking is not
enabled. They can be enabled in *Control Panel* &rarr; *Configuration* &rarr;
*Instance Settings* &rarr; *Audience Targeting Analytics* (for portal level
configuration) or in Site Administration &rarr; *Configuration* &rarr; *Site
Settings* &rarr; *Advanced* &rarr; *Audience Targeting Analytics* (for site
level configuration).

### Content Visited

Evaluates if the user has visited the selected content.

### Page Visited

Evaluates if the user has visited the selected page.

### Previously Visited Site

Evaluates if the user has visited a specific site before visiting the current
site. The site's URL can be evaluated based on whether it contains or starts
with defined text.

For example, if you'd like to segment users based on whether they navigated to
your site from Twitter, you could define a Twitter URL for this rule.

### Score Points

Evaluates if the user has visited any page or content categorized under this
user segment a number of times equals or higher than the configured threshold.

## Social Rules

These rules allow you to classify users based on their profiles in social
networks (e.g., Facebook).

These rules will not work properly if login through the specific social network
(Single Sign On) is not enabled and properly configured. Follow these steps to
enable Facebook Single Sign On in Liferay:

1. Sign in to the [Facebook Developers site](https://developers.facebook.com)
   and add a new App. For more information, read the
   [Facebook app developer guide](https://developers.facebook.com/docs/apps).
   After going through all the steps, you'll finally have a new app with an
   Application ID and an Application Secret.

2. Log in as a Portal administrator in your @product@ and go to *Control Panel*
   *Configuration* &rarr; *Instance Settings* &rarr; *Authentication* &rarr;
   *Facebook*. Check *Enabled* and copy your Application ID and Application
   Secret to their respective fields. Finally, click *Save*.

3. To verify that the Facebook Single Sign On works properly, sign out and then
   click the Facebook option in the Sign In box. Enter your Facebook username
   and password in the prompted pop-up and click *Login*. You should be
   automatically signed in to your Liferay Portal with your Facebook user.

Your Facebook app, by default, only provides access to certain user attributes
(e.g., gender, age, number of friends). For the Facebook City, Facebook
Education, and Facebook Page Like rules to evaluate properly, you must declare
this information accessible in your Facebook app. @product@ cannot read this
information from Facebook users without these granted permissions.

Read the
[Integrating with Facebook](/docs/7-0/user/-/knowledge_base/u/integrating-with-facebook-twitter-and-more#integrating-with-facebook)
section for more information on using Facebook with @product@.

### Facebook Age

Evaluates if the age in the user's Facebook profile is in the configured range.

### Facebook City

Evaluates if the city in the user's Facebook profile matches the configured
value.

### Facebook Education

Evaluates if the education in the user's Facebook profile matches the configured
values.

### Facebook Friends

Evaluates if the user has more or less friends in Facebook than the selected
value.

### Facebook Gender

Evaluates if the gender in the user's Facebook profile matches the selected
value.

### Facebook Page Like

Evaluates if the user likes the configured Facebook page.

## User Attributes Rules

These rules allow you to classify users based on the attributes.

These rules will not work properly if the corresponding attributes from the user
profile are not available. Follow the given instructions for each rule in such
cases.

### Age

Evaluates if the age in the user's profile is in the configured range.

### Custom Field

Evaluates if the value set for the selected custom field matches the value from
the user's profile.

### Gender

Evaluates if the gender in the user's profile matches the selected value.

### Organization Member

Evaluates if the user is member of the selected organization.

### Organization Role

Evaluates if the user has the selected role assigned in the selected
organization.

### Regular Role

Evaluates if the user has the selected regular role assigned.

### Site Member

Evaluates if the user is a member of the selected site.

### Site Role

Evaluates if the user has the selected role assigned in the selected site.

### User Group Member

Evaluates if the user is member of the selected user group.

### User Signed In

Evaluates if the user is signed in to the portal.

## Session Attributes Rules

These rules allow you to classify users based on their session attributes.
Session attributes usually refer to the context in which the user accesses.

These rules will not work properly if the corresponding session attributes
are retrieved through any tools that are not currently available or properly
configured. Follow the given instructions for each rules in such cases.

### Access Time

Evaluates if the user is accessing at a time that is within the configured
range. Notice that the reference time is that of the server.

### Browser

Evaluates if the user is accessing with the selected browser.

### Device

Evaluates if the user is accessing with the selected device.

This rule is based on the existing Device Families. To manage Device Families,
go to *Site Administration* &rarr; *Configuration* &rarr; *Mobile Device
Families*.

### IP Range

Evaluates if the user is accessing with an IP with the configured range.

### Language

Evaluates if the user is accessing with the selected language.

### Last Login Date

Evaluates if the last login date of the current user was after, before, or
between the selected dates.

### Location

Evaluates if the user is accessing from a country and region that match the
configured values.

### Operating System

Evaluates if the user is accessing with the selected Operating System.

### Sign Up Date

Evaluates if the Sign Up date of the current user was after, before, or between
the selected dates.

In this chapter, you learned how to use Liferay's Audience Targeting app. This
app allows you to define custom user segments, target specific content to
different user segments, and create campaigns for different user segments.
Liferay's Audience Targeting app allows you generate reports so that you can
measure the effectiveness of your campaigns. Liferay's Audience Targeting app
also includes a simulator so that you can preview how your site would appear to
users belonging to different user segments. You can create user segments by
applying various rules that reference session attributes, profile attributes,
behavior, and possibly other information, such as information from social
networks. It's also easy for developers to create additional rules and rule
types.
