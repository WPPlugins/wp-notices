# WP-Notices
Display notice messages to visitors, admin users, editors, contributors and anonymous readers. Notices can last forever, display between specific dates or at specified times of specified days regularly. Automatically convert notices to images if desired.
# Description
<p>WP Notices is a flexible way to display notices to readers.</p>

<p>Notices can be targeted by WordPress user role (admin, editor, contributor, author, subscriber, reader, anon or any other configured role), by WordPress capabilities (manage_plugins, read, delete_pages or any other configured capability) or targeted at a specific user.</p>

<p>Notice messages can be displayed as text or each message can be automatically converted to a PNG image. Useful for displaying advisory notices that you prefer search engines do not index as text. Useful for creating post images on the fly. The image directory is wiped periodically so download and move images to your WordPress media library if you want to keep them (remember to add them to the post as images from the media library).</p>

<p>The time or period of display can be set using natural language. Display notices forever (by leaving out a start and end time period), from a set start time to an open ended end date, for a specific day, range of days for one time or ad infinnitum. For example start="Thursday 8am" End="Friday" would display a notice every Thursday from 8am until start of Friday or start="Thursday 8am" End="Friday 4:30pm" would display a notice every Thursday from 8am until 4:30pm Friday; you can even say start="Wednesday 1st June 2016 8am" End="Friday 24th June 2016".</p>

<p>The notice can be styled to change its appearance. There are four inbuilt style classes (alert-success, alert-info, alert-warning and alert-danger).</p>

<p>There is a help message built into WP Notices. When using the WP Notices shortcode set help=\true\ to display the help information.</p>

<p>WP Notices is written to be used to display notices to specific users, user groups or to all readers. It can easily also be used as a flexible lightweight way to show page content to specific users (the style classes are optional) or as a membership plugin (though you would need to configure your membership roles manually).</p>

<p>WP Notices has been tested. It is known to work. If you find a bug, let us know. Support will be provided to fix bugs. We are busy with regular work duties so support may be slow on occasion and anyone who does not read the FAQs before posting a support request will be promptly pointed to read the FAQs.</p>

## How to Use
<p>See FAQ section for instructions.</p>

# Installation
## Automatic installation

<p>Automatic installation is the easiest option as WordPress handles the file transfers itself and you don’t need to leave your web browser. To do an automatic install of WP Notices, log in to your WordPress dashboard, navigate to the Plugins menu and click Add New.</p>

<p>In the search field type “WP Notices” and click Search Plugins. Once you’ve found this plugin you can view details about it such as the point release, rating and description. Most importantly of course, you can install it by simply clicking “Install Now”.</p>

## Manual installation

