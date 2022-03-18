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


## Configuration

Following properties can be configured:


| Option                       	| Description
| ---------------------------- 	| -----------
| `header`                     	| The header text to display <br><br> **Type:** `string` <br> **Default value:** `"My Volvo"`
| `scanInterval`               	| The interval fetchting informations from that API. <br><br> **Type:** `string` <br> **Default value:** `10 * 60 * 1000` // 10 Minutes
| `units`                      	| The metrics shown km/h, mp/h. <br><br> **Type:** `string` <br> **Possible values:** `metrics`, `us`, `imperial`, `kr` <br> **Default value:** `metrics`
| `info`                   		| Display the details of your car: car license plate, model and construction year. <br><br> **Type:** `boolean` <br> **Possible values:** `true` or `false` <br> **Default value:** `false`
| `graphic`                     | Display a graphic of your Volvo. (see below _Volvo Graphic Gallery_). <br><br> **Type:** `string` <br> **Default value:** `"v90.png"`
| `status`               		| Display the general information from your car: Fuel amount, Avg. Speed, Fuel Level ect. <br> ![](https://raw.githubusercontent.com/mazim-co/MMM-MyVolvo/master/gallery/status_example.png)<br><br> **Type:** `boolean` <br> **Possible values:** `true` or `false` <br> **Default value:** `true`
| `notice`               		| Display details from vehicle status: Doors looked, Engine on/off, Tyre ok, Windows open/closed. <br> ![](https://raw.githubusercontent.com/mazim-co/MMM-MyVolvo/master/gallery/notice_example.png)<br><br> **Type:** `boolean` <br> **Possible values:** `true` or `false` <br> **Default value:** `true`
| `trip`              			| Display the last trip. Depature and Destination as well as the trip details. <br> ![](https://raw.githubusercontent.com/mazim-co/MMM-MyVolvo/master/gallery/trip_example.png)<br><br> **Type:** `boolean` <br> **Possible values:** `true` or `false` <br> **Default value:** `true`

## Volvo Graphic Gallery
__Option 1:__ You can select your Volvo from the gallery folder.
   * As in the sample config above, write the .png file into next to `graphic: "file.png"`

__Option 2:__ Upload your own graphic and save it in the graphic folder. You reference that as in Option

__Option 3:__ Hide the graphic by just leaving `graphic: ""` blank.

![](https://raw.githubusercontent.com/mazim-co/MMM-MyVolvo/master/gallery/model_overview.png)









