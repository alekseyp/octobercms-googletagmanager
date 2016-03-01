octobercms-googletagmanager-plugin
============

Google Tag manager plugin for October CMS.  Inspired by the [Google Analytics Plugin]
(rainlab/googleanalytics-plugin) from RainLab.

You can use default code on all pages or you can specify unique tag for specific pages.


## Instructions

1. Install the plugin via the October CMS backend.
2. Add your site configuration details to the Google Tag Manager Plugin configuration page. (Under the 'Misc' section of the System Settings page in the Backend).
3. Add the Google Tag Manager Component to your master layout.
4. Add ```{% component 'gtmCode' %}``` to the content of the default layout so that it appears immediately after the opening <body> tag.
5. Save the file.

You can also add the component to the file manually and/or override container_id from your settings.  For Example:

    [gtmCode]
    container_id = "GTM-XXXXXX"
	==
	<html>
	<head>
		<title>{{ this.page.title }}</title>
		<meta name="author" content="October CMS">
    	<meta name="viewport" content="width=device-width, initial-scale=1.0">
    	{% styles %}
    	<link href="{{ [
    	    'assets/css/theme.css'
    	]|theme }}" rel="stylesheet">
	</head>
	<body>
 		<header>
 			<h1>Header</h1>
 			<hr />
 		</header>

 		<!-- Content -->
        <section id="layout-content">
            {% page %}
        </section>

        <!-- Footer -->
        <footer id="layout-footer">
            {% partial "footer" %}
        </footer>

        <!-- Scripts -->
        <script src="{{ [
            'assets/js/jquery.js',
            'assets/js/app.js'
        ]|theme }}"></script>
        {% framework extras %}
        {% scripts %}
        {% component 'gtmCode' %}
	</body>
	</html>
	
	
	
License
-------

MIT

Author Information
------------------

Aleksey Potaneyko

Mediahub