<p>The manual installation method involves downloading WP Notices and uploading it to your webserver via your favourite FTP application. The WordPress codex contains [instructions on how to do this here](https://codex.wordpress.org/Managing_Plugins#Manual_Plugin_Installation).</p>

## Updating

<p>Automatic updates should work fine. Ensure you backup your site just in case...</p>

# Instructions
<p>WP Notices is shortcode driven.</p>
<p>The shortcode with all attributes is:</p>

<p><strong>[wp-notice to='admin' class='alert alert-success' css='' start='Tuesday 1pm' end='Tuesday 5pm' image='portrait' format='c4' files='pdf,html,png' html5='false' help='true']</strong>Message to display to admin users every Tuesday between 1pm and 5pm.<strong>[/wp-notice]</strong></p>

<p>The shortcode has 10 attributes: to='', class='', css='', start='', end='', image='', format='', files='', html5='' and help=''.</p>
<ul>
 	<li><strong>to=''</strong> (required) is the addressee of the notice. This can be a WordPress user role, a WordPress capability or a registered username. Usernames must be prefixed with an <strong>@</strong>. See notes below for more details.</li>
 	<li><strong>class=''</strong> (optional) but determines the design of the notice. Any custom CSS class can be used. The default CSS classes are alert-info, alert-success, alert-warning and alert-danger. These correspond to Bootstrap alerts.</li>
 	<li><strong>css=''</strong> (optional) Add custom CSS to load inline or load the custom stylesheet stored in wp-content/uploads/wp-notices/css/custom.css. Use @ to load a file e.g. css='@'.</li>
 	<li><strong>start=''</strong> and <strong>end=''</strong> (optional) attributes set the start date and end date for the notice to display. These attributes accept the time of day as well. These attributes accept natural language date and time expressions as well as regular year-month-day formats. You can specify times after the date such as start='2016-12-28 10pm' end='2016-12-28 11pm'. Unless a time is specified, the start date will begin at 12 midnight and the end date will end at 12 midnight e.g start='1st Jan 2016' end='2nd Jan 2016' will count as 24 hours i.e start of day on the 1st to start of day on the second. If no end date is given then the end date will always default to 'tomorrow' i.e. never expires. State no start date to show the message forever. Want the notice to display at a particular period of the day every day? Specify times without dates.</li>
 	<li><strong>image=''</strong> (optional) is used to convert the notice into an image file. The image file is then displayed instead of any text. This is useful for when you prefer to not have text in a public notice indexed by a search engine. For example, you may need to display a sponsored post awareness message above posts; instead of displaying the message as text you can choose to display it as an image. The options are image='portrait' and image='landscape'. See the note below <strong>Custom Image Dimensions</strong> to learn how to specify exact image dimensions.</li>
 	<li><strong>format=''</strong> (optional) is used to specify the paper sized format of the images. For example, A4, B4 or C4. Adjusting this setting could improve legibility of the text within the image. The default value is C4. See notes below for more information.</li>
 	<li><strong>files=''</strong> (optional) Shows download links for HTML, PDF and PNG versions of the notice message. Separate each required file type with a comma e.g. files='pdf,html,png'. The download links expire one hour after creation.</li>
 	<li><strong>html5='false'</strong> (optional) is used to disable HTML5 support for the PDF creator. HTML5 support is enabled by default. Only use this attribute if HTML renders poorly.</li>
 	<li><strong>help=''</strong> (optional) Display link to shortcode help page and help messages (if any). Accepts a user role, user capability, username (@username) or admin.</li>
</ul>
<p>The message displayed can contain any HTML that is allowed within regular post content such as &lt;h1&gt;, &lt;p&gt;, &lt;em&gt;, &lt;strong&gt;, &lt;br&gt;, &lt;hr&gt;, &lt;ul&gt; and so on. If you use HTML tags that do not show in the message then that will be because they were filtered out.</p>

<p>As well as regular WordPress user roles and capabilities, there are several aliases you can use in the <strong>to=''</strong> attribute. For example to='admin' is the same as to='administrator', use 'anon' to reach all none logged in users, use 'loggedin' to reach all loggedin users and use 'everyone' to display your message to everyone.</p>

<p>User roles, capabilities and usernames cannot currently be combined to reach multiple groups or multiple users.</p>

<p>User roles are role specific e.g. to='admin' will display a message to admin users but not to editors, authors, contributors or subscribers.</p>

<p>Notices that target user capabilities cascade upwards to users with higher capabilities but not downwards to those with lower capabilities e.g. if the notice is to='delete_others_pages' then editors and admins will see the message (they both share this capability) but authors, contributors and subscribers will not see the message.</p>

<h2>Image inbuilt formats for format='' are ( <strong>format</strong> (width*height) ):</h2>
<ul>
 	<li>4a0 (4767.87, 6740.79)</li>
 	<li>2a0 (3370.39, 4767.87)</li>
 	<li>a0 (2383.94, 3370.39)</li>
 	<li>a1 (1683.78, 2383.94)</li>
 	<li>a2 (1190.55, 1683.78)</li>
 	<li>a3 (841.89, 1190.55)</li>
 	<li>a4 (595.28, 841.89)</li>
 	<li>a5 (419.53, 595.28)</li>
 	<li>a6 (297.64, 419.53)</li>
 	<li>a7 (209.76, 297.64)</li>
 	<li>a8 (147.40, 209.76)</li>
 	<li>a9 (104.88, 147.40)</li>
 	<li>a10 (73.70, 104.88)</li>
 	<li>b0 (2834.65, 4008.19)</li>
 	<li>b1 (2004.09, 2834.65)</li>
 	<li>b2 (1417.32, 2004.09)</li>
 	<li>b3 (1000.63, 1417.32)</li>
 	<li>b4 (708.66, 1000.63)</li>
 	<li>b5 (498.90, 708.66)</li>
 	<li>b6 (354.33, 498.90)</li>
 	<li>b7 (249.45, 354.33)</li>
 	<li>b8 (175.75, 249.45)</li>
 	<li>b9 (124.72, 175.75)</li>
 	<li>b10 (87.87, 124.72)</li>
 	<li>c0 (2599.37, 3676.54)</li>
 	<li>c1 (1836.85, 2599.37)</li>
 	<li>c2 (1298.27, 1836.85)</li>
 	<li>c3 (918.43, 1298.27)</li>
 	<li>c4 (649.13, 918.43)</li>
 	<li>c5 (459.21, 649.13)</li>
 	<li>c6 (323.15, 459.21)</li>
 	<li>c7 (229.61, 323.15)</li>
 	<li>c8 (161.57, 229.61)</li>
 	<li>c9 (113.39, 161.57)</li>
 	<li>c10 (79.37, 113.39)</li>
 	<li>ra0 (2437.80, 3458.27)</li>
 	<li>ra1 (1729.13, 2437.80)</li>
 	<li>ra2 (1218.90, 1729.13)</li>
 	<li>ra3 (864.57, 1218.90)</li>
 	<li>ra4 (609.45, 864.57)</li>
 	<li>sra0 (2551.18, 3628.35)</li>
 	<li>sra1 (1814.17, 2551.18)</li>
 	<li>sra2 (1275.59, 1814.17)</li>
 	<li>sra3 (907.09, 1275.59)</li>
 	<li>sra4 (637.80, 907.09)</li>
 	<li>letter (612.00, 792.00)</li>
 	<li>legal (612.00, 1008.00)</li>
 	<li>ledger (1224.00, 792.00)</li>
 	<li>tabloid (792.00, 1224.00)</li>
 	<li>executive (521.86, 756.00)</li>
 	<li>folio (612.00, 936.00)</li>
 	<li>commercial #10 envelope (684, 297)</li>
 	<li>catalog #10 1/2 envelope (648, 864)</li>
 	<li>8.5x11 (612.00, 792.00)</li>
 	<li>8.5x14 (612.00, 1008.0)</li>
 	<li>11x17 (792.00, 1224.00)</li>
</ul>
<h3>Custom Image Dimensions</h3>
<p>Custom image dimensions can be set using the attributes image='' and format=''. Instead of using image='landscape' or image='portrait' you can use image='@number', replacing number with an actual integer value such as image='@400'. Use format='' to specify the height e.g. format='300' (the @ sign is optional for format). For example, to describe an image of 400 points by 800 points, use image='@400' format='800'.</p>
<h2>Reference Links</h2>
<p><a href="http://php.net/manual/en/datetime.formats.relative.php" target="_blank">PHP natural language time reference information (Relative Times)</a>.</p>

<p><a href="https://codex.wordpress.org/Roles_and_Capabilities" target="_blank">WordPress roles and capabilities list</a>. These are used in the "to" field.</p>

# Questions
<strong>Why do iFrames and videos not show in image mode?</strong>
<p>This is a limitation of the software used to create PDFs. In order to create images we first convert the notice message to PDF format. The PDF is then converted to an image. The image is what you see.</p>
<p>iFrame content will display as a non-clickable link.</p>

<strong>Can I use images in the notice message?</strong>
<p>Yes you can. Add the image as you normally would for a post or text widget.</p>

<strong>Can I use shortcodes within the WP-Notices shortcode (nested shortcodes)?</strong>
<p>Yes.</p>

<strong>Can I use background images?</strong>
<p>Yes. Either in the CSS or using the background='' attribute.</p>

<strong>Can I use my own CSS?</strong>
<p>Yes. Use the css='' attribute to add CSS style attributes. Use css='@' to load the custom.css stylesheet. The custom.css stylesheet is in wp-content/wp-uploads/wp-notices/SITE-ID/css/custom.css</p>
<p>We are still deciding whether to allow specific custom CSS files to be called. The option may be added at a future date.</p>

<strong>Why does my notice message not include my CSS styles when image mode is used?</strong>
<p>The CSS style rules must be loaded through css='' either as inline styles or through the custom.css file. This is because PDF creation (which leads to image creation) takes place outside of the WordPress core code.</p>

<strong>Why do some messages still show after the message has expired?</strong>
<p>This is caused by a limitation in cache plugins. We can either not cache pages that display notice messages (we're considering adding a nocache='' option but are worried notices shown in widget areas would then cause all pages to not be cached...) or we can ask you to clear the cache for specific pages or clear the cache for the whole site manually. We prefer to ask you to clear the page/site cache if you notice a message is cached too long.</p>
<p>We do send a 'Do Not Cache' alert to cache plugins for pages that display WP Notices to logged in readers. This prevents leakage to unintended readers.</p>

<strong>Can I use the shortcode in widget areas?</strong>
<p>You can. The WP Notices shortcode can be used in a text widget. Keep in mind that WP Notices sends a Do Not Cache alert to file cache plugins to prevent notice messages being displayed after expiration or to the wrong users. When you use WP Notices in a widget area you will need to use widget visibility controls, such as with the Jetpack Widget Visibility module, to narrow display of the text widget to only the pages where you want the widget to display. The next version of WP Notices will implement a method of notice display without need to disable page caching.</p>

<strong>Where can I send donations?</strong>
<p>Donations are welcome. They can be sent to us through [PayPal](https://paypal.me/vr51)</p>

<strong>Can I contribute</strong>
<p>Yes you can! Join us on [GitHub](https://github.com/VR51/WP-Notices/)</p>

# Changelog
1.2.2 - 9th September 2016

- WordPress 4.6.1 compatibility flag
-	Updated DOMPDF
- Moved dompdf directory from includes/dompdf to includes/vendor/dompdf. This fits in better with dompdf files being built via Composer

1.2.1 - 26th June 2016

- Added option to choose which download links to display of the files for PDF, HTML and PNG.
- Separated file creation into individual functions. Now file generation can happen whether images are created or not, but only if files='' is set.
- Added multisite compatibility.
- Forced no-caching of pages that display content to site members.
- Began process of converting the plugin into a class.

1.2.0 - 25th June 2016

- Security improvement. DOMPDF directory is renamed on plugin activation. The new name is created via a randomly generated sha2 hash. Directory name is created on plugin installation and is created afresh on reinstallation.
- New css='' attribute. This is used to specify inline CSS for the alert or to specify a custom CSS file to load from wp-notices/css (an upcoming version of WP Notices will include an options screen for CSS file management)
- Activation routine. Install directories wp-content/wp-notices/css and wp-content/wp-notices/tmp
- Deactivation routine. Plugin deactivation removes scheduled event and deletes the dirctory wp-notices/tmp. wp-notices/css remains intact in case it contains custom CSS files.
- Added file download feature. Files created during image creation can now be downloaded. Set files='true' to display a link below the image notice. A future update of WP Notices will move file creation to a separate process and thereby permit file downloads for none image notices too.

1.1.0 - 24th June 2016

- Enabled HTML5 support for dompdf. Enabled by default.
- Introduced new shortcode attribute to disable HTML5 support. html5=''. Set to fals to disable HTML5 support.
- Fixed typos in plugin index.php. The intro info needed a few fixes.
- Enabled nested shortcode support. Notices can include shortcodes.
- Added filter to enable oEmbeds and shortcodes in text widgets. Undecided whether to keep this filter in index.php or move it to the FAQ section.
- Added test for ImageMagick support. Conversion of PDFs to images requires ImageMagick. No ImageMagick = no image creation. Help message when enabled displays warning when ImageMagick is not enabled.
- Adjusted help='' attribute to accept @username, a WordPress user role, WordPress user capability or admin as the intended viewer of the help notice.
- Added option to set custom image dimensions using image='@number' format='number' (width & height).

1.0.0 - First Public Release

23rd June 2016

# Upgrade Notice