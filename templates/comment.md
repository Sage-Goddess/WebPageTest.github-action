# WebPageTest Test Results
Automatically triggered by [WebPageTest](https://www.webpagetest.org)'s GitHub Action.

<% tests.forEach((test) => { %>
## Page Tested:<%- test.url %>
**Full test results: <%- test.testLink %>**

| <% test.metrics.forEach((metric) => { %><%- metric.name %> | <% }); %>
| <% test.metrics.forEach((metric) => { %>--- | <% }); %>
| <% test.metrics.forEach((metric) => { %><%- metric.value %> | <% }); %>

<% if (test.show_waterfall) { %>
![Image of waterfall](<%- test.waterfall %>)
<% } %>

## Budget Specs Set - wpt-budget.json
* Based off Staging Averages
```
"firstView": {
      "firstContentfulPaint": 2000,
      "TTFB": 1232,
      "render": 1900,
      "visualComplete": 14400,
      "domContentLoadedEventEnd": 2900,
      "SpeedIndex": 11700
}
```
<% }); %>
