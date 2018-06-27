Cygwin Method:

-Install cygwin as per word doc
-Run command: for year in `seq 2001 2018`;do for month in `seq 1 12`;do wget --content-disposition "http://climate.weather.gc.ca/climate_data/bulk_data_e.html?format=csv&stationID=31688&Year=${year}&Month=${month}&Day=14&timeframe=1&submit= Download+Data" ;done;done
-This will download all data to cygwin/home/<username>
-move all data to data folder in python directory
-run .ipynb
-will spit out concat csv of weather data

Python Method [BEST METHOD]:
-pip install wget
-run code:
for year in year_static:
        print(year)
        for month in range(1,12):
            wget.download("http://climate.weather.gc.ca/climate_data/bulk_data_e.html?format=csv&stationID={0}&Year={1}&Month={2}&Day=14&timeframe=1&submit=Download+Data".format(station_ID,year,month),out='wget_data/Weather')

Cygwin Command line:  

for year in `seq 1998 2008`;do for month in `seq 1 12`;do wget --content-disposition "http://climate.weather.gc.ca/climate_data/bulk_data_e.html?format=csv&stationID=1706&Year=${year}&Month=${month}&Day=14&timeframe=1&submit= Download+Data" ;done;done


WHERE; 
• year = change values in command line (`seq 1998 2008)
• month = change values in command line (`seq 1 12)
• format= [csv|xml]: the format output
• timeframe = 1: for hourly data 
• timeframe = 2: for daily data 
• timeframe = 3 for monthly data 
• Day: the value of the "day" variable is not used and can be an arbitrary value 
• For another station, change the value of the variable stationID
• For the data in XML format, change the value of the variable format to xml in the URL. 
