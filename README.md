# GST_2016-2017
Documentation for 2016 update

General Notes

	A. When renaming shapefiles, must manually change file path in CurrentMap .gprj file
		- Add shapefile to CurrentMap folder, then add through GST Layer Control
		- GST will rename all letters to lowercase by default

	B. In GST, Settings > Settings > Map > Save Map extent on exit

	C. We like the 1:10,000 default map scale, allows for two zooms to display addresses, hazmat & hydrants

	D. Use Beyond Compare to copy GST folder to other MDC to preserve xml styling

	E. Did NOT update to 2014 Aerial 

Goals

	A. Clearly identify shapefile version by changing naming conventions.  Breaking the year into four quarters (q1,q2,q3,q4)

	B. Maintain xml styles we already like

	C. Turn off SRA outside of SLU

FILES NEEDING NAME CHANGE ONLY

atoms, callboxes, CPN's, dpa_slu, dpa_state, expedited_launch_zone, local, major, mobile_homes_etc, PAZ, parcels

FILES NEEDING DATA UPDATE

address_points, buildings, pipelines, powerlines, railroads(?), Sirens, Solar(4), SRA(3), treatments

FILES OK AS IS

battalions, cdf_units, city_limits, counties, diablo_buildings, districts, firestations(3), freeways_state, hydrants, lakes, low_water_crossing, major_state, ownership, Pac_Ocean(2), Paso_fire_grid, Postmile_markers, ramp, ramp_state, rivers, slo_city_grid, slo_county, tsunami_inundation, wilderness

Updating shapefiles

	A. Using Quarter_Year naming convention (ex: buildings_q2_2016) with Fast File Renamer http://www.fastfilerenamer.com/download/

	B. Adding in new state layers (ex: SRA15_2, dpa_slu_15_3,dpa_state_15_3)

	C. Consolidated solar_blocks & solar_site_facilities (polygons layers) into solar_blocks_facilities_q2_2016

XML Styling

	New Layers
		1. Fire History
		2. Hazmat
		3. Schools
		4. Railroad Crossings

	Existing Layers we changed
		A. major, local(roads)- Aerial road name style to ?
		B. address_points- tools> layer control> label> Horizontal pixel offset (0), Vertical Pixel Offset (0) 

Day-by-Day Tasks

4/21- Add in new SRA15_2 for SLU, CA N, CA S. (need to delete old SRA from beta-test MDC)

4/25- Name changing for shapefiles, figure out state roads situation

	WORKFLOW
	1. Ensure the GST program is closed

	2. Open Fast File Renamer > Add Files > Navigate to C:GST/GST Mapper/CurrentMap/Files-to-be-renamed (can select all parts of shapefile by selecting first file > hold Shift + Ctrl> select last file)

	3. Input file name (without type) into the box labeled 'Original Pattern' (ex:expedited_launch_zone)

	4. Input new file name into box labeled 'New Pattern' (ex:expedited_launch_zone_q2_2016)

	5. Click 'Simulate' button to visualize changes without actually making them.  Ensure this is correct BEFORE performing rename.

	6. If the name change is correct, click 'Undo Simulate' button
	
	7. Lastly, click 'Perform rename'.  You will see your changes take effect instantly in the windows file explorer

4/26- Update shapefiles with new data (address_points_q1_2016, buildings_q1_2016, pipelines_q2_2016, railroads_slu, railroads_state, sirens_q2_2016, treatments_q1_2016, )

	Copy/paste gst.xml of old files to new, find and replace shapefile name

5/2- Add in new Layers (hazmat_sites_q2_2016, school_buildings_q2_2016)

5/6- Styling of new layers, correcting school addresses v. address points

5/9- Add in and style driveways, finish school addresses

5/10- Create ICS symbols, add to GST.  Import pre-attack layers, style.

5/12- Import and style ICS symbology

5/13- Style and display fire history

5/16- Document all display/label levels, back up newest cut to x drive, solve GPS issue

5/18- Beta Testing begins

5/24- Station 15 vehicles receive new version

5/25- Chiefs receive new version, version backed up on x

