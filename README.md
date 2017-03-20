# Installation
If you don't have Pip, [get Pip](https://pip.pypa.io/en/latest/installing.html)!

Either clone the repo or [download as a zip](https://github.com/CIC-Geospatial-Data-Discovery-Project/csw-update/archive/master.zip. Once cloned/downloaded and extracted, execute this command:

    pip install -r requirements.txt

# Configuration
1. Make a copy of `config.py.sample`
2. Name it `config.py`
3. Fill in `CSW_URL`, `USER`, and `PASSWORD`
4. (Optional) Set DEBUG to True for more detailed execution information.

# Export from GeoNetwork
Export a CSV for the records you want to edit via spreadsheet. We use a custom CSV export for the CIC: GDDP (mainly for link handling), but as long as you have the `uuid` field, the tool should work with the out of the box CSV export.

# Spreadsheet Input Structural Requirements
- The input file format **must be** `csv`. Excel formats (`xls` or `xlsx`) are not supported.
- There **must be** a column called `uuid`. The values in it should correspond to the fileIdentifier for the records being updated. For example: `bdfc5cd2-732d-4559-a9c7-df38dd683aec`.

# CSV column formatting
When working with a CSV exported from GeoNetwork, you'll need to either:
1. **PREFERRED** Insert a new column, name it according to the table below and add your new values into it. (empty cells will be ignored, so if you want to null out a value, too bad I suppose. Let me know if you really need to do this and I can work in that functionality).
2. Change column names to the appropriate Column Header listed below (this is not really well tested, but ought to work, I guess)

# Updateable Fields
| **Name**                       | **Column Header**        |
|:------------------------------:|:-------------------------|
| **Title**                      | NEW_title                |
| **Abstract**                   | NEW_abstract             |
| **Theme Keywords**             | NEW_keywords_theme       |
| **Place Keywords**             | NEW_keywords_place       |
| **ISO Topic Categories**       | NEW_topic_categories     |
| **Download Link**              | NEW_link_download        |
| **Information Link**           | NEW_link_information     |
| **Esri Web Service Link**      | NEW_link_service_esri    |
| **Web Map Service (WMS) Link** | NEW_link_service_wms     |
| **Metadata Link**              | NEW_link_metadata    |
| **Distribution Format**        | NEW_distribution_format  |
| **Date Published**             | NEW_date_publication     |
| **Date Revised**               | NEW_date_revision        |
| **Temporal Extent Start**      | NEW_temporal_start       |
| **Temporal Extent End**        | NEW_temporal_end         |
| **Bounding Box: north**	     | NEW_north_extent         |
| **Bounding Box: south**        | NEW_south_extent         |
| **Bounding Box: east** 	     | NEW_east_extent          |
| **Bounding Box: west**         | NEW_west_extent          |
| **Reference System Code**      | NEW_ref_system           |
| **Collection**	             | NEW_collective_title     |
| **Geometry Type**              | NEW_other_citation       |
| **Metadata Maintenance Note**  | NEW_maintenance_note     |



#Change Log
March 20, 2017
Added the following element:
*Metadata Link*
Development will continue on update.py.  csw-update.py will be kept as reference version of original script.


Dec 30, 2016

Added the following elements:
*Bounding Box extents
*Reference System
*CollectiveTitle
*Geometry Type (as text string within otherCitation)
*Metadata Maintenance Note
*Originator
*Publisher
*Distributor

Changed format of Temporal Extent to 4 digit year

Changed input format of Topic Categories spellings

