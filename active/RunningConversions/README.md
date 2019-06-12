# Running Conversions spec

## Problem Statement

Distance running is a constant interplay between space, time, and pain. Eavesdrop into any discussion between runners,
and you’ll be constantly hearing about paces, race times, interval splits, and hitting the wall. Athletes and coaches need
to convert between different speed, pace, and race time measures when they are planning their training or races. These conversions
are mentally difficult to perform, and even to think of an algorithm for, if the runner is not mathematically inclined.

## Evidence or User Insights

A [web search](https://www.bing.com/search?q=running+pace+conversion) can get us a lot of charts and online calculators that try to address this problem, but they usually provide conversions for a small set of data points, and only for a few measurements (usually between minutes per mile and minutes per kilometer
paces).

Yet, distance running is an extremely popular sport, and very available to everyone. In 2018, more than 18 million people registered
for road races just in the USA ([reference](https://runningusa.org/RUSA/News/2019/Running_USA_Releases_2019_U.S._Running_Trends_Report.aspx)). Helping this broad user base around the world easily solve their conversion problems would bring them one step closer to achieving their goals.

## Proposal

We propose to introduce a new conversion mode into Windows Calculator that would make these conversions easy for everyone interested
in or practicing running.

A typical list of measures would include:

* Speed: Miles per hour
* Speed: Kilometers per hour
* Pace: Minutes per mile
* Pace: Minutes per kilometer
* Race time: 5K
* Race time: 10K
* Race time: Half marathon
* Race time: Marathon
* Intervals: 200m time
* Intervals: 400m time
* Intervals: 600m time
* Intervals: 800m time

## Goals and Non-Goals

With this mode, a user would be able to solve real world problems such as:

* What pace do I need to run to achieve my goal 42:00 time in a 10K race?
* My training plan shows paces in minutes per kilometer, but I am using minutes per mile, how can I change them using Windows Calculator?
* What speed do I set the treadmill to for my interval workout? The plan specifies paces.
* What’s the target pace for 1’15” 400m intervals?
* If I could run as fast as Eliud Kipchoge when he achieved his latest Marathon world record, what would my 5K time be? (The right answer is “you probably can’t” but the calculator would show 14:24. Wow. I can't *think* that fast, let alone run.)

Non-Goals: Calculating race times and paces for other similar sports (such as cycling, race walking, etc.), and non-standard running race distances, including ultras.

## Success Criteria

<!-- How do we measure if things are successful? What’s the metric/KPI to track? Include proposed success metrics here. -->

## Feature Requirements

The key user stories of the feature are:

1. Users can switch Windows Calculator to Running conversions mode.
1. Users can convert between speeds, paces, standard race times, and interval training times.
1. Users can use mile-based or kilometer-based measurements where applicable, according to their preference.
1. When converting from a time or pace measurement, users can enter values that include hours, minutes, seconds, and tenths of a second.
1. When converting from a speed measurement, users can enter values with decimal digits.

## Feature Details and High-Fidelity Concept

| Scenario | Feature details |
| -------- | --------------- |
| Switching to Running conversion mode | [ModeSwitch.md](./ModeSwitch.md) |
| Conversion units | [Units.md](./Units.md) |
| Calculations | [Calculations.md](./Calculations.md) |
| Coverter UX | [UX.md](./UX.md) |
| "About equal to" | [SecondaryConversions.md](./SecondaryConversions.md) |

<!-- Show a detailed look at the experience. Make sure you cover all possible flows. Include any alternative designs that were considered. Call out if strings being used are proposed or final. Don’t forget about edge and error cases. Keep in mind compliance and other quality considerations. This should take the form of polished design comps and/or screenshots combined with textual descriptions. -->

## Appendix
<!-- Phases: For larger projects, it may be useful to break the plan into phases (e.g., crawl, walk, run). If applicable, detail that plan here. -->

<!-- Risks and Open Issues: Call out any open issues, if applicable. Waht's left to solve or agree on? -->

<!-- Resources: Include links to any additional documentation or resources, if applicable. -->
