# trip_data_2


# Answer 1
<br>

```python
# It allows us to read and work on the data line by line which is very beneficial as it loads only one line into the memory at a time. 
import csv, time, datetime
fn = 'trip_data_2.csv'
f = open(fn,'r')              #it is not upload all the data atonce into memory, valueabe and time saving
reader = csv.reader(f)         # it will upload 1 row at a time

line=f.read().splitlines()        #   it splitted the whole csv into rows
lastline=line[-1] # accessed last row
ending_range=lastline.split(",") # splitted the last row to use indexing to get particular columns
firstline=line[1] # accessed first line
starting_range=firstline.split(",") # splitted the first row to use indexing to get particular columns
print("|  COLUMN NUMBER   |    FIELD NAME     | STARTING RANGE     |  ENDING RANGE      |")
print("|-----------------:|:-----------------:|: -----------------:| :----------------: |")
print("|    1             | PICK-UP DATETIME  |{} |{} |".format(starting_range[5],ending_range[5])) # accessed the pickup datetime column
print("|    2             | DROP-OFF DATETIME |{} |{} |".format(starting_range[6],ending_range[6])) # accessed the drop-off datetime column    
   
```
# output    It describe about 


```python
|  COLUMN NUMBER   |    FIELD NAME     | STARTING RANGE     |  ENDING RANGE      |
|-----------------:|:-----------------:|: -----------------:| :----------------: |
|    1             | PICK-UP DATETIME  |2013-02-08 23:35:14 |2013-02-05 22:44:00 |
|    2             | DROP-OFF DATETIME |2013-02-08 23:42:58 |2013-02-05 23:01:00 |
```


# row count
```python
import csv, time
fn = 'trip_data_2.csv'
f = open(fn,'r')
reader = csv.reader(f)
n=0                         # Setting up the  starting value of n = 0
for row in reader:
    if n % 10000 == 0:   #IT WILL SEND REMINDER ON EVERY 10000 ROW
        print(n)
    n+=1                #it will continue adding 1, till the last row
print(n)
```
Total Number of rows = 13990177



# Answer 2
<br>

```python

import csv, time
fn = 'trip_data_2.csv'
f = open(fn,'r')
reader = csv.reader(f)
for row in reader:
    print(row)
    break
    
```
<br>

```python
NUMBER	FIELD NAME
 1|medallion
 2|hack_license
 3|vendor_id
 4|rate_code
 5|store_and_fwd_flag
 6|pickup_datetime
 7|dropoff_datetime
 8|passenger_count
 9|trip_time_in_secs
 10|trip_distance
 11|pickup_longitude
 12|pickup_latitude
 13|dropoff_longitude
 14|dropoff_latitude
```

# DESCRIPTION:
<br>

```python
medallion: A taxi medallion, also known as a CPNC (Certificate of Public Necessity and Convenience), is a transferable permit in the United States allowing a taxicab driver to operate.

hack_license: A permit, license or other authority issued by a governmental agency authorizing a person to drive a taxicab in service to customers in that area.

vendor_id: A code indicating the Taxicab Technology Service Provider(TPEP) that provided the record.

rate_code: It refers to the  code related taximeter rate.

store_and_fwd_flag: This flag indicates whether the trip record was held in vehicle memory before sending to the vendor, aka "store and forward," because the vehicle did not have a connection to the server. Y= store and forward trip, N= not a store and forward trip

pickup_datetime:The date and time when the meter was engaged.

dropoff_datetime: The date and time when the meter was disengaged.

passenger_count: The number of passengers in the vehicle. This is a driver-entered value.

trip_time_in_secs: It refers to the amount of time calculated in seconds by the cab to pickup a passenger and then drop off the passenger. 

trip_distance:  It refers to the distance calculated to pickup a passenger and then drop off the passenger.

pickup_longitude: Longitude where the meter was engaged

pickup_latitude: Latitude where the meter was engaged.

dropoff_longitude: Longitude where the meter was timed off.

dropoff_latitude: Latitude where the meter was timed off.

```




# Answer 3

<br>

