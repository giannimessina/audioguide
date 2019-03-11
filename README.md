# Static Museum Audio Guide

A static site theme for building lightweight audio tours for exhibitions or museums.

## Overview

This template is built to create Audio Guide in simple way.

Image editing / Photoshop skills will be required to build a finished guide. 

Parts of the theme  will need to be customised for your guide.

The audio guide features the following main pages:

- `/welcome` - an onboarding page to get users started with the audio guide.
- `/` - a menu with headphone icons to begin using the guide.
- `/stops/1` - an individual audio guide stop, with slide-down menu, hero images in a carousel, and fixed footer audio player.

The guide will work best with 128kbps 16-bit 44.1khz MP3 files.

There is also a simple page at `/connected` as a landing page if you are using Captive Network WiFi pages. Redirect post login pages to this page, and the anchor tags with `target="_system"` should make the links open in Safari on iOS devices.

## Getting Started

1. Each audio guide stop is just a page in Jekyll terms, using a layout called `episode`.
2. Meta-data should be added to the top of each audio guide stop as follows:
  - `layout` - this should be set to `episode`
  - `permalink` - the default structure is `/stops/1` (replace the number with the desired permalink)
  - `type` - set this to `stop` - type is used for generating the slide down menus
  - `section_title` - this appears at the top of each stop page
  - `title` - this is a sub-heading, but is typically the name of the actual object in the exhibition, and is used as the title of the page.
  - `page_rank` - this is used to order the stops in the menu and slide-down menu
  - `stop_id` - if you wanted, you could give the stop a different ID number to its page rank, but you should probably keep it the same as the permalink and page_rank.
  - `audio_file` - just the filename and extension of the MP3 file to play
  - `hero_images` - an array of `path` and `alt_text` values for the hero image on the audio guide stop page. Multiple images will appear in an image carousel (using Slick JS). Good image settings for this are 512 x 341 pixels (1.5:1 aspect ratio) JPEG at 50 - 60% compression.
3. Update `config.yml` with settings for your particular guide. You can use the default settings, but be sure to update the `title`, `description`, `url` and `twitter` usernames for your site. If you want to change the folder structure for the MP3s or hero images, you can do that here.
4. Update `/assets/img/meta/og-image.jpg` with an image you'd like to have appear when the site is shared on social media. (This is used for Open Graph tags, pulled by Facebook and other sites).
5. To change colour scheme, update the variable `$brand-color` in `css/main.scss` with your main colour. Most of the other colours in the web app will be calculated from this one.
6. Add Font import or @font-face statements to `_sass/_fonts.scss` and update `$base-font-family` in `_css/main.scss` to swap fonts.
7. Once you're happy with your content and have updated all styling and branding above. Navigate to a stop in the audio tour and take screenshots at mobile resolution.
13. Update the images in `assets/img/welcome` with these screenshots from your own web app.
14. In `_layouts/welcome/html` update the mark-up of the welcome pages to give an overview to your web app.
15. Once you're happy with your audio guide, drop in your own Google Analytics or Google Tag Manager snippet into `_includes/tagmanager.html`.

Each time you update the JS or CSS files, you may wish to update `version_number` in `config.yml`. This is appended a query string to the CSS link and JS script tag in the Head element for [cache busting](https://css-tricks.com/strategies-for-cache-busting-css/).


## Modifications and reused code snippets

The above snippet allows you to easily use markdown includes in the site, however it breaks support for Github pages, so we've removed useage from this repo. In the index.html page for example, you could use `{% markdown overview.md %}` to include the markdown text in `overview.md` without having to write HTML. The on boarding pages could also be refactored to use this.

## Included JS libraries

Most of the web app (aside from audio!) works without JavaScript, and we've tried to keep to a progressive enhancement approach as much as possible. The following JS libraries have been included here, each is covered by their own MIT license also in the repo. If you're extending this project, you may wish to switch to CDN copies, or concatenate and minify your libraries.


## Other people using this project



## License

The Museum Audio Guide theme is released under the terms of the MIT license. Included JS libraries are covered by their own licenses, included in this repo.