5/26- Turn mobile_homes_etc, parcels_q4_2015 layers on

5/27- Add in airport, change local roads to display at 100,000

5/31- 3419 recieves newest update 05312016

6/3- Send styled GST package for processing

6/6- Fix city_limits display settings, change:

	A. Move layer below districts

	B. Make layer selectable & visible on Aerial

	C. Change multiple displays to one symbol: Outline Yellow 3pt, 150 transparency for day, night, aerial

	D. Check box for field tab, city_name

6/7- Backup newest version, fix city boundaries to make visible and selectable

6/9- Reformat and combine firestations_slu, firestations_contract (now firestations_local). + firestations_USFS

	Turn driveways on at 10,000 zoom

	Change flammable symbols at SLO airport

6/10- Compile documents for "Chief Document Folder" (CCOP, FDOP, etc.) to reside on MDC Desktop

6/13- Make all layers selectable/identifiable. Add slu_helibase, slu_tactical_staging, slu_base_camp symbols.  Refine local fire history to 1900-2015

6/14- Add BLM layers blm_preferred_dozerline, blm_wilderness_sensitive_areas.  Insert and symbolize new fire stations layer, firestations_slu_all.

6/15- Export roads that are not already in GST from OpenStreetMap.

6/20- B3406 given new cut, fixed parcel and hazmat sites zoom layer issue.  What to do about state parcels, if anything?

6/22- New style for mobile_homes_etc layer labels

6/23- Development for new Santa Barbara GST begins

	1. Create new folder under GST Mapper> SBCurrentMap.  

	2. Copy/paste CurrentMap.gprj contents into new SantaBarbara.gprj file.

	3. Delete all shapefiles not needed for SB. 

	4. Only change needed to load this 'new' GST for Santa Barbara is to edit the 'default.gprj' file. Change text from 'CurrentMap.gprj' to 'SantaBarbara.gprj'

	5. Clip all needed data layers to SB County and style same as slo

	*Need to figure out way to easily switch to different GST when going out of county.  A button? 

	**We will do this same process for all counties/units surrounding slo; Monterey (BEU), Kern, Ventura

6/24- Speak with Fresno about how they switch between County GST's

6/30- Devise rollout plan by Battalion, solicit constructive feedback (cell-phone pics, screenshots, verbal, written)

	Day 1: Battalions 1,6

	Day 2: Battalions 2,4

	Day 3: Battalions 3,5

7/1- Create GST Quick Reference Guide

9/5- Updated shapefiles: dunes_oceano_points_q3_2016, dunes_oceano_roads_q3_2016

12/1- Beginning of driveways task manager in OSM for future-routing

**KEY LESSON**

A copy of the county's newest road geodatabase must be made and edited as a seperate file.  This is done to provide for attribute field schema differences between the data processing and routing of GST and CAD systems.

3/19- Removed 'Unnamed Rd' labels, as they are not helpful and take up space (visually)

3/20- In-house roads copy, then edit for GST-specific purposes using:

	GST Class	GST Description		FCC			Description
	A91					P00			High speed ramp
	A89		Freeway			P01			Interstate
	A90		Major			P02, P03		State Highway, Arterial (main thouroghfares)
	A40		Local			P04,P05,P06,P10, P11	Collector, light duty, alley, private, trail
	
3/21- Routing issues on Hwy 166, Morro, Calabaza Way, 5650 Farousse, new communities, trails (must change one_way field from B--->N in order to prevent routing up mountain bike/hiking trails)

3/23- In-house roads layer and OSM driveways used to edit roads in order to route up long, rural driveways.  For sending off road processing in GST, roads must be broken up at intersections. 

4/3- FCC code fixes for changing local--> major roads.  Addition of some trails to GST_roads layer from OSM export.

4/4- Trails: Bishop's Peak, Cerro San Luis, Irish Hills, Cuesta Grade

4/5- Send to GST for processing

4/8- Updated address points

4/21- Double-check road network for dangles in extra driveways using QGIS Disconnected Island Plugin http://plugins.qgis.org/plugins/disconnected-islands/
	
