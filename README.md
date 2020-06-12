# emissions_comparison_readme
## ReadMe file for EPA v. EIA Comparison Methods Document
### Description: This explains how to compare power plant emissions data from EPA Clean Air Markets Data and EIA Data.
-------------------
#### EPA Clean Air Markets CEMS Emissions Data
The EPA Clean Air Markets Emissions Data is a maintained by the EPA’s Clean Air Markets Division. 
Continuous monitoring and reporting of sulfur dioxide (SO2), carbon dioxide (CO2), and nitrogen oxide (NOx) emissions is required for sources regulated under the Part 75 of Volume 40 of the Code of Federal Regulations, also known as the continuous emissions monitoring rule.

EPA Clean Air Markets Data is retrieved from: https://ampd.epa.gov/ampd/

Prepackaged data was downloaded at an hourly emissions by month level from 1995 through 2018.

--------------------

The prepackaged data - column headers and meanings

--------------------

STATE - State in which the facility is located

FACILITY_NAME - The name given by the owners and operators to a facility

ORISPL_CODE - The unique six-digit identification number, also called and ORISPL assigned by the Energy Information Administration

UNITID - Unique identifier for each unit at a facility

OP_DATE - Operating Date

OP_HOUR - Operating Hour

OP_TIME - Operational time whtin the hour

GLOAD (MW) - Rate of electrical generation of a unit or source produced by combusting a given heat input of fuel

SLOAD (1000lb/hr) - Steam Load - Rate of steam pressure generated by a unit or source produced by combusting a given heat input of fuel

SO2_MASS (lbs) - Sulfur dioxide emissions in pounds

SO2_MASS_MEASURE_FLG - Flag indicating whether sulfur dioxide emissions was measured or not

SO2_RATE (lbs/mmBtu) - Sulfur dioxide emissions rate in pounds per million Btu

SO2_RATE_MEASURE_FLG - Flag indicating whether the rate of sulfur dioxide emissions was measured or not

NOX_RATE (lbs/mmBtu) - Nitrogen oxide emissions rate in pounds per million Btu

NOX_RATE_MEASURE_FLG - Flag indicating whether the rate of nitrogen oxide emissions was measured or not

NOX_MASS (lbs) - Nitrogen oxide emissions in pounds

NOX_MASS_MEASURE_FLG - Flag indicating whether the rate of nitrogen oxide emissions was measured or not

CO2_MASS (tons) - Carbon dioxide emissions in tons

CO2_MASS_MEASURE_FLG - Flag indicating whether the rate of carbon dioxide emissions was measured or not

CO2_RATE (tons/mmBtu) - Nitrogen oxide emissions rate in tons per million Btu

CO2_RATE_MEASURE_FLG - Flag indicating whether the rate of carbon dioxide emissions was measured or not

HEAT_INPUT (mmBtu) - The measure of utilization that is calculated by multiplying the quantity of fuel by the fuels heat content

FAC_ID - Facility ID

UNIT_ID - Unique identifier for each unit at a facility

-------------------

Then to get the remaining facility metadata that was not in the prepackaged data, a query was run on the same Clean Air Markets Data website to get the facility information.
Once all of the EPA data was gathered, Stata was used to combine the emissions data with the facilities metadata.

-------------------

#### EIA-923 and -860 data 
Form EIA-923 collects monthly and annual electric power data, including electric electricity generation, fuel consumption, fossil fuel stocks, and receipts at the power plant and prime mover level.

EIA-923 data was retrieved from: https://www.eia.gov/electricity/data/eia923/ for the years 2001 through 2018.

To further supplement generator information, and mainly to find power plant nameplate capacity, form EIA-860 was also used. Form EIA-860 is a report that provides additional data from power plants with a generate nameplate capacity of over 1 MW.

EIA-860 data was downloaded from: https://www.eia.gov/electricity/data/eia860/

The data of interest is in the 3_1_GeneratorYyyyy data file (the exact name of this file changed throughout the years, but it was generally a file with “generator” or “gen” in it.

This data was then combined in Stata with the EIA-923 data

#### Compare EPA and EIA data
As the main goal was to compare EIA and EPA Clean Air Markets Data, the data of particular concern was the “Electricity Net Generation (MWh)”.

In order to compare the EIA data with the EPA Clean Air Markets Data, the data is joined on Plant ID and Plant Name.

The two data sets were then compared to see emissions differences.
