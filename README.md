# sampling_data1


#Mendownload sebuah file excel
wget https://github.com/labusiam/dataset/raw/main/weather_data.xlsx

#konvert setiap sheet pada file weather_data.xlsx
in2csv weather_data.xlsx --sheet "weather_2015" > weather_2015.csv
in2csv weather_data.xlsx --sheet "weather_2014" > weather_2014.csv

#Gabungkan Data weather 2014 dan 2015 menjadi 1 csv
csvstack weather_2015.csv weather_2014.csv > weather.csv

#hapus file weather_data.xlsx
rm weather_data.xlsx

#sampling pada file weather.csv dengan rate 0.3
weather.csv | sample -r 0.3 > sample_weather.csv
