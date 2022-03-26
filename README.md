# MMM-MyVolvo [![license](https://img.shields.io/github/license/mashape/apistatus.svg)](LICENSE) 

MMM-MyVolvo is a MagicMirror module. The module retrieves informations from your Volvo through the Volvo Cars API. 

![](https://raw.githubusercontent.com/mazim-co/MMM-MyVolvo/master/gallery/example.png) 

## Notice

This module is based on the initial module from [eouia](https://github.com/eouia/MMM-VolvoOnCall) (archived).
- This module uses unofficial and not-well-supported methods to retrieve sensitive information of the car.
- There is no legal right or duty for data and module's working. All responsibility for using is on yours.
- For safety, there are no remote-controllable features on this module. (like heater on, engine start, door unlock)
- Since the community of Volvo owners with a MagicMirror are small, I wasn't able to test that in detail. There could be the possibility of bugs. 
- I'm a developer beginner and just started to learn programming. I might not able to help you with issues. There is always a great [community](https://forum.magicmirror.builders/) available who is able to help.

## Dependencies
- The module visualize the information that it receives from the python script, developed by [molobrakos](https://github.com/molobrakos/volvooncall).

## Requirements
- Volvo Car owner with an **active Volvo ID and the Volvo Cars App**.
 - Works for all connected cars up to model year 2021, excluding the XC40 Recharge.
 - For the moment it only works for cars registered in Germany. A german license plate is required (e.g. AB-CD 123, or AB-CD 123E).
- Python 3.8 or higher.

## Installation
The installation is divided in two parts: Installation `volvooncall` and `MMM-MyVolvo`
<br>
#### Part 1: Installing `volvooncall` python programm.
**Check and install Python3.6.** To find out which version of Python you have, open a terminal window and typ the following commands:
```shell
# Check the system Python version
$ python --version
# Check the Python 3 version
$ python3 --version

# If you have Python on your machine, then the command should respond with a version number.
# For example, if you already had Python 3.6.10 on your computer, then the python3 --version command would display that version number:
Python 3.6.10
```
#If you haven't Python3.6 or higher, you need to install the requried version. Follow the recommended steps from [realpython.com/installing-python](https://realpython.com/installing-python/#how-to-build-python-from-source-code)

**Install volvooncall**
```shell
cd ~
git clone https://github.com/molobrakos/volvooncall.git
cd volvooncall
# Install the programm
python3 setup.py install
```
**Authorization**
```shell
# Create a new file .voc.conf
touch .voc.conf

# Edit file with nano
nano .voc.conf

# Add your credentials
username: <username> #Your VOC ID (email address)
password: <password> #Your Volvo Passwort

# Save & Exit:
# CTRL+X than respond by entering either “Y” or “N”. Since we are trying to save our changes, press “Y” and hit enter.
```
**Testing**
```shell
# Pull information from the VOC API
voc list

# You should get following example response: Licence Plate, Type/Year, VIN
HH-GS 1869 (V90/2019) YV1PWXXXXXXX95578
```


#### Part 2: Installation `MMM-MyVolvo` module.

```shell
# Access the Module folder from you MagicMirror
cd ~/MagicMirror/modules
# Clone Repository and install
git clone https://github.com/mazim-co/MMM-MyVolvo
cd MMM-MyVolvo
npm install
```


## Sample Config
```javascript
{
  module: "MMM-MyVolvo",
  header: "MyVolvo V90 T4",
  position: "top_right",
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
| `scanInterval`               	| The interval fetching informations from that API. <br><br> **Type:** `string` <br> **Default value:** `10 * 60 * 1000` // 10 Minutes
| `units`                      	| The metrics shown km/h, mp/h. <br><br> **Type:** `string` <br> **Possible values:** `metrics`, `us`, `imperial`, `kr` <br> **Default value:** `metrics`
| `info`                   		| Display the details of your car: car license plate, model and construction year. <br><br> **Type:** `boolean` <br> **Possible values:** `true` or `false` <br> **Default value:** `false`
| `graphic`                     | Display a graphic of your Volvo. (see below _Volvo Graphic Gallery_). <br><br> **Type:** `string` <br> **Default value:** `"v90.png"`
| `status`               		| Display the general information from your car: Fuel amount, Avg. Speed, Fuel Level ect. <br> ![](https://raw.githubusercontent.com/mazim-co/MMM-MyVolvo/master/gallery/status_example.png)<br><br> **Type:** `boolean` <br> **Possible values:** `true` or `false` <br> **Default value:** `true`
| `notice`               		| Display details from vehicle status: Doors looked, Engine on/off, Tyre ok, Windows open/closed. <br> ![](https://raw.githubusercontent.com/mazim-co/MMM-MyVolvo/master/gallery/notice_example.png)<br><br> **Type:** `boolean` <br> **Possible values:** `true` or `false` <br> **Default value:** `true`
| `trip`              			| Display the last trip. Departure and Destination as well as the trip details. <br> ![](https://raw.githubusercontent.com/mazim-co/MMM-MyVolvo/master/gallery/trip_example.png)<br><br> **Type:** `boolean` <br> **Possible values:** `true` or `false` <br> **Default value:** `true`

## Volvo Graphic Gallery
__Option 1:__ You can select your Volvo from the [graphics folder](https://github.com/mazim-co/MMM-MyVolvo/tree/main/graphics).
   * As in the sample config above, write the name of the .png file next to `graphic: "file.png"` 

   > **_NOTE:_**  Please access the folder to get the right name of the file from your graphic. For example in the overview it shows `XC90 Recharge` but the file is `xc90-hybrid.png`

__Option 2:__ Upload your own graphic and save it in the graphic folder. You can reference that as described in Option 1.

__Option 3:__ Hide the graphic by just leaving `graphic: ""` blank.

![](https://raw.githubusercontent.com/mazim-co/MMM-MyVolvo/master/gallery/model_overview.png)


