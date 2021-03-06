# This repo is no longer maintained. 
<img src="images/logo/logo_347x50_PPa11y.png" alt="PayPal accessibility logo">
amCharts Accessibility Plugin by the PayPal Accessibility Team. See the [Authors](#authors) section below for more information.

## What is it?
This plugin provides accessibility enhancements for a very versatile chart library from [amCharts.com](http://www.amcharts.com). Once applied, the plugin enables navigation for keyboard users and provides the necessary support for screen reader users.

Watch a [screencast of the plugin in action](http://paypal.github.io/amcharts-accessibility-plugin/media/SR_amChartsAccessibility.mp4) or try the live demo below:

[<img src="images/amchart_screenshot.png" alt="Demo of amCharts Accessibility Plugin">](http://paypal.github.io/amcharts-accessibility-plugin/demo.html)

## Installation instructions
Download the [amCharts Accessibility Plugin](plugins/amstock-accessibility.min.js) from the amCharts Accessibility Plugin Github page and include it after the amCharts stock JavaScript on your site.

For example, here is the plugin called after amStock.js:

```html
<script type="text/javascript" src="http://www.amcharts.com/lib/amstock.js"></script>
<script type="text/javascript" src="/js/amcharts-accessibility-plugin/plugins/amstock-acessibility.min.js"></script>
```

## Keyboard interaction
After the plugin is applied to the amCharts code, the following keyboard navigation becomes possible:

  - When focused on the chart, the left and right arrow keys navigate between the data points of the chart. To aid the navigation, the cursor tooltip is shown when the arrow keys are pressed.
  - The Tab and Shift+Tab keys navigate between the chart, "Start Date" and "End Date" sliders that allow the user to control the date ranges for the chart.

## Screen reader features
  - When navigating between the data points on the chart, the values on the x-axis and y-axis will be spoken.
  - A "start of chart" and "end of chart" messages will be spoken when the start and the end of chart  data is reached.
  - When changing the values for the "start date" or the "end date" sliders, the values will be read as well.
  
## Implementation notes
  - This plugin utilizes [WAI-ARIA roles, states and properties](http://www.w3.org/TR/wai-aria/) to enable the meaningful spoken feedback for screen reader users.
  - The chart is a Div container with a role of application and aria-label and tabIndex of 0 in order to receive focus.
  - A status Div is used to announce the tooltip to screen reader users. It is hidden offscreen and aria-live is set to polite and aria-atomic is set to true.
  - The left slider is an SVG element which has aria-label, aria-valuemin, aria-valuemax, aria-valuetext and aria-valuenow.
  - The right slider is also an SVG element with aria-label, aria-valuemin, aria-valuemax, aria-valuetext and aria-valuenow. 

## Known issues
The slider functionality doesn't work in Firefox as there is a bug in this browser which prevents an SVG element inside an SVG document getting focused. See [this issue](https://bugzilla.mozilla.org/show_bug.cgi?id=778654) for more information.

## Update
Recently updated to work with amstockchart_3.20.5 . The changes are in [branch  3.20.5](https://github.com/paypal/amcharts-accessibility-plugin/tree/3.20.5) .

## Feedback and Contributions
Please do not hesitate to open an issue or send a pull request if something doesn't work or you have ideas for improvement. For instructions on how to contribute to this project please read the [contribution guide](CONTRIBUTING.md).

## <a name="authors">Authors</a>
  * Prem Nawaz Khan, primary developer on the project.
[https://github.com/mpnkhan](https://github.com/mpnkhan) || [@mpnkhan](https://twitter.com/mpnkhan)

  * Victor Tsaran, project lead, documentation, user interaction and testing
[https://github.com/vick08](https://github.com/vick08) || [@vick08](https://twitter.com/vick08)

  * The rest of the PayPal Accessibility Team

## Copyright and license
Copyright 2015, PayPal under [the BSD license](LICENSE.md).