```python
import csv, time

fn = 'trip_data_2.csv'
f = open(fn,'r')
reader = csv.reader(f)
n=0
for row in reader:
    print(row)   #it will be taking 1 row at a time
    if n>10:   #to breal the loop after 10
        break   #for exit from loop after 10 th row
    n+=1       # setting the n vale to increase by 1 till  10th row
```

# Output ( first five row details) 

<br>

['medallion', 'hack_license', 'vendor_id', 'rate_code', 'store_and_fwd_flag', 'pickup_datetime', 'dropoff_datetime', 'passenger_count', 'trip_time_in_secs', 'trip_distance', 'pickup_longitude', 'pickup_latitude', 'dropoff_longitude', 'dropoff_latitude']
['1B5C0970F2AE8CFFBA8AE4584BEAED29', 'D961332334524990D1BBD462E2EFB8A4', 'CMT', '1', 'N', '2013-02-08 23:35:14', '2013-02-08 23:42:58', '1', '463', '.80', '-73.992439', '40.724487', '-73.984421', '40.718903']
['B42249AE16E2B8E556F1CB1F940D6FB4', 'D4BB308D1F3FCB3434D9DB282CDC93D7', 'CMT', '1', 'N', '2013-02-07 12:20:16', '2013-02-07 12:50:27', '4', '1810', '3.10', '-73.989494', '40.769588', '-73.990303', '40.737347']
['890699222C47C09FBC898758CEC69762', '6318C3AEC02248928C3345B5805EB905', 'CMT', '1', 'N', '2013-02-08 08:56:54', '2013-02-08 08:59:43', '1', '168', '1.00', '-73.963036', '40.799141', '-73.972168', '40.786446']
['74B7D835C2CD98606D5256DA8A38E045', 'D5E278C918256D1F97680A1F04D290E0', 'CMT', '1', 'N', '2013-02-08 09:37:02', '2013-02-08 09:50:50', '1', '828', '2.10', '-73.987953', '40.728764', '-74.007118', '40.705399']
['4003B8478418FEC5D761E2F37602769B', '0B766F1054A5C16D86BC023858BD8143', 'CMT', '1', 'N', '2013-02-08 19:31:25', '2013-02-08 19:46:23', '1', '897', '3.30', '-73.987282', '40.743042', '-74.010284', '40.703964']
['D72DF7B12201912BFDBB93081EF04C96', 'AFD828EEF790A2485BBB0B568A8BE22E', 'CMT', '1', 'N', '2013-02-08 23:10:01', '2013-02-08 23:46:15', '4', '2173', '7.60', '-73.993004', '40.720154', '-73.959747', '40.80854']






# answer 4
<br>

