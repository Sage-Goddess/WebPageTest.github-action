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
* Reference: https://docs.webpagetest.org/metrics/page-metrics/
* Schema Ref: https://gist.github.com/Nooshu/ff463b3cbc95ffe75da16224cb217fd5
```json
{
  "median": {
    "firstView": {
      "TTFB": {
        "min": 4000,
        "max": 10000
      },
      "firstContentfulPaint": {
        "min": 4000,
        "max": 10000
      },
      "TotalBlockingTime": {
        "min": 1000,
        "max": 6000
      },
      "chromeUserTiming.LargestContentfulPaint": {
        "min": 9000,
        "max": 20000
      },
      "chromeUserTiming.CumulativeLayoutShift": {
        "min": 0.10,
        "max": 0.15
      },
      "render": {
        "min": 2000,
        "max": 6000
      },
      "visualComplete": {
        "min": 4000,
        "max": 15000
      },
      "domContentLoadedEventEnd": {
        "min": 4000,
        "max": 10000
      },
      "SpeedIndex": {
        "min": 2000,
        "max": 1200
      },
      "requests": {
        "min": 85,
        "max": 215
      }
    }
  }
}

```
<% }); %>
