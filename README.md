# GST_042016
Documentation for 2016 update

General Notes

	A. When renaming shapefiles, must manually change file path in CurrentMap .gprj file
		- Add shapefile to CurrentMap folder, then add through GST Layer Control, then in .gprj (path)
		- GST will rename all letters to lowercase by default

	B. In GST, Settings > Settings > Map > Save Map extent on exit

	C. We like the 1:5,000 default map scale, allows for one zoom to display addresses & hydrants

	D. Used Beyond Compare to copy GST folder to other MDC to preserve xml styling

	E. Did not update to 2014 Aerial 

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

4/26- Update shapefiles with new data (address_points_q1_2016, buildings_q1_2016, pipelines_npms_q2_2016, railroads_slu, railroads_state, sirens_q2_2016, treatments_q1_2016, )

Copy/paste gst.xml of old files to new, find and replace shapefile name

5/2- Beta Testing begins



