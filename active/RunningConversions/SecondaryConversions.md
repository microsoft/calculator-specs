# Secondary coversions

Secondary conversions in the Windows Calculator display a subset of the alternative target conversions at the bottom of the window, along
with one "real-world" conversion that is not available in the drop down and its goal is to give users a feeling how the value
translates into the everyday experience. The alternative target conversions differ in number, depending on the available space
(defined by the window size).

In the Running conversion mode, we propose the following approach to selecting secondary conversions.

## Alternative target units

The simplest approach to selecting alternative target units, which we are recommending, is to start from the ordered list of units
as detailed in [Units.md](./Units.md), remove the selected source and target units from this list, and then display the N first
calculations (where N is calculated from the available space in the window using the same approach as in all other conversions).

## "Real-world" target units

The two options considered for the "real world" target units are:

* Use the same units as in the "Speed" conversion category, which will probably result into "horses" being shown in
most occasions.
* Use existing world records (and record holder names) in well known running distances, such as the 100m dash and the Marathon.

While the latter approach is more relevant to the Running category, it requires monitoring and update of the metric
each time world records change.