```python
FIELD NAME- DATATYPE-SIZE-REASON 

medallion - VARCHAR - 40- BECAUSE IT IS A COMBINATION OF BOTH NUMBER AND CHARACTER AND THE SIZE IS  AROUND 40 LETTERS LONG

hack_license - VARCHAR - 45 - REASON SAME AS ABOVE.

vendor_id - VARCHAR - 5 - BECAUSE IT IS CHAR AND THE SIZE IS 3, FOR THE SAFER SIDE 5 HAS BEEN TAKEN 

rate_code - INT -2 - BECAUSE IT IS NUMBER AND THE SIZE IS 1. FOR THE SAFER SIDE 2 HAS BEEN TAKEN

store_and_fwd_flag - VARCHAR - 2 - BECAUSE IT IS CHAR AND THE SIZE IS 1, FOR THE SAFER SIDE 2 HAS BEEN TAKEN

pickup_datetime - DATETIME - DO NEED TO PUT SIZE - BECAUSE IT IS A DATETIME

dropoff_datetime- DATETIME - DO NEED TO PUT SIZE - BECAUSE IT IS A DATETIME

passenger_count - INT - 2 - BECAUSE IT IS ONLY NUMBER AND THE SIZE IS 1, FOR THE SAFER SIDE 2 HAS BEEN TAKEN 

trip_time_in_secs - INT - 8 - BECAUSE IT IS ONLY NUMBER AND THE SIZE IS BETWEEN 4 AND 5,FOR THE SAFER SIDE 8 HAS BEEN TAKEN 

trip_distance - DECIMAL - (6,4)- BECAUSE TOTAL NUMBER IS AROUND 3, 1 BEFORE DECIMAL POINT AND 2 AFTER DECIMAL POINT. FOR THE SAFER SIDE TOTAL NUMBER 6 HAS BEEN TAKEN 2 BEFORE DECIMAL POINT AND 4 AFTER DECIMAL POINT.

pickup_longitude - DECIMAL - (12,8) -BECAUSE TOTAL NUMBER IS AROUND 8, 2 BEFORE DECIMAL POINT AND 6 AFTER DECIMAL POINT. FOR THE SAFER SIDE TOTAL NUMBER 12 HAS BEEN TAKEN 4 BEFORE DECIMAL POINT AND 8 AFTER DECIMAL POINT.

pickup_latitude - DECIMAL - (12,8) -BECAUSE TOTAL NUMBER IS AROUND 8, 2 BEFORE DECIMAL POINT AND 6 AFTER DECIMAL POINT. FOR THE SAFER SIDE TOTAL NUMBER 12 HAS BEEN TAKEN 4 BEFORE DECIMAL POINT AND 8 AFTER DECIMAL POINT.

dropoff_longitude - DECIMAL - (12,8) - BECAUSE TOTAL NUMBER IS AROUND 8, 2 BEFORE DECIMAL POINT AND 6 AFTER DECIMAL POINT. FOR THE SAFER SIDE TOTAL NUMBER 12 HAS BEEN TAKEN 4 BEFORE DECIMAL POINT AND 8 AFTER DECIMAL POINT.

dropoff_latitude - DECIMAL - (12,8) - BECAUSE TOTAL NUMBER IS AROUND 8, 2 BEFORE DECIMAL POINT AND 6 AFTER DECIMAL POINT. FOR THE SAFER SIDE TOTAL NUMBER 12 HAS BEEN TAKEN 4 BEFORE DECIMAL POINT AND 8 AFTER DECIMAL POINT.
```

# Answer 5
<br>

