# WebPageTest Test Results
Automatically triggered by [WebPageTest](https://www.webpagetest.org)'s GitHub Action.

## Overall Budget Specs
firstContentfulPaint: <%- tests.specs.median.firstView.firstContentfulPaint %>

<% tests.forEach((test) => { %>
## Page Tested:<%- test.url %>
**Full test results: <%- test.testLink %>**
### Budget Specs
firstContentfulPaint: <%- test.specs.median.firstView.firstContentfulPaint %>

| <% test.metrics.forEach((metric) => { %><%- metric.name %> | <% }); %>
| <% test.metrics.forEach((metric) => { %>--- | <% }); %>
| <% test.metrics.forEach((metric) => { %><%- metric.value %> | <% }); %>

<% if (test.show_waterfall) { %>
![Image of waterfall](<%- test.waterfall %>)
<% } %>
<% }); %>
