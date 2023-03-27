# RTB-House-S2S-GTM-SS
RTB House Google Tag Manager Serve-Side template for S2S integration


Data is passed to the server-side container primarily by firing GA4 tags in the web container.
● Google Analytics: GA4 Configuration tag
○ Send to server container enabled
○ Server container url set
● Google Analytics: GA4 Event tag
○ Configuration Tag set as the server-side GA4 Configuration tag
○ Triggered on the corresponding web container event
○ Web variables can be passed from web -> server by defining them as event
parameters for each GA4 Event tag.

First party cookies can be accessed inside the server-side container so long as the server
container is set up as a subdomain of the web container website.

○ E.g. if the web container is implemented on www.example.com, the server
container must be configured as a subdomain, such as ssgtm.example.com
○ Instructions for custom domain configuration

Important: for event data to be made available in the server-side container, GA4
Configuration and/or Event tags must be set up to pass the necessary information for
each event that you want to tag.

RTB House AID Template
This template can be used in the GTM Web Container to create a tag that will do the following:
● Set/get a local storage identifier: __rtbhouse.lid
● Set/get a first party cookie: __rtbh.aid
● Collect site url and site referrer from the page (su / sr params)
● Fire an iframe multi tag with the following:
○ aid tag
○ lid tag
○ su
○ sr

Import
● Navigate to the Templates section of your GTM Web Container and select Tag Templates > New
● On the top right, open options and select Import
● Select the RTB House AID Template - Beta.tpl file, and hit Save.

Configuration
● Create a new tag in your GTM container and choose RTB House AID Template - Beta
● Select the Tagging hash and Region provided by your RTB House representative
● Set a trigger to fire this tag at least once per session when a user first arrives on the
website. Alternatively this tag can be fired on every page view.