```python
import csv
import matplotlib.pyplot as plt
count=1
i1=0
i2=0
i3=0
i4=0
i5=0
i6=0
i7=0
i8=0
count2=1
count4=1
picklat=[]
picklong=[]
droplat=[]
droplong=[]
with open('trip_data_2.csv') as f:
    reader=csv.reader(f)
    for i,line in enumerate(reader):
        picklat.append(line[11])
        picklong.append(line[10])       # WE HAVE TO MAKE A LIST OF COLUMNS CONTAINING THE LATTITUDES AND THE LONGITUDE
        droplat.append(line[13])
        droplong.append(line[12])
    picklat = [float(i) for i in picklat[1:]]
    picklong = [float(i) for i in picklong[1:]]
    droplat = [float(i) for i in droplat[1:]]        # ITS IMPORTANT TO CONVERT ALL IN ONE FORMAT(IN THIS CASE ITS FLOAT)
    droplong = [float(i) for i in droplong[1:]]
    minpicklat=picklat[0]
    maxpicklat=picklat[0]
    minpicklong=picklong[0]
    maxpicklong=picklong[0]
    mindroplat=droplat[0]
    maxdroplat=droplat[0]
    mindroplong=droplong[0]
    maxdroplong=droplong[0]
    for x in picklat[1:]:
        if(minpicklat > picklat[count]):
            minpicklat=picklat[count]
            i1=count
        if(maxpicklat < picklat[count]):
            maxpicklat=picklat[count]
            i2=count
        count=count+1
    print(i1)
    print(i2)
    for value in picklong[1:]:
        if(minpicklong > picklong[count2]):
            minpicklong=picklong[count2]
            i3=count2                                   # THIS STEP IS VERY IMPORTANT TO FIND THE MIN AND MAX OF ALL 4 LONGITUDE
        if(maxpicklong < picklong[count2]):
            maxpicklong=picklong[count2]
            i4=count2
        count2=count2+1
    print(i3)
    print(i4)
    for x in droplat[1:]:
        if(mindroplat > droplat[count3]):
            mindroplat=droplat[count3]
            i5=count3
        if(maxdroplat < droplat[count3]):
            maxpicklat=picklat[count3]
            i6=count3
        count3=count3+1
    print(i5)
    print(i6)
    for value in droplong[1:]:
        if(mindroplong > droplong[count4]):
            mindroplong=droplong[count4]
            i7=count4
        if(maxdroplong < droplong[count4]):
            maxdroplong=droplong[count4]
            i8=count4
        count4=count4+1
    print(i7)
    print(i8)
f.close()

# THE SAME WILL DE WITH REST OF THE THREE

with open('trip_data_2.csv') as f:
    reader=csv.reader(f)
    line=f.read().splitlines()
    max_pickup_lattitude=line[4752898].split(",")[12]
    max_pickup_longitude=line[4752898].split(",")[13]
    print(max_pickup_lattitude) #max lattitude
    print(max_pickup_longitude)
    min_pickup_lattitude=line[14310378].split(",")[12]
    min_pickup_longitude=line[14310378].split(",")[13]
    print(min_pickup_lattitude) #min lattitude
    print(min_pickup_longitude)
    min_pickup=[min_pickup_lattitude,min_pickup_longitude]
    max_pickup=[max_pickup_lattitude,max_pickup_longitude]
    plt.plot(min_pickup,max_pickup,color='red', marker='o')
    plt.title('GEOGRAPHICAL RANGE OF PICK_UP LATTITUDE', fontsize=12)
    plt.xlabel('MIN', fontsize=14)
    plt.ylabel('MAX', fontsize=14)
    plt.grid(True)
    plt.show()
    max_pickup_longitude=line[2629582].split(",")[12]#main
    max_pickup_longitude=line[2629582].split(",")[13]
    print(max_pickup_lattitude) #max longitude
    print(max_pickup_longitude)
    min_pickup_lattitude=line[12171748].split(",")[12]
    min_pickup_longitude=line[12171748].split(",")[13]
    print(min_pickup_lattitude) #min longitude
    print(min_pickup_longitude)
    min_pickup=[min_pickup_lattitude,min_pickup_longitude]
    max_pickup=[max_pickup_lattitude,max_pickup_longitude]
    plt.plot(min_pickup,max_pickup,color='red', marker='o')
    plt.title('GEOGRAPHICAL RANGE OF PICK_UP LONGITUDE', fontsize=12)
    plt.xlabel('MIN', fontsize=14)
    plt.ylabel('MAX', fontsize=14)
    plt.grid(True)
    plt.show()
    min_dropoff=[40.560763,-73.920471]
    max_dropoff=[41.084076,-74.155197]
    plt.plot(min_dropoff,max_dropoff,color='red', marker='o')
    plt.title('GEOGRAPHICAL RANGE OF DROP_OFF LATTITUDE', fontsize=14)
    plt.xlabel('MIN', fontsize=14)
    plt.ylabel('MAX', fontsize=14)
    plt.grid(True)
    plt.show()
    min_dropoff=[40.908452,-74.405731]
    max_dropoff=[40.649765,-73.460228]
    plt.plot(min_dropoff,max_dropoff,color='red', marker='o')
    plt.title('GEOGRAPHICAL RANGE OF DROP_OFF LONGITUDE', fontsize=14)
    plt.xlabel('MIN', fontsize=14)
    plt.ylabel('MAX', fontsize=14)
    plt.grid(True)
    plt.show()
    

    
```

# Map reprezentation of both latitude and longitude
https://github.com/Rajatgoe/taxi_project/blob/main/Images/georaphical%20range.png
https://github.com/Rajatgoe/taxi_project/blob/main/Images/pickup%20latitude.png
https://github.com/Rajatgoe/taxi_project/blob/main/Images/drop_off_latitudeand%20longitude.png
https://github.com/Rajatgoe/taxi_project/blob/main/Images/drop_off.png



#Min and max of all both latitude and longitude
https://github.com/Rajatgoe/taxi_project/blob/main/Images/Drop_off%20longitude.png
https://github.com/Rajatgoe/taxi_project/blob/main/Images/Drop_off%20latitude.png
https://github.com/Rajatgoe/taxi_project/blob/main/Images/pick_up%20longitude.png
https://github.com/Rajatgoe/taxi_project/blob/main/Images/pick_up%20latitude.png





# Answer 6
<br>

```python
import csv
import matplotlib.pyplot as plt      #you can import matplotlib in windows power shell to see the histogram
fn = 'trip_data_2.csv'
f = open(fn,'r')
reader = csv.reader(f)
x=[]
y=[]
for i, row in enumerate(reader):
    if i==0:continue 
    x.append(round(float(row[9])))     # x is an array where I store the trip distances. Note I rounded up to whole number before storing it in the array.
    y.append(float(row[9]))

plt.hist(x, bins=20)                        # gap between bins  Then I plotted the graph using
plt.show()                                      #plt.hist(x, bins=20)

avg = sum(y)/len(y)                  # I found the average Also, y is a list where I stored the trip distances. Note, that this time I                                              did not round up.                                                                                                                         This is because I needed the actual value to find the trip average.
print('Average', avg)                         #for printing  Average 2.7416122234633344 
f.close()
```

![](images/filename Q6.png)    https://github.com/Rajatgoe/taxi_project/blob/main/Images/Q6.png

Average 2.7416122234633344

# Answer 7
<br>

```python
import csv
with open('trip_data_2.csv') as f:
    reader=csv.reader(f)
    vendor_id=[]
    pickup_datetime=[]
    dropoff_datetime=[]
    passenger_count=[]
    trip_time_in_sec=[]
    trip_distance=[]
    pick_up_lattitude=[]
    pick_up_longitude=[]
    dropoff_lattitude=[]
    dropoff_longitude=[]
    store_and_fwd_flag=[]
    rade_code=[]
    hack_license=[]
    medallion=[]
    for i,line in enumerate(reader):
        medallion.append(line[0])
        hack_license.append(line[1]) # we are appending all the value to get the distinct value of each column
        vendor_id.append(line[2])
        rate_code.apppend(line[3])
        store_and_fwd_flag.apppend(line[4])
        pickup_datetime.apppend(line[5])
        dropoff_datetime.apppend(line[6])
        passenger_count.apppend(line[7])
        trip_time_in_sec.apppend(line[8])
        trip_distance.apppend(line[9])
        pick_up_longitude.apppend(line[10])
        pick_up_lattitude.apppend(line[11])
        dropoff_longitude.apppend(line[12])
        dropoff_lattitude.apppend(line[13])
    unique_word_rate_code=set(rate_code[1:])    #TO GET UNIQUE VALUES, WE HAVE TO USE SET FUNCTION AND FUNCTION
    print(unique_word_rate_code)
    unique_words_medallion = set(medallion[1:])
    print(unique_words_medallion)
    unique_words_hack_license = set(hack_license[1:])
    print(unique_words_hack_license)
    unique_word_vendor_id=set(vendor_id[1:])
    print(unique_word_vendor_id)
    unique_word_store_and_fwd_flag=set(store_and_fwd_flag[1:])
    print(unique_word_store_and_fwd_flag)
    unique_word_ pickup_datetime=set(pickup_datetime[1:])
    print(unique_word_pickup_datetime)
    unique_word_dropoff_datetime=set(dropoff_datetime[1:])
    print(unique_word_dropoff_datetime)
    unique_word_passenger_count=set(passenger_count[1:])
    print(unique_word_passenger_count)
    unique_word_trip_time_in_sec=set(trip_time_in_sec[1:])
    print(unique_word_trip_time_in_sec)
    unique_word_trip_distance=set(trip_distance[1:])
    print(unique_word_trip_distance)
    unique_word_pick_up_longitude=set(pick_up_longitude[1:])
    print(unique_word_pick_up_longitude)
    unique_word_pick_up_lattitude=set(pick_up_lattitude[1:])
    print(unique_word_pick_up_lattitude)
    unique_word_ dropoff_lattitude=set( dropoff_lattitude[1:])
    print(unique_word_dropoff_lattitude)
    unique_word_dropoff_longitude=set(dropoff_longitude[1:])
    print(unique_word_dropoff_longitude)
        
```

# OUTPUT

