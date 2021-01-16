# Meeting finder web plugin

## Introduction
The purpose of the frontend module is to provide a tool for the areas and districts within CA to easliy let visitors of their website search and find meetings.

The frontend module, also referred to as the "plugin" is a meeting search tool that can be embedded on any website.

To get started you first need to get an account for the administration panel for your area. This is currently done by emailing your request to dev@ca.org.

A guide on how you add meetings using the administration panel will be linked from here soon.

## Setup

Once you have entered all you meetings you are ready to use the plugin.

To use the plugin you need to edit the html of the page where you want to embedd it and insert three tags.

```html
<div id="root"></div>
<link rel="stylesheet" type="text/css" href="https://meetings.ca.org/static/latest/css/standalone.css">
<script src="https://meetings.ca.org/static/latest/js/standalone.js"></script>
```

The following basic configuration is also necessary. Replace "Sweden" with your area. For oredring the options "CITY" and "DAY" are avilable. This options is poorly named at the moment but it defines how the meetings will be griuped when a search is done, experiment with this to see what suits your needs.

```html
<script>
window.caws_config = {
    area: "Sweden", 
    ordering: "CITY"
}
</script>
```

The final result should look like this.

```html
<script>window.caws_config = { area: "Sweden", ordering: "CITY" }</script>
<div id="root"></div>
<link rel="stylesheet" type="text/css" href="https://meetings.ca.org/static/latest/css/standalone.css">
<script src="https://meetings.ca.org/static/latest/js/standalone.js"></script>
```

You have now taken all the mandatory steps and the plugin is ready to be used. However you can configure the plugin further if you wish.

## Configuration

This section might be updated ever so often so please check out this page peridocally to see if any new features have been added.

Following is a complete custom configuration of the plugin. Any options can be omitted except "ordering" and "area".

```html
<script>
window.caws_config = {
    area: "Sweden", // Replace with your area
    ordering: "CITY", // Mandatory, can be either "CITY" or "DAY"
    geoSearchRadius: 500, // Limit the search radius in kilometers when the user searched using "Search close by"
    geoLimit: 100,
    showCount: 30
}
</script>
```