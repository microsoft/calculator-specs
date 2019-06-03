# Calculations

Converting between the measures listed in [Units](./Units.md) requires a different calculation, depending on the kind
of the source and target measures (speed, pace, or time). Converting between pace and time measures is multiplication based,
while coverting between speed and pace/time is division based.

For example:

    (Race time: 5K) = 3.106855961 * (Pace: Miles per hour)

    (Pace: Minutes per kilometer) = 60 / (Speed: Kilometers per hour)

Division based conversions are symmetrical, i.e. if unit Ua and unit Ub have a division based conversion with factor F,
then:

    Ua = F / Ub

    Ub = F / Ua

For the 12 measures listed in [Units](./Units.md), setting up a full configuration matrix would require a minimum of
20 division based configurations and 36 multiplication based configurations for a total of 56.

The simplest way to manage this complexity is to make conversions with triangulation, i.e. converting the source value
to a base measure and then converting the base measure value to the target measure. Given the context of these conversions,
the precision loss incurred by rounding twice is considered not significant to the usefuleness of the result.

Given that 8 out of the 12 measures are kilometer based and 2 are mile based (marathon and half-marathon distances are "neutral" as in they don't have a primary internationally used measure), the base measure will be Speed: Kilometers per hour. The conversions from and
to the base measure are as follows.

| Value v | Factor f | To base b | From base b |
| ----- | ----- | ----- | ----- |
| Speed: Miles per hour | 1,609344 | b = v * f | v = b * 1 / f |
| Speed: Kilometers per hour | 1 | b = v * f | v = b * 1 / f |
| Pace: Minutes per mile | 96,56064 | b = f / v | v = f / b |
| Pace: Minutes per kilometer | 60 | b = f / v | v = f / b |
| Race time: 5K | 300 | b = f / v | v = f / b |
| Race time: 10K | 600 | b = f / v | v = f / b |
| Race time: Half marathon | 1266 | b = f / v | v = f / b |
| Race time: Marathon | 2531,7 | b = f / v | v = f / b |
| Intervals: 200m time | 12 | b = f / v | v = f / b |
| Intervals: 400m time | 24 | b = f / v | v = f / b |
| Intervals: 600m time | 36 | b = f / v | v = f / b |
| Intervals: 800m time | 48 | b = f / v | v = f / b |