|FIELD_NAME | UNIQUE_ VALUES |
|-----------|----------------|
|VENDOR_ID  | {'VTS', 'CMT'} |
|RATE_CODE  | {'1', '3', '4', '0', '210', '9', '5', '6', '8', '2', '77'} |
| store_and_fwd_flag|{'N', '', 'Y'}|
| passenger_count |{'1', '4', '3', '0', '5', '6', '8', '208', '2'} |

......I only have taken a part of output because it was too long.




# Answer 8
# we age making a list of column except latitude and longitude

<br>

```python
import csv
count=1
id1=0  
rate_code=[]
passenger_count=[]
trip_distance=[] #float
trip_in_sec=[]
with open('trip_data_6.csv') as f:
    reader=csv.reader(f)
    for i,line in enumerate(reader):
        rate_code.append(line[3])
        passenger_count.append(line[7])
        trip_distance.append(line[9])
        trip_in_sec.append(line[8]                                    ### REST OF THE FIELDS ARE STRING VARIABLE SO FINDING MINIMUM AND                                                        MAXIMUM OF THESE VARIABLES IS NOT POSSIBLE. Except their length can be compared.
                                                      ### Now, we must remember that to perform any operation, it must be converted to                                                               either ***int type*** or ***float type*** depending on the values.
    rate_code =[int(i) for i in rate_code[1:]]
    passenger_count=[int(i) for i in passenger_count[1:]]
    trip_in_sec=[int(i) for i in trip_in_sec[1:]]
    trip_distance=[float(i) for i in trip_distance[1:]]   # it will convert entire list of trip_distance into float type as it should be                                                                   a float type. Rest all contain int values
    minrate=rate_code[0]
    maxrate=rate_code[0]
    minpasct=passenger_count[0] 
    maxpasct=passenger_count[0]
    mintriptime=trip_in_sec[0]
    maxtriptime=trip_in_sec[0] 
    mintripdis=trip_distance[0] 
    maxtripdis=trip_distance[0]                       
    for x in rate_code[1:]:
        if(minrate > rate_code[count]& minrate!=0):
            minrate=rate_code[count]
            id1=count
        if(maxrate < rate_code[count]):
            maxrate=rate_code[count]
            id2=count
        count=count+1
    print(minrate)
    print(maxrate)
    for x in passenger_count[1:]:
       if(minpasct > passenger_count[count1]& minpasct!=0):
            minpasct=passenger_count[count1]
            id1=count1
        if(maxpasct < passenger_count[count1]):
            maxpasct=passenger_count[count1]
            id2=count1
        count1=count1+1
    print(minpasct)
    print(maxpasct)    
    for x in trip_in_sec[1:]:
        if(mintriptime > trip_in_sec[count3]& minrate!=0):
            mintriptime=trip_in_sec[count3]
            id1=count3
        if(maxtriptime < trip_in_sec[count3]):
            maxtriptime=trip_in_sec[count3]
            id2=count3
        count=count+1
    print(mintriptime)       # we will initialise min and max at the first value of each coulumn so that we can check and then later                                    change the  values by going through in a loop. By doing this, we can get minimum and maximum values of all                                fields                                                                                                                                             
   print(maxtriptime)
   for x in trip_distance[1:]:
        if(mintripdis > trip_distance[count4]& minrate!=0):
           mintripdis=trip_distance[count4]
            id1=count4
        if(maxtripdis < trip_distance[count4]):
            maxtripdis=trip_distance[count4]
            id2=count4
        count4=count4+1
    print(mintripdis)
    print(maxtripdis)

```

### OUTPUT (FOR ONLY RATE_CODE)

1
120


# Answer 9

# AFTER APPENDING THE ROWS NEEDED AND CHANGING IT INTO INTEGER FORMAT( TRIP_TIME _IN_SEC, PASSENGER_COUNT),TO CHANGE EVERY TRIP TIME IN SECOND TO HOURS.
<br>