5/5- DPA/SRA clip for surrounding counties.  Also utilized QGIS 'FLoating Islands' Plugin for OSM roads to update roads, tracks network (view only, not routable) https://github.com/mjmarsh/QGIS_Plugins	

5/15- Addition of new extents layers: pre-attacks, interactive topo quads

**KEY LAYER STYLING XML**

	ADDRESSES:  <Symbol>
    <SymbolClassification>One symbol</SymbolClassification>
    <SymbolSize>12</SymbolSize>
    <LineShadeSymbol>0</LineShadeSymbol>
    <MarkerSymbol>X</MarkerSymbol>
    <MarkerSymbolSet>GST Symbol</MarkerSymbolSet>
    <LineSymbolSet>GST Symbol</LineSymbolSet>
    <ShadeSymbolSet>GST Symbol</ShadeSymbolSet>
    <MarkerSymbolIsImage>n</MarkerSymbolIsImage>
    <SymbolMarkerImagePath />
    <SymbolFGColor>0,255,128,64</SymbolFGColor>
    <SymbolBGColor>255,255,128,64</SymbolBGColor>
    <SymbolShadeOutlineColor>255,0,0,0</SymbolShadeOutlineColor>
    <SymbolShadeOutlineSymbol>0</SymbolShadeOutlineSymbol>
    <SymbolShadeImagePath />
    <SymbolFGColorNight>0,0,255,0</SymbolFGColorNight>
    <SymbolBGColorNight>255,0,255,0</SymbolBGColorNight>
    <SymbolShadeOutlineColorNight>255,0,255,0</SymbolShadeOutlineColorNight>
    <SymbolFGColorAerial>0,255,128,64</SymbolFGColorAerial>
    <SymbolBGColorAerial>255,255,128,64</SymbolBGColorAerial>
    <SymbolShadeOutlineColorAerial>255,255,128,64</SymbolShadeOutlineColorAerial>
    <SymbolField>id</SymbolField>
    <SymbolFieldValueList />
    <UseSymbolSizeByScale>n</UseSymbolSizeByScale>
    <SymbolSizeByScale />
    <ShowLineCasing>n</ShowLineCasing>
    <LineCasingColor>255, 78, 78, 78</LineCasingColor>
    <CasingScaleFrom>0</CasingScaleFrom>
    <CasingScaleTo>50000</CasingScaleTo>
 	 </Symbol>
	
	buildings: <Symbol>
    <SymbolClassification>One symbol</SymbolClassification>
    <SymbolSize>1</SymbolSize>
    <LineShadeSymbol>53</LineShadeSymbol>
    <MarkerSymbol>X</MarkerSymbol>
    <MarkerSymbolSet>GST Symbol</MarkerSymbolSet>
    <LineSymbolSet>GST Symbol</LineSymbolSet>
    <ShadeSymbolSet>GST Symbol</ShadeSymbolSet>
    <MarkerSymbolIsImage>n</MarkerSymbolIsImage>
    <SymbolMarkerImagePath />
    <SymbolFGColor>255,182,168,154</SymbolFGColor>
    <SymbolBGColor>255,255,128,64</SymbolBGColor>
    <SymbolShadeOutlineColor>255,0,0,0</SymbolShadeOutlineColor>
    <SymbolShadeOutlineSymbol>0</SymbolShadeOutlineSymbol>
    <SymbolShadeImagePath />
    <SymbolFGColorNight>255,52,154,184</SymbolFGColorNight>
    <SymbolBGColorNight>255,0,255,0</SymbolBGColorNight>
    <SymbolShadeOutlineColorNight>125,255,255,255</SymbolShadeOutlineColorNight>
    <SymbolFGColorAerial>70,155,163,232</SymbolFGColorAerial>
    <SymbolBGColorAerial>255,255,128,64</SymbolBGColorAerial>
    <SymbolShadeOutlineColorAerial>255,55,4,123</SymbolShadeOutlineColorAerial>
    <SymbolField>osm_id</SymbolField>
    <SymbolFieldValueList />
    <UseSymbolSizeByScale>n</UseSymbolSizeByScale>
    <SymbolSizeByScale />
    <ShowLineCasing>n</ShowLineCasing>
    <LineCasingColor>255, 78, 78, 78</LineCasingColor>
    <CasingScaleFrom>0</CasingScaleFrom>
    <CasingScaleTo>50000</CasingScaleTo>
  	</Symbol>
	
	DPA: <Symbol>
    <SymbolClassification>Multiple symbol</SymbolClassification>
    <SymbolSize>12</SymbolSize>
    <LineShadeSymbol>0</LineShadeSymbol>
    <MarkerSymbol>X</MarkerSymbol>
    <MarkerSymbolSet>GST Symbol</MarkerSymbolSet>
    <LineSymbolSet>GST Symbol</LineSymbolSet>
    <ShadeSymbolSet>GST Symbol</ShadeSymbolSet>
    <MarkerSymbolIsImage>n</MarkerSymbolIsImage>
    <SymbolMarkerImagePath />
    <SymbolFGColor>255,255,128,64</SymbolFGColor>
    <SymbolBGColor>255,255,128,64</SymbolBGColor>
    <SymbolShadeOutlineColor>255,0,0,0</SymbolShadeOutlineColor>
    <SymbolShadeOutlineSymbol>0</SymbolShadeOutlineSymbol>
    <SymbolShadeImagePath />
    <SymbolFGColorNight>255,0,255,0</SymbolFGColorNight>
    <SymbolBGColorNight>255,0,255,0</SymbolBGColorNight>
    <SymbolShadeOutlineColorNight>255,0,255,0</SymbolShadeOutlineColorNight>
    <SymbolFGColorAerial>255,255,128,64</SymbolFGColorAerial>
    <SymbolBGColorAerial>255,255,128,64</SymbolBGColorAerial>
    <SymbolShadeOutlineColorAerial>255,255,128,64</SymbolShadeOutlineColorAerial>
    <SymbolField>dpa_agency</SymbolField>
    <SymbolFieldValueList>BLM»GST Symbol,23,150,128,0,0,0,252,226,203,210,128,0,0,0,2,,150,128,0,0,0,45,45,45,255,128,0,0,0,128,0,0,0,45,45,128,100,128,0,0¶CDF»GST Symbol,53,0,243,221,255,0,243,221,255,0,0,255,128,0,2,,0,75,75,75,255,75,75,75,0,0,255,128,0,75,75,75,255,75,75,0,0,128,255,128¶DOD»GST Symbol,23,150,0,0,0,0,185,185,255,210,0,0,0,0,2,,150,0,0,0,0,90,90,90,210,0,0,0,0,192,192,192,0,90,90,0,100,0,0,0¶LOCAL»GST Symbol,1,0,0,0,255,0,232,190,245,0,0,0,255,0,1,,0,0,0,255,0,105,105,105,0,0,0,255,0,0,0,255,0,105,105,0,0,0,0,255¶UFW»GST Symbol,4,0,0,64,0,0,164,186,238,0,0,64,0,0,1,,0,0,64,0,0,150,150,150,0,0,64,0,0,0,64,0,0,150,150,0,0,0,64,0¶USF»GST Symbol,22,150,0,64,0,0,138,255,193,210,0,64,0,0,2,,150,0,64,0,0,165,165,165,210,0,64,0,0,0,255,0,0,165,165,0,210,0,128,0</SymbolFieldValueList>
    <UseSymbolSizeByScale>n</UseSymbolSizeByScale>
    <SymbolSizeByScale />
    <ShowLineCasing>n</ShowLineCasing>
    <LineCasingColor>255, 78, 78, 78</LineCasingColor>
    <CasingScaleFrom>0</CasingScaleFrom>
    <CasingScaleTo>50000</CasingScaleTo>
 	 </Symbol>
	 
	SRA:  <Symbol>
    <SymbolClassification>Multiple symbol</SymbolClassification>
    <SymbolSize>1</SymbolSize>
    <LineShadeSymbol>0</LineShadeSymbol>
    <MarkerSymbol>X</MarkerSymbol>
    <MarkerSymbolSet>GST Symbol</MarkerSymbolSet>
    <LineSymbolSet>GST Symbol</LineSymbolSet>
    <ShadeSymbolSet>GST Symbol</ShadeSymbolSet>
    <MarkerSymbolIsImage>n</MarkerSymbolIsImage>
    <SymbolMarkerImagePath />
    <SymbolFGColor>255,255,128,64</SymbolFGColor>
    <SymbolBGColor>255,255,128,64</SymbolBGColor>
    <SymbolShadeOutlineColor>255,0,0,0</SymbolShadeOutlineColor>
    <SymbolShadeOutlineSymbol>0</SymbolShadeOutlineSymbol>
    <SymbolShadeImagePath />
    <SymbolFGColorNight>255,0,255,0</SymbolFGColorNight>
    <SymbolBGColorNight>255,0,255,0</SymbolBGColorNight>
    <SymbolShadeOutlineColorNight>255,0,255,0</SymbolShadeOutlineColorNight>
    <SymbolFGColorAerial>255,255,128,64</SymbolFGColorAerial>
    <SymbolBGColorAerial>255,255,128,64</SymbolBGColorAerial>
    <SymbolShadeOutlineColorAerial>255,255,128,64</SymbolShadeOutlineColorAerial>
    <SymbolField>sra</SymbolField>
    <SymbolFieldValueList>FRA»GST Symbol,53,210,89,156,80,210,248,248,207,255,61,94,55,0,2,,255,12,66,81,255,30,30,30,255,6,36,45,50,79,153,43,50,30,30,6,100,52,109,35¶LRA»GST Symbol,53,210,255,255,145,214,255,168,81,210,221,196,19,0,2,,255,8,49,75,255,45,45,45,255,6,36,45,0,45,45,45,255,45,45,6,100,198,198,0¶SRA»GST Symbol,53,210,185,218,154,210,194,254,163,210,97,134,64,0,2,,255,20,101,116,255,60,60,60,0,233,233,233,0,60,60,60,255,60,60,233,100,179,255,102</SymbolFieldValueList>
    <UseSymbolSizeByScale>n</UseSymbolSizeByScale>
    <SymbolSizeByScale />
    <ShowLineCasing>n</ShowLineCasing>
    <LineCasingColor>255, 78, 78, 78</LineCasingColor>
    <CasingScaleFrom>0</CasingScaleFrom>
    <CasingScaleTo>50000</CasingScaleTo>
 	 </Symbol>
	
	STATIONS:   <Symbol>
    <SymbolClassification>Multiple symbol</SymbolClassification>
    <SymbolSize>12</SymbolSize>
    <LineShadeSymbol>0</LineShadeSymbol>
    <MarkerSymbol>X</MarkerSymbol>
    <MarkerSymbolSet>GST Symbol</MarkerSymbolSet>
    <LineSymbolSet>GST Symbol</LineSymbolSet>
    <ShadeSymbolSet>GST Symbol</ShadeSymbolSet>
    <MarkerSymbolIsImage>n</MarkerSymbolIsImage>
    <SymbolMarkerImagePath />
    <SymbolFGColor>255,255,128,64</SymbolFGColor>
    <SymbolBGColor>255,255,128,64</SymbolBGColor>
    <SymbolShadeOutlineColor>255,0,0,0</SymbolShadeOutlineColor>
    <SymbolShadeOutlineSymbol>0</SymbolShadeOutlineSymbol>
    <SymbolShadeImagePath />
    <SymbolFGColorNight>255,0,255,0</SymbolFGColorNight>
    <SymbolBGColorNight>255,0,255,0</SymbolBGColorNight>
    <SymbolShadeOutlineColorNight>255,0,255,0</SymbolShadeOutlineColorNight>
    <SymbolFGColorAerial>255,255,128,64</SymbolFGColorAerial>
    <SymbolBGColorAerial>255,255,128,64</SymbolBGColorAerial>
    <SymbolShadeOutlineColorAerial>255,255,128,64</SymbolShadeOutlineColorAerial>
    <SymbolField>sta_type</SymbolField>
    <SymbolFieldValueList>AAB»GST Symbol,X,12,210,248,248,207,C:\GST\GST Mapper\CurrentMap\Symbol\AirAttack.png,y,255,0,0,0,255,0,0,0¶CALFIRE_OR_COUNTY»GST Symbol,X,12,210,252,226,203,C:\GST\GST Mapper\CurrentMap\Symbol\firestation2.PNG,y,255,0,0,0,255,0,0,0¶CC»GST Symbol,X,12,210,194,254,163,C:\GST\GST Mapper\CurrentMap\Symbol\chainsaw.PNG,y,255,0,0,0,255,0,0,0¶LOCAL»GST Symbol,X,12,210,243,221,255,C:\GST\GST Mapper\CurrentMap\Symbol\FireStationBlue.png,y,255,0,0,0,255,0,0,0¶USFS»GST Symbol,X,12,210,185,185,255,C:\GST\GST Mapper\CurrentMap\Symbol\firestation_USFS.PNG,y,255,0,0,0,255,0,0,0</SymbolFieldValueList>
    <UseSymbolSizeByScale>n</UseSymbolSizeByScale>
    <SymbolSizeByScale />
    <ShowLineCasing>n</ShowLineCasing>
    <LineCasingColor>255, 78, 78, 78</LineCasingColor>
    <CasingScaleFrom>0</CasingScaleFrom>
    <CasingScaleTo>50000</CasingScaleTo>
  	</Symbol>
	
	ROADS:
	- FREEWAY: <Symbol>
    <SymbolClassification>One symbol</SymbolClassification>
    <SymbolSize>3</SymbolSize>
    <LineShadeSymbol>0</LineShadeSymbol>
    <MarkerSymbol>X</MarkerSymbol>
    <MarkerSymbolSet>GST Symbol</MarkerSymbolSet>
    <LineSymbolSet>GST Symbol</LineSymbolSet>
    <ShadeSymbolSet>GST Symbol</ShadeSymbolSet>
    <MarkerSymbolIsImage>n</MarkerSymbolIsImage>
    <SymbolMarkerImagePath />
    <SymbolFGColor>255,255,0,0</SymbolFGColor>
    <SymbolBGColor>255,255,128,64</SymbolBGColor>
    <SymbolShadeOutlineColor>255,0,0,0</SymbolShadeOutlineColor>
    <SymbolShadeOutlineSymbol>0</SymbolShadeOutlineSymbol>
    <SymbolShadeImagePath />
    <SymbolFGColorNight>255,255,0,0</SymbolFGColorNight>
    <SymbolBGColorNight>255,255,128,64</SymbolBGColorNight>
    <SymbolShadeOutlineColorNight>255,255,128,64</SymbolShadeOutlineColorNight>
    <SymbolFGColorAerial>0,255,0,0</SymbolFGColorAerial>
    <SymbolBGColorAerial>255,255,128,64</SymbolBGColorAerial>
    <SymbolShadeOutlineColorAerial>255,255,128,64</SymbolShadeOutlineColorAerial>
    <SymbolField>street</SymbolField>
    <SymbolFieldValueList />
    <UseSymbolSizeByScale>y</UseSymbolSizeByScale>
    <SymbolSizeByScale>0,3000,12@3001,4000,10@4001,5000,10@5001,8000,10@8001,11000,8@11001,16000,6@16001,24000,4@24001,35000,2@35001,200000,2</SymbolSizeByScale>
    <ShowLineCasing>y</ShowLineCasing>
    <LineCasingColor>255, 78, 78, 78</LineCasingColor>
    <CasingScaleFrom>0</CasingScaleFrom>
    <CasingScaleTo>50000</CasingScaleTo>
	  </Symbol>
	  
	- MAJOR: <Symbol>
    <SymbolClassification>One symbol</SymbolClassification>
    <SymbolSize>2</SymbolSize>
    <LineShadeSymbol>0</LineShadeSymbol>
    <MarkerSymbol>X</MarkerSymbol>
    <MarkerSymbolSet>GST Symbol</MarkerSymbolSet>
    <LineSymbolSet>GST Symbol</LineSymbolSet>
    <ShadeSymbolSet>GST Symbol</ShadeSymbolSet>
    <MarkerSymbolIsImage>n</MarkerSymbolIsImage>
    <SymbolMarkerImagePath />
    <SymbolFGColor>255,251,82,0</SymbolFGColor>
    <SymbolBGColor>255,255,128,64</SymbolBGColor>
    <SymbolShadeOutlineColor>255,0,0,0</SymbolShadeOutlineColor>
    <SymbolShadeOutlineSymbol>0</SymbolShadeOutlineSymbol>
    <SymbolShadeImagePath />
    <SymbolFGColorNight>255,255,128,64</SymbolFGColorNight>
    <SymbolBGColorNight>255,255,128,64</SymbolBGColorNight>
    <SymbolShadeOutlineColorNight>255,255,128,64</SymbolShadeOutlineColorNight>
    <SymbolFGColorAerial>0,255,128,64</SymbolFGColorAerial>
    <SymbolBGColorAerial>255,255,128,64</SymbolBGColorAerial>
    <SymbolShadeOutlineColorAerial>255,255,128,64</SymbolShadeOutlineColorAerial>
    <SymbolField>street</SymbolField>
    <SymbolFieldValueList />
    <UseSymbolSizeByScale>y</UseSymbolSizeByScale>
    <SymbolSizeByScale>0,2000,14@2001,4000,10@4001,8000,8@8001,16000,6@16001,35000,4@35001,70000,2@70001,200000,2</SymbolSizeByScale>
    <ShowLineCasing>n</ShowLineCasing>
    <LineCasingColor>255,0,0,0</LineCasingColor>
    <CasingScaleFrom>0</CasingScaleFrom>
    <CasingScaleTo>50000</CasingScaleTo>
 	 </Symbol>
	 
	- LOCAL: 
	
	- RAMP: <Symbol>
    <SymbolClassification>One symbol</SymbolClassification>
    <SymbolSize>2</SymbolSize>
    <LineShadeSymbol>0</LineShadeSymbol>
    <MarkerSymbol>X</MarkerSymbol>
    <MarkerSymbolSet>GST Symbol</MarkerSymbolSet>
    <LineSymbolSet>GST Symbol</LineSymbolSet>
    <ShadeSymbolSet>GST Symbol</ShadeSymbolSet>
    <MarkerSymbolIsImage>n</MarkerSymbolIsImage>
    <SymbolMarkerImagePath />
    <SymbolFGColor>255,255,86,4</SymbolFGColor>
    <SymbolBGColor>255,255,128,64</SymbolBGColor>
    <SymbolShadeOutlineColor>255,0,0,0</SymbolShadeOutlineColor>
    <SymbolShadeOutlineSymbol>0</SymbolShadeOutlineSymbol>
    <SymbolShadeImagePath />
    <SymbolFGColorNight>255,249,81,0</SymbolFGColorNight>
    <SymbolBGColorNight>255,255,128,64</SymbolBGColorNight>
    <SymbolShadeOutlineColorNight>255,255,128,64</SymbolShadeOutlineColorNight>
    <SymbolFGColorAerial>0,255,128,64</SymbolFGColorAerial>
    <SymbolBGColorAerial>255,255,128,64</SymbolBGColorAerial>
    <SymbolShadeOutlineColorAerial>255,255,128,64</SymbolShadeOutlineColorAerial>
    <SymbolField>street</SymbolField>
    <SymbolFieldValueList />
    <UseSymbolSizeByScale>y</UseSymbolSizeByScale>
    <SymbolSizeByScale>0,2000,12@2001,4000,8@4001,8000,6@8001,16000,4@16001,35000,2@35001,70000,2@70001,200000,1</SymbolSizeByScale>
    <ShowLineCasing>y</ShowLineCasing>
    <LineCasingColor>255, 78, 78, 78</LineCasingColor>
    <CasingScaleFrom>0</CasingScaleFrom>
    <CasingScaleTo>50000</CasingScaleTo>
 	 </Symbol>

**Possible changes**

- Use pre-attack extents for hot links vs. pre-attack ICS points


