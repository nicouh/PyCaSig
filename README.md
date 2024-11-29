
# PyCaSig
GUI based Python program to analyze calcium spike trains.

## Info
Excel/.csv files containing multiple spike trains and text files containing single spike trains can be loaded.
Excel files have to include headers including the keywords 'time' and 'ratio'/'ROI' with the time and amplitude data in the columns below.

When viewing a single spike, the baseline can be modified. All spike properties will be computed based on the new baseline. Resetting to the internally computed baseline is possible by pressing the corresponding reset button.

The checkboxes of the individual spikes enable or disable them for export.
When a spike train is marked in the spike train list, pressing enter will activate or deactivate all spikes of that spike train for export.

Analysis intervals can be set, which will affect the output when exporting results.

### Spike info box
The abbreviations in the spike info box are:
* `pos`: time value of peak,
* `amp`: amplitude as y-distance from baseline to peak value,
* `hw`: half-width value of peak in seconds at half of amplitude,
* `rise`: rise time from 10% of 90% of amplitude,
* `decay`: decay times from peak value to 50%, 70%, and 90% of amplitude,
* `area`: area between baseline and signal,
* `fit const.`: rate constant and its inverse of an exponential fit to a peak.

## Peak finding properties
Peak finding is variable and depends on parameters set in the upper right box.
* `dist.`: minimum distance between peaks, in data samples.
* `amp.`: minimum amplitude of peaks.
* `threshold`: minimum (y-)value of peaks.
* `width`.: minimum half width of peaks.

Possible candidates not fulfilling these criteria will not be recognized as peaks.

## Settings
A settings file, `pycasig_settings.ini`, will be generated up on start. It stores file properties set by previous use. These are
* parameters used for peak finding per spike train,
* baseline values per spike,
* analysis intervals per spike train,
* export boolean per spike.

Also, general settings can be used to set standard values for peak finding and the font size of the program.
```
    [general_settings]
    peak_params_spiketrain_default = [5.0, 100, 1000, 1.0]
    font_size_pixels = 12
```

On file basis, default peak finding parameters can be set using
```
    [some_spiketrains.csv__e78abb948646a6b85db5ed99edd2e556]
    peak_params_spiketrain_default = [5.0, 0.5, 0.5, 1.0]
```

## Shortcuts
* (Up/Down) browse spikes and spike trains
* (Left/Right) browse spike trains
* (e) edit baseline
* (r) reset data
* (s) show exp. fit
* (d) export details
* (z) little spike zoom out
* (x) little spike zoom in