```python
import csv
import matplotlib.pyplot as plt
count=1
count2=1          
sum=0          
value=0
average=[]
hour=[]
sec=3600
dict={}
average_number_of_passenger=[]
passenger_count=[]
trip_in_sec=[]
trip_in_hour=[]
with open('trip_data_2.csv') as f:
    reader=csv.reader(f)
    for i,line in enumerate(reader):
        passenger_count.append(line[3])
        trip_in_sec.append(line[8])
    passenger_count =[int(i) for i in passenger_count[1:]]
    trip_in_sec =[int(i) for i in trip_in_sec[1:]]
    for x in trip_in_sec[1:]:
        value=trip_in_sec[count]/sec
        trip_in_hour.append(value)
        count=count+1
    #print(len(passenger_count))
    hour=[1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24]    
    for x in range(1,len(passenger_count[1:])):    #FINDING AVERAGE NUMBER OF PASSENGER EVERY HOUR BY DIVING NUMBER OF PASSENGER BY                                                                   NUMBER OF HOURS
        try:
            value=passenger_count[count2]/trip_in_hour[count2]
        except:ZeroDivisionError
        sum=sum+value
        count2=count2+1
    print(sum)   
    for i in hour:
        average.append((sum/len(passenger_count[1:]))*i)
    print(average)
    plt.plot(hour,average,color='red', marker='o')
    plt.title('average number of passenger per hour', fontsize=15)   # providing vase to the plot
    plt.xlabel('hour', fontsize=15)
    plt.ylabel('number of passenger', fontsize=15)
    plt.grid(True)
    plt.show()
``` 
# Output
138852867.22586328
[9.925027186998253, 19.850054373996507, 29.77508156099476, 39.70010874799301, 49.62513593499126, 59.55016312198952, 69.47519030898778, 79.40021749598603, 89.32524468298428, 99.25027186998253, 109.17529905698079, 119.10032624397904, 129.0253534309773, 138.95038061797555, 148.8754078049738, 158.80043499197205, 168.7254621789703, 178.65048936596855, 188.5755165529668, 198.50054373996505, 208.42557092696333, 218.35059811396158, 228.27562530095983, 238.20065248795808]

https://github.com/Rajatgoe/taxi_project/blob/main/Images/Q9.png

# Answer 10

#  # Starting Value or row count is 0 
#  if n % 1000 == 0:   It will keep sending the reminder
#    n+=1              #it will keep adding the loop till the end of data

<br>

```python

import csv, time
fn = 'trip_data_2.csv'
f = open(fn,'r')
reader = csv.reader(f)
n=0             
for row in reader:
    if n % 1000 == 0:  
        print(n)
    n+=1             
print(n)
```

# Output

0
1000
2000
3000
4000
5000
6000
7000
8000
9000
10000
11000
12000
13000
14000
15000
16000

It will keep running till 13990000  
    
# Answer 11    

<br>

```python
import csv
import matplotlib.pyplot as plt
passenger_count=[]
count=0
count3=1
count2=1
sum=0
value=0
average=[]
hour=[]
sec=3600
dict={}
average_number_of_passenger=[]
trip_in_sec=[]
trip_in_hour=[]
with open('trip_data_2.csv',) as f:
    reader=csv.reader(f)
    for i,line in enumerate(reader):
        if(count>=1):
            if(count%1000==0):      # breakin the data into 1000
                passenger_count.append(line[3])
                trip_in_sec.append(line[8])
        count=count+1
    #print(len(passenger_count))       
    passenger_count =[int(i) for i in passenger_count[1:]]
    trip_in_sec =[int(i) for i in trip_in_sec[1:]]
    for x in trip_in_sec[1:]:
        value=trip_in_sec[count3]/sec
        trip_in_hour.append(value)
        count3=count3+1
    #print(len(passenger_count))
    hour=[1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24]
    for x in range(1,len(passenger_count[1:])):
        try:
            value=passenger_count[count2]/trip_in_hour[count2]
        except:ZeroDivisionError
        sum=sum+value
        count2=count2+1
    print(sum)   
    for i in hour:
        average.append((sum/len(passenger_count[1:]))*i)
    print(average)
    plt.plot(hour,average,color='red', marker='o')
    plt.title('average number of passenger per hour', fontsize=15)
    plt.xlabel('hour', fontsize=15)
    plt.ylabel('number of passenger', fontsize=15)
    plt.grid(True)
    plt.show()

```
https://github.com/Rajatgoe/taxi_project/blob/main/Images/Q%2011.png

# There is not much difference between two plots , I think its because of average of total and average of thousand
