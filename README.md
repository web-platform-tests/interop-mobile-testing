# interop-2023-mobile-testing
Mobile Testing Investigation in Interop 2023

## Scope
Do the infrastructure work required to allow us to accept future Interop proposals that test mobile-specific functionality which can't be scored using the current desktop-only wpt CI.

## Roadmap

1. Write up the requirements and options for testing on mobile (e.g. provide dedicated hardware, use vendor results, use mobile-simulation mode in desktop browsers etc.) along with pros and cons of each.
1. Do a feasability study into the options (e.g. if resources are required can any participant help provide those).
1. Pick the option that appears most feasible.
1. Do infrastructure work required to stand up mobile testing given the selected option (e.g. implement fetching mobile browsers, downloading emulators, or whatever else is required)
1. Enable regular mobile testing and ensure the results are available on wpt.fyi.

Complete success would look like mobile results being available on wpt.fyi by the end of Interop 2023. Working out how such results would be used as part of a future Interop metric is explicitly out of scope, as are the addition of additional test APIs to support testing specific mobile features.

## Original Rationale

From the proposal: https://github.com/web-platform-tests/interop/issues/201

One of the great advantages of the web platform is that it can work across many devices and form factors. However some platform features, particuarly around layout, work differently on typical mobile devices compared to desktops.

Latest figures suggest that over half of all web traffic is coming from mobile devices. This suggests that interop concerns affecting mobile web experiences are especially important to end users. The webcompat project sees a large number of issues that are specific to mobile browsers, suggesting that mobile-specific interop problems do indeed cause noticable pain for end users.

Meanwhile web-platform-tests is only running regular testing on desktop browsers. This means that it's not possible to have Interop focus areas for mobile-specific features since they would be impossible to score. It also makes it harder for browser engineers to test and understand the interop landscape when it comes to mobile.

This lack of support for testing on mobile is blocking progress on areas of known interop concern. For example the Interop 2022 viewport investigation has considered the possibility of adding new test APIs to make it possible to test more areas, but these will be of limited utility unless it's possible to run tests using these APIs in CI.

Meanwhile browser vendors themselves do test on mobile; for example Gecko runs wpt on Android in project CI using wptrunner. This shows that the problem is not intractable, but there are obstacles to overcome in making mobile results available in a way that's useful to the interop process. More details about the current state of affairs and possible solutions are available in this RFC issue.
