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

3/20- In-house roads copy, then edit for GST-specific purposes using:

	GST Class	GST Description		FCC			Description
	A91					P00			High speed ramp
	A89		Freeway			P01			Interstate
	A90		Major			P02, P03		State Highway, Arterial (main thouroghfares)
	A40		Local			P04,P05,P06,P10, P11	Collector, light duty, alley, private, trail
	
3/21- Routing issues on Hwy 166, Morro, new communities
	
	
	



