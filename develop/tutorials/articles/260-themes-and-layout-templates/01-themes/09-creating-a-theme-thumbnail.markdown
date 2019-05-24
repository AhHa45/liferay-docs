---
header-id: creating-a-theme-thumbnail
---

# Creating a Theme Thumbnail

Theme thumbnails help users quickly identify your theme. It's especially
important to provide thumbnails when your theme offers 
[color schemes](/docs/7-0/tutorials/-/knowledge_base/t/specifying-color-schemes). 

Here's how to create a proper thumbnail image for your theme:

1.  Create a thumbnail image. Make sure it's 150 pixels wide by 120 pixels high.
    You may want to take a snapshot of your theme and re-size it to these
    dimensions. **Your thumbnail must be these exact dimensions** or the image 
    won't display properly. 

2.  Save the image as a `.png` file named `thumbnail.png` and place it in the
    theme's `images` folder (create this folder if it doesn't already exist). On 
    redeployment, the `thumbnail.png` file automatically becomes the theme's
    thumbnail.

| **Note:** The
| [Theme Builder Gradle plugin](/docs/7-0/reference/-/knowledge_base/r/theme-builder-gradle-plugin)
| doesn't recognize a `thumbnail.png` file. If you're using this plugin to build
| your theme instead, you must create a `screenshot.png` file in your theme's
| `images` folder that is 1080 pixels high by 864 pixels wide. The thumbnail is
| automatically generated from the screenshot for you when the theme is built.

Now, when you apply the theme, its thumbnail displays along with the other
themes that are available to your site.

![Figure 1: Your theme thumbnail is displayed with the rest of the available themes.](../../../images/available-themes-thumbnail.png)

Congrats! Now you know how to create a thumbnail image for your theme!

## Related Topics

[Liferay Theme Generator](/docs/7-0/tutorials/-/knowledge_base/t/themes-generator)
[Specifying Color Schemes in Your Theme](/docs/7-0/tutorials/-/knowledge_base/t/specifying-color-schemes)
