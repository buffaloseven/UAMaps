# UAMaps

Script for plotting meteorological upper air maps.


## Dependancies

* Python 3.9+
* Metpy 1.3.0
* Siphon 0.9
* Matplotlib 3.5.2
* Cartopy 0.20.2
* Pandas 1.4.2



## Usage

uaplot.py takes options for plotting latest maps or past maps. To plot the latest map run the following in your terminal,


```bash
python uaplot.py --latest
```


This will plot the latest 12z or 00z maps depending on the time at which the program is run. Data is from the [University of Wyoming sounding archive](https://weather.uwyo.edu/upperair/sounding.html). 

Maps from past dates can also be plotted by passing a --date=YYYYMMDDHH argument. Note: The HH must be either 12 or 00. For example

```bash
python uaplot.py --date=2022052300 
```

This will plot a UA map from May 23, 2022 at 00 UTC. 


Certain levels can also be chosen to be plotted by passing a levels arguement. For example,

```bash
python uaplot.py --latest --levels=850,500
```

This will only plot the 850 mb and 500 mb charts. When the levels argument is not passed, all standard levels will be plotted (250, 300, 500, 700, 850 and 925). 


There are also two additional options: --td and --te for plotting dewpoint temperature on the station plot and contouring theta-e instead of temperature for 700, 850 and 925 mb. For example,

```bash
python uaplot.py --latest --td --te 
```

This will plot dewpoint on the station plot for 850 and 925 (700 mb will always default to dewpoint depression) and theta-e for 700, 850, and 925 mb instead of temperature. A solid red line (0 degrees C) will always be plotted on 700, 850, and 925 mb to highlight the freezing level, and a brown 10 degrees C line on 700 mb is also always plotted for thunderstorm analysis.