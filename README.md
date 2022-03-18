# MMM-MyVolvo [![license](https://img.shields.io/github/license/mashape/apistatus.svg)](LICENSE) 

MMM-MyVolvo is a MagicMirror module. The module retrieves informations from your Volvo through the Volvo Cars API. 

![](https://raw.githubusercontent.com/mazim-co/MMM-MyVolvo/master/gallery/example.png) 

## Notice

This module is based on the intital module from [eouia](https://github.com/eouia/MMM-VolvoOnCall) (archived).
- This module uses unofficial and not-well-supported methods to retrieve sensitive information of the car.
- There is no legal right or duty for data and module's working. All responsibility for using is on yours.
- For safety, there are no remote-controllable features on this module. (like heater on, engine start, door unlock)
- Since the community of Volvo owners with a MagicMirror are small, I wasn't able to test that in detail. There could be the possibility of bugs. 
- I'm a developer beginner and just started to learn programming. I might not able to help you with issues. There is always a great [community](https://forum.magicmirror.builders/) available who is able to help.

## Dependecies
- The module visualize the information that it receives from the python script, developed by [molobrakos](https://github.com/molobrakos/volvooncall).

## Requriements
- Volvo Car owner with an **active Volvo ID and the Volvo Cars App**.
 - Works for all connected cars up to model year 2021, excluding the XC40 Recharge.
- Python 3.8 or higher.

## Installation
_coming soon_


## Sample Config
```javascript
{
  module: "MMM-MyVolvo",
  header: "MyVolvo V90 T4",
  position: "top_left",
	config: {
		display: {
			info: false,
			graphic: "v90.png",
			status: true,
			notice: true,
			trip: true,
			}				
		},
},
```

## Volvo Graphic Gallery
1. Option: You can select your Volvo from the gallery folder.
 * As in the sample config above, write the .png file into next to `graphic: "file.png"`
2. Option: Upload your own graphic and save it in the graphic folder. You reference that as in Option.
3. Option: Hide the graphic by just leaving `graphic: ""` blank.

![](https://raw.githubusercontent.com/mazim-co/MMM-MyVolvo/master/gallery/model_overview.png)









