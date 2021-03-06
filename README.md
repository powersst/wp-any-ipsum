# Any Ipsum
[WordPress plugin](https://wordpress.org/plugins/any-ipsum/) to roll your own custom lorem ipsum generator - used by the [Bacon Ipsum](http://baconipsum.com/) web site

[![Code Climate](https://codeclimate.com/github/petenelson/wp-any-ipsum/badges/gpa.svg)](https://codeclimate.com/github/petenelson/wp-any-ipsum)

## What's in here?

- **wp-anyipsum.php** - WordPress plugin wrapper (loades classes, registers core hooks, etc)
- **readme.txt** - Info for the WordPress repo
- **uninstall.php** - WordPress uninstall code
- **assets/** - Assets for the WordPress plugin repository
- **lang/** - For future translastions
- **lib/**
  - **admin-help** - Help page for the plugin
  - **default-custom.txt** - Default custom text (meat)
  - **default-filler.txt** - Default filler text (lorem ipsum)
  - **class-WPAnyIpsumCore.php** - Exposes filters used by other classes
  - **class-WPAnyIpsumForm.php** - Shortcode for generating the form to allow visitors to generate your custom filler
  - **class-WPAnyIpsumSettings.php** - Admin settings for managing your custom filler text
  - **class-WPAnyIpsumWPCLI.php** - WP-CLI commands
  - **class-WPAnyIpsumAPI.php** - API endpoint (supports JSON and plain text)
  - **class-WPAnyIpsumOembed.php** - oEmbed endpoint
  - **class-WPAnyIpsumGenerator.php** - The WPAnyIpsumGenerator class for generating custom filler text.

## Revision History

### v1.8.1 January 8, 2016 ###
- Fixed a bug that was always showing the 'Starts with' text (thanks @ghost_harrenhal)

### v1.8.0 December 1, 2015 ###
- Changed the WP-CLI generate-posts output to display a progress bar instead of individual posts (can be toggled via --no-progress-bar)

### v1.7.0 November 30, 2015 ###
- Added --category support to WP-CLI, pass in either an ID, slug, or name
- Added --excerpt support to WP-CLI, pass this flag to use the first sentence of the post content as the post excerpt
- Added 'anyipsum-filler-wp-cli-insert-post-args' filter to allow modifications of the post insert args before each new post is created
- Added 'anyipsum-filler-wp-cli-post-inserted' action which is fired after each new post is created, passes post_id

### v1.6.1 September 18, 2015 ###
- Added WP-CLI support for generating posts.  Try 'wp help any-ipsum generate-posts' for more info
- Fixed a bug with sentence mode generating a random number of sentences

### v1.5.0 June 19, 2015 ###
- Action 'anyipsum-filler-generated' is fired after either the shortcode or API generates any custom filler (useful for logging)

### v1.4.1 July 30, 2015 ###
- Fixed a missing </div> tag in the form

### v1.4.0 June 9, 2015 ###
- Added 'html' format to API, which wraps each paragraph in <p> tags.
- Added range values for the 'paras' parameter to allow random number of paragraphs, ex: paras=3-7
- Added charset to Content-Type header for all API calls
- Added Content-Length header for all API calls

### v1.3.0 May 29, 2015 ###
- API now supports a 'format' parameter to specify return format
- 'text' return format added to return ipsum in plain text

### v1.2.3 March 27, 2015
- Trim each word before adding it to a sentence

### v1.2.2 March 6, 2015
- Bux fix for API POST requests

### v1.2.1 March 4, 2015
- Code refactoring to use filter_input() and better WordPress coding standards
- Fixed activation bug that was not setting up the initial oEmbed settings

### v1.2.0 January 7, 2015
- Added admin notice to visit settings page on plugin activation
- Bug fix for sentences in JSON API

### v1.1.0 October 22, 2014
- Added a header for the form shortcode, ex: [anyipsum-form]Give our ipsum a try!  It's the best![/anyipsum-form]
- Added sentence mode for ipsum generators that want to use full sentences as custom words.
- The ipsum generator on baconipsum.com site is now powered by this plugin!

### v1.0.1 September 12, 2014
- Initial Release
