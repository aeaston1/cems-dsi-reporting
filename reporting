
import os
import os.path
import time
#from dateutil.parser import parse
#import datetime
from datetime import date, timedelta
from tempfile import TemporaryFile
from xlwt import Workbook
import numpy as np

i = 0
txtloc = r'/var/log'

Monday = date.today() - timedelta(8)
Tuesday = date.today() - timedelta(7)
Wednesday = date.today() - timedelta(6)
Thursday = date.today() - timedelta(5)
Friday = date.today() - timedelta(4)
Saturday = date.today() - timedelta(3)
Sunday = date.today() - timedelta(2)

Mon = Monday.strftime('%Y%m%d')
Tues = Tuesday.strftime('%Y%m%d')
Wednes =  Wednesday.strftime('%Y%m%d')
Thurs =  Thursday.strftime('%Y%m%d')
Fri =  Friday.strftime('%Y%m%d')
Satur = Saturday.strftime('%Y%m%d')
Sun = Sunday.strftime('%Y%m%d')

#This method gets the date from a given path, and changes it to the same format
# as above
def modify_date(path):
    t = time.ctime(os.path.getmtime(path))
    s = t.replace(' ', '')
    remove = s[16:]+s[3:8]  
    if "Jan" in remove:
        remove = remove.replace("Jan", "01")
    elif "Feb" in remove:
        remove = remove.replace("Feb", "02")
    elif "Mar" in remove:
        remove = remove.replace("Mar", "03")
    elif "Apr" in remove:
        remove = remove.replace("Apr", "04")
    elif "May" in remove:
        remove = remove.replace("May", "05")
    elif "Jun" in remove:
        remove = remove.replace("Jun", "06")
    elif "Jul" in remove:
        remove = remove.replace("Jul", "07")
    elif "Aug" in remove:
        remove = remove.replace("Aug", "08")
    elif "Sep" in remove:
        remove = remove.replace("Sep", "09")
    elif "Oct" in remove:
        remove = remove.replace("Oct", "10")
    elif "Nov" in remove:
        remove = remove.replace("Nov", "11")
    elif "Dec" in remove:
        remove = remove.replace("Dec", "12")
    return remove

def getGlobal(path):
	globalsize, globalcnt = 0,0
        

	for root, dirs, files in os.walk(path): 
		for file in files:
			if ("") in file:	
				tgt=os.path.join(root,file)
			#	m = file.split('_')[5]
			#	mod = m.split('T')[0]


				if os.path.exists(tgt): 
					size = os.stat(tgt).st_size
					globalsize = globalsize + size
					globalcnt+=1		

			
	return globalsize,globalcnt

def getSize(path):
    file_list = []
    totalsize,totalsize1,totalsize2,totalsize3,totalsize4,totalsize5,\
    totalsize6,totalsize7,totalsize8,totalsize9,totalsize10,totalsize11 = \
    0,0,0,0,0,0,0,0,0,0,0,0
    filecnt_add,filecnt_add1,filecnt_add2,filecnt_add3,filecnt_add4,\
    filecnt_add5,filecnt_add6,filecnt_add7,filecnt_add8,filecnt_add9,\
    filecnt_add10,filecnt_add11 = 0,0,0,0,0,0,0,0,0,0,0,0
    filecnt,filecnt1,filecnt2,filecnt3,filecnt4,filecnt5,filecnt6,filecnt7,\
    filecnt8,filecnt9,filecnt10,filecnt11 = 0,0,0,0,0,0,0,0,0,0,0,0
    keywords = np.array(["SIR1ACQ","SIR1LRC10","SIR1LRM_0_","SIR1SAC10_",\
    "SIR1SAR_0_","SIR1SIC10_","SIR1SIN_0_","SIR1TKSA0","SIR1TKSI0",\
    "SIR2SIC10_","SIR2SIN_0_","SIR2STST0"])
    for root,dirs,files in os.walk(path):
        file_array = np.asarray(files)
    
    for i in range(len(keywords)):
        file_list.append(file_array[np.char.find(file_array, keywords[i]) > -1])
        
    for i in range(len(file_list)):
        for j in range(len(file_list[i])):
            filename = file_list[i][j]
            tgt = os.path.join(path, filename)
            filecnt_ = len(file_list[i])
            if i == 0 and (modify_date(tgt) == (Mon) or \
            modify_date(tgt) == (Tues) or modify_date(tgt) == (Wednes) or \
            modify_date(tgt) == (Thurs) or modify_date(tgt) == (Fri) or \
            modify_date(tgt) == (Satur) or modify_date(tgt) == (Sun)):
                filecnt_add += filecnt_
                filecnt = filecnt_add / filecnt_
            if i == 1 and (modify_date(tgt) == (Mon) or \
            modify_date(tgt) == (Tues) or modify_date(tgt) == (Wednes) or \
            modify_date(tgt) == (Thurs) or modify_date(tgt) == (Fri) or \
            modify_date(tgt) == (Satur) or modify_date(tgt) == (Sun)):
                filecnt_add1 += filecnt_
                filecnt1 = filecnt_add1 / filecnt_
            if i == 2 and (modify_date(tgt) == (Mon) or \
            modify_date(tgt) == (Tues) or modify_date(tgt) == (Wednes) or \
            modify_date(tgt) == (Thurs) or modify_date(tgt) == (Fri) or \
            modify_date(tgt) == (Satur) or modify_date(tgt) == (Sun)):
                filecnt_add2 += filecnt_
                filecnt2 = filecnt_add2 / filecnt_
            if i == 3 and (modify_date(tgt) == (Mon) or \
            modify_date(tgt) == (Tues) or modify_date(tgt) == (Wednes) or \
            modify_date(tgt) == (Thurs) or modify_date(tgt) == (Fri) or \
            modify_date(tgt) == (Satur) or modify_date(tgt) == (Sun)):
                filecnt_add3 += filecnt_
                filecnt3 = filecnt_add3 / filecnt_
            if i == 4 and (modify_date(tgt) == (Mon) or \
            modify_date(tgt) == (Tues) or modify_date(tgt) == (Wednes) or \
            modify_date(tgt) == (Thurs) or modify_date(tgt) == (Fri) or \
            modify_date(tgt) == (Satur) or modify_date(tgt) == (Sun)):
                filecnt_add4 += filecnt_
                filecnt4 = filecnt_add4 / filecnt_
            if i == 5 and (modify_date(tgt) == (Mon) or \
            modify_date(tgt) == (Tues) or modify_date(tgt) == (Wednes) or \
            modify_date(tgt) == (Thurs) or modify_date(tgt) == (Fri) or \
            modify_date(tgt) == (Satur) or modify_date(tgt) == (Sun)):
                filecnt_add5 += filecnt_
                filecnt5 = filecnt_add5 / filecnt_
            if i == 6 and (modify_date(tgt) == (Mon) or \
            modify_date(tgt) == (Tues) or modify_date(tgt) == (Wednes) or \
            modify_date(tgt) == (Thurs) or modify_date(tgt) == (Fri) or \
            modify_date(tgt) == (Satur) or modify_date(tgt) == (Sun)):
                filecnt_add6 += filecnt_
                filecnt6 = filecnt_add6 / filecnt_
            if i == 7 and (modify_date(tgt) == (Mon) or \
            modify_date(tgt) == (Tues) or modify_date(tgt) == (Wednes) or \
            modify_date(tgt) == (Thurs) or modify_date(tgt) == (Fri) or \
            modify_date(tgt) == (Satur) or modify_date(tgt) == (Sun)):
                filecnt_add7 += filecnt_
                filecnt7 = filecnt_add7 / filecnt_
            if i == 8 and (modify_date(tgt) == (Mon) or \
            modify_date(tgt) == (Tues) or modify_date(tgt) == (Wednes) or \
            modify_date(tgt) == (Thurs) or modify_date(tgt) == (Fri) or \
            modify_date(tgt) == (Satur) or modify_date(tgt) == (Sun)):
                filecnt_add8 += filecnt_
                filecnt8 = filecnt_add8 / filecnt_
            if i == 9 and (modify_date(tgt) == (Mon) or \
            modify_date(tgt) == (Tues) or modify_date(tgt) == (Wednes) or \
            modify_date(tgt) == (Thurs) or modify_date(tgt) == (Fri) or \
            modify_date(tgt) == (Satur) or modify_date(tgt) == (Sun)):
                filecnt_add9 += filecnt_
                filecnt9 = filecnt_add9 / filecnt_
            if i == 10 and (modify_date(tgt) == (Mon) or \
            modify_date(tgt) == (Tues) or modify_date(tgt) == (Wednes) or \
            modify_date(tgt) == (Thurs) or modify_date(tgt) == (Fri) or \
            modify_date(tgt) == (Satur) or modify_date(tgt) == (Sun)):
                filecnt_add10 += filecnt_
                filecnt10 = filecnt_add10 / filecnt_
            if i == 11 and (modify_date(tgt) == (Mon) or \
            modify_date(tgt) == (Tues) or modify_date(tgt) == (Wednes) or \
            modify_date(tgt) == (Thurs) or modify_date(tgt) == (Fri) or \
            modify_date(tgt) == (Satur) or modify_date(tgt) == (Sun)):
                filecnt_add11 += filecnt_
                filecnt11 = filecnt_add11 / filecnt_
     
   
    for i in range(len(file_list)):
        for j in range(len(file_list[i])):
            filename = file_list[i][j]
            tgt = os.path.join(path, filename)
            size = os.stat(tgt).st_size
            if i == 0 and (modify_date(tgt) == (Mon) or \
            modify_date(tgt) == (Tues) or modify_date(tgt) == (Wednes) or \
            modify_date(tgt) == (Thurs) or modify_date(tgt) == (Fri) or \
            modify_date(tgt) == (Satur) or modify_date(tgt) == (Sun)):
                totalsize += size
            if i == 1 and (modify_date(tgt) == (Mon) or \
            modify_date(tgt) == (Tues) or modify_date(tgt) == (Wednes) or \
            modify_date(tgt) == (Thurs) or modify_date(tgt) == (Fri) or \
            modify_date(tgt) == (Satur) or modify_date(tgt) == (Sun)):
               totalsize1 += size
            if i == 2 and (modify_date(tgt) == (Mon) or \
            modify_date(tgt) == (Tues) or modify_date(tgt) == (Wednes) or \
            modify_date(tgt) == (Thurs) or modify_date(tgt) == (Fri) or \
            modify_date(tgt) == (Satur) or modify_date(tgt) == (Sun)):
                totalsize2 += size
            if i == 3 and (modify_date(tgt) == (Mon) or \
            modify_date(tgt) == (Tues) or modify_date(tgt) == (Wednes) or \
            modify_date(tgt) == (Thurs) or modify_date(tgt) == (Fri) or \
            modify_date(tgt) == (Satur) or modify_date(tgt) == (Sun)):
                totalsize3 += size
            if i == 4 and (modify_date(tgt) == (Mon) or \
            modify_date(tgt) == (Tues) or modify_date(tgt) == (Wednes) or \
            modify_date(tgt) == (Thurs) or modify_date(tgt) == (Fri) or \
            modify_date(tgt) == (Satur) or modify_date(tgt) == (Sun)):
                totalsize4 += size
            if i == 5 and (modify_date(tgt) == (Mon) or \
            modify_date(tgt) == (Tues) or modify_date(tgt) == (Wednes) or \
            modify_date(tgt) == (Thurs) or modify_date(tgt) == (Fri) or \
            modify_date(tgt) == (Satur) or modify_date(tgt) == (Sun)):
                totalsize5 += size
            if i == 6 and (modify_date(tgt) == (Mon) or \
            modify_date(tgt) == (Tues) or modify_date(tgt) == (Wednes) or \
            modify_date(tgt) == (Thurs) or modify_date(tgt) == (Fri) or \
            modify_date(tgt) == (Satur) or modify_date(tgt) == (Sun)):
                totalsize6 += size
            if i == 7 and (modify_date(tgt) == (Mon) or \
            modify_date(tgt) == (Tues) or modify_date(tgt) == (Wednes) or \
            modify_date(tgt) == (Thurs) or modify_date(tgt) == (Fri) or \
            modify_date(tgt) == (Satur) or modify_date(tgt) == (Sun)):
               totalsize7 += size
            if i == 8 and (modify_date(tgt) == (Mon) or \
            modify_date(tgt) == (Tues) or modify_date(tgt) == (Wednes) or \
            modify_date(tgt) == (Thurs) or modify_date(tgt) == (Fri) or \
            modify_date(tgt) == (Satur) or modify_date(tgt) == (Sun)):
                totalsize8 += size
            if i == 9 and (modify_date(tgt) == (Mon) or \
            modify_date(tgt) == (Tues) or modify_date(tgt) == (Wednes) or \
            modify_date(tgt) == (Thurs) or modify_date(tgt) == (Fri) or \
            modify_date(tgt) == (Satur) or modify_date(tgt) == (Sun)):
                totalsize9 += size
            if i == 10 and (modify_date(tgt) == (Mon) or \
            modify_date(tgt) == (Tues) or modify_date(tgt) == (Wednes) or \
            modify_date(tgt) == (Thurs) or modify_date(tgt) == (Fri) or \
            modify_date(tgt) == (Satur) or modify_date(tgt) == (Sun)):
                totalsize10 += size
            if i == 11 and (modify_date(tgt) == (Mon) or \
            modify_date(tgt) == (Tues) or modify_date(tgt) == (Wednes) or \
            modify_date(tgt) == (Thurs) or modify_date(tgt) == (Fri) or \
            modify_date(tgt) == (Satur) or modify_date(tgt) == (Sun)):
                totalsize11 += size
       
    return totalsize,filecnt,totalsize1,filecnt1,totalsize2,filecnt2,\
    totalsize3,filecnt3,totalsize4,filecnt4,totalsize5,filecnt5,totalsize6,\
    filecnt6,totalsize7,filecnt7,totalsize8,filecnt8,totalsize9,filecnt9,\
    totalsize10,filecnt10,totalsize11,filecnt11

def getSizeorb(path):
    file_list = []
    totalsize,totalsize1,totalsize2,totalsize3 = 0,0,0,0
    filecnt_add,filecnt_add1,filecnt_add2,filecnt_add3 = 0,0,0,0
    filecnt,filecnt1,filecnt2,filecnt3 = 0,0,0,0    
    keywords = np.array(["ORBDOR","DOR_NAV","ORBDOP","MPL_ORBPRE"])
    for root,dirs,files in os.walk(path):
        file_array = np.asarray(files)
    
    for i in range(len(keywords)):
        file_list.append(file_array[np.char.find(file_array, keywords[i]) > -1])
        
    for i in range(len(file_list)):
        for j in range(len(file_list[i])):
            filename = file_list[i][j]
            tgt = os.path.join(path, filename)
            filecnt_ = len(file_list[i])
            if i == 0 and (modify_date(tgt) == (Mon) or \
            modify_date(tgt) == (Tues) or modify_date(tgt) == (Wednes) or \
            modify_date(tgt) == (Thurs) or modify_date(tgt) == (Fri) or \
            modify_date(tgt) == (Satur) or modify_date(tgt) == (Sun)):
                filecnt_add += filecnt_
                filecnt = filecnt_add / filecnt_
            if i == 1 and (modify_date(tgt) == (Mon) or \
            modify_date(tgt) == (Tues) or modify_date(tgt) == (Wednes) or \
            modify_date(tgt) == (Thurs) or modify_date(tgt) == (Fri) or \
            modify_date(tgt) == (Satur) or modify_date(tgt) == (Sun)):
                filecnt_add1 += filecnt_
                filecnt1 = filecnt_add1 / filecnt_
            if i == 2 and (modify_date(tgt) == (Mon) or \
            modify_date(tgt) == (Tues) or modify_date(tgt) == (Wednes) or \
            modify_date(tgt) == (Thurs) or modify_date(tgt) == (Fri) or \
            modify_date(tgt) == (Satur) or modify_date(tgt) == (Sun)):
                filecnt_add2 += filecnt_
                filecnt2 = filecnt_add2 / filecnt_
            if i == 3 and (modify_date(tgt) == (Mon) or \
            modify_date(tgt) == (Tues) or modify_date(tgt) == (Wednes) or \
            modify_date(tgt) == (Thurs) or modify_date(tgt) == (Fri) or \
            modify_date(tgt) == (Satur) or modify_date(tgt) == (Sun)):
                filecnt_add3 += filecnt_
                filecnt3 = filecnt_add3 / filecnt_
            
   
    for i in range(len(file_list)):
        for j in range(len(file_list[i])):
            filename = file_list[i][j]
            tgt = os.path.join(path, filename)
            size = os.stat(tgt).st_size
            if i == 0 and (modify_date(tgt) == (Mon) or \
            modify_date(tgt) == (Tues) or modify_date(tgt) == (Wednes) or \
            modify_date(tgt) == (Thurs) or modify_date(tgt) == (Fri) or \
            modify_date(tgt) == (Satur) or modify_date(tgt) == (Sun)):
                totalsize += size
            if i == 1 and (modify_date(tgt) == (Mon) or \
            modify_date(tgt) == (Tues) or modify_date(tgt) == (Wednes) or \
            modify_date(tgt) == (Thurs) or modify_date(tgt) == (Fri) or \
            modify_date(tgt) == (Satur) or modify_date(tgt) == (Sun)):
               totalsize1 += size
            if i == 2 and (modify_date(tgt) == (Mon) or \
            modify_date(tgt) == (Tues) or modify_date(tgt) == (Wednes) or \
            modify_date(tgt) == (Thurs) or modify_date(tgt) == (Fri) or \
            modify_date(tgt) == (Satur) or modify_date(tgt) == (Sun)):
                totalsize2 += size
            if i == 3 and (modify_date(tgt) == (Mon) or \
            modify_date(tgt) == (Tues) or modify_date(tgt) == (Wednes) or \
            modify_date(tgt) == (Thurs) or modify_date(tgt) == (Fri) or \
            modify_date(tgt) == (Satur) or modify_date(tgt) == (Sun)):
                totalsize3 += size
            
  
    return totalsize,filecnt,totalsize1,filecnt1,totalsize2,filecnt2,\
    totalsize3,filecnt3  


def getSizeaux(path):
    file_list = []
    totalsize,totalsize1,totalsize2,totalsize3,totalsize4,totalsize5,\
    totalsize6,totalsize7,totalsize8,totalsize9,totalsize10,totalsize11,\
    totalsize12,totalsize13,totalsize14,totalsize15,totalsize16 = \
    0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0
    filecnt_add,filecnt_add1,filecnt_add2,filecnt_add3,filecnt_add4,\
    filecnt_add5,filecnt_add6,filecnt_add7,filecnt_add8,filecnt_add9,\
    filecnt_add10,filecnt_add11,filecnt_add12,filecnt_add13,filecnt_add14,\
    filecnt_add15,filecnt_add16 = \
    0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0
    filecnt,filecnt1,filecnt2,filecnt3,filecnt4,filecnt5,filecnt6,filecnt7,\
    filecnt8,filecnt9,filecnt10,filecnt11,filecnt12,filecnt13,filecnt14,\
    filecnt15,filecnt16 = \
    0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0
    keywords = np.array(["AUX_DORUSO","AUX_IONGIM","AUXIMOG_2D","AUX_MOG_2D",\
    "AUXISEAMPS","AUX_SEA_IC","AUX_SURFPS","AUXIU_WIND","AUXIV_WIND",\
    "AUX_WETTRP","AUX_SEAMPS","AUXISURFPS","AUX_U_WIND","AUX_V_WIND",\
    "AUXIWETTRP","AUX_POLLOC","AUXIIONGIM"])
    for root,dirs,files in os.walk(path):
        file_array = np.asarray(files)
    
    for i in range(len(keywords)):
        file_list.append(file_array[np.char.find(file_array, keywords[i]) > -1])
        
    for i in range(len(file_list)):
        for j in range(len(file_list[i])):
            filename = file_list[i][j]
            tgt = os.path.join(path, filename)
            filecnt_ = len(file_list[i])
            if i == 0 and (modify_date(tgt) == (Mon) or \
            modify_date(tgt) == (Tues) or modify_date(tgt) == (Wednes) or \
            modify_date(tgt) == (Thurs) or modify_date(tgt) == (Fri) or \
            modify_date(tgt) == (Satur) or modify_date(tgt) == (Sun)):
                filecnt_add += filecnt_
                filecnt = filecnt_add / filecnt_
            if i == 1 and (modify_date(tgt) == (Mon) or \
            modify_date(tgt) == (Tues) or modify_date(tgt) == (Wednes) or \
            modify_date(tgt) == (Thurs) or modify_date(tgt) == (Fri) or \
            modify_date(tgt) == (Satur) or modify_date(tgt) == (Sun)):
                filecnt_add1 += filecnt_
                filecnt1 = filecnt_add1 / filecnt_
            if i == 2 and (modify_date(tgt) == (Mon) or \
            modify_date(tgt) == (Tues) or modify_date(tgt) == (Wednes) or \
            modify_date(tgt) == (Thurs) or modify_date(tgt) == (Fri) or \
            modify_date(tgt) == (Satur) or modify_date(tgt) == (Sun)):
                filecnt_add2 += filecnt_
                filecnt2 = filecnt_add2 / filecnt_
            if i == 3 and (modify_date(tgt) == (Mon) or \
            modify_date(tgt) == (Tues) or modify_date(tgt) == (Wednes) or \
            modify_date(tgt) == (Thurs) or modify_date(tgt) == (Fri) or \
            modify_date(tgt) == (Satur) or modify_date(tgt) == (Sun)):
                filecnt_add3 += filecnt_
                filecnt3 = filecnt_add3 / filecnt_
            if i == 4 and (modify_date(tgt) == (Mon) or \
            modify_date(tgt) == (Tues) or modify_date(tgt) == (Wednes) or \
            modify_date(tgt) == (Thurs) or modify_date(tgt) == (Fri) or \
            modify_date(tgt) == (Satur) or modify_date(tgt) == (Sun)):
                filecnt_add4 += filecnt_
                filecnt4 = filecnt_add4 / filecnt_
            if i == 5 and (modify_date(tgt) == (Mon) or \
            modify_date(tgt) == (Tues) or modify_date(tgt) == (Wednes) or \
            modify_date(tgt) == (Thurs) or modify_date(tgt) == (Fri) or \
            modify_date(tgt) == (Satur) or modify_date(tgt) == (Sun)):
                filecnt_add5 += filecnt_
                filecnt5 = filecnt_add5 / filecnt_
            if i == 6 and (modify_date(tgt) == (Mon) or \
            modify_date(tgt) == (Tues) or modify_date(tgt) == (Wednes) or \
            modify_date(tgt) == (Thurs) or modify_date(tgt) == (Fri) or \
            modify_date(tgt) == (Satur) or modify_date(tgt) == (Sun)):
                filecnt_add6 += filecnt_
                filecnt6 = filecnt_add6 / filecnt_
            if i == 7 and (modify_date(tgt) == (Mon) or \
            modify_date(tgt) == (Tues) or modify_date(tgt) == (Wednes) or \
            modify_date(tgt) == (Thurs) or modify_date(tgt) == (Fri) or \
            modify_date(tgt) == (Satur) or modify_date(tgt) == (Sun)):
                filecnt_add7 += filecnt_
                filecnt7 = filecnt_add7 / filecnt_
            if i == 8 and (modify_date(tgt) == (Mon) or \
            modify_date(tgt) == (Tues) or modify_date(tgt) == (Wednes) or \
            modify_date(tgt) == (Thurs) or modify_date(tgt) == (Fri) or \
            modify_date(tgt) == (Satur) or modify_date(tgt) == (Sun)):
                filecnt_add8 += filecnt_
                filecnt8 = filecnt_add8 / filecnt_
            if i == 9 and (modify_date(tgt) == (Mon) or \
            modify_date(tgt) == (Tues) or modify_date(tgt) == (Wednes) or \
            modify_date(tgt) == (Thurs) or modify_date(tgt) == (Fri) or \
            modify_date(tgt) == (Satur) or modify_date(tgt) == (Sun)):
                filecnt_add9 += filecnt_
                filecnt9 = filecnt_add9 / filecnt_
            if i == 10 and (modify_date(tgt) == (Mon) or \
            modify_date(tgt) == (Tues) or modify_date(tgt) == (Wednes) or \
            modify_date(tgt) == (Thurs) or modify_date(tgt) == (Fri) or \
            modify_date(tgt) == (Satur) or modify_date(tgt) == (Sun)):
                filecnt_add10 += filecnt_
                filecnt10 = filecnt_add10 / filecnt_
            if i == 11 and (modify_date(tgt) == (Mon) or \
            modify_date(tgt) == (Tues) or modify_date(tgt) == (Wednes) or \
            modify_date(tgt) == (Thurs) or modify_date(tgt) == (Fri) or \
            modify_date(tgt) == (Satur) or modify_date(tgt) == (Sun)):
                filecnt_add11 += filecnt_
                filecnt11 = filecnt_add11 / filecnt_
            if i == 12 and (modify_date(tgt) == (Mon) or \
            modify_date(tgt) == (Tues) or modify_date(tgt) == (Wednes) or \
            modify_date(tgt) == (Thurs) or modify_date(tgt) == (Fri) or \
            modify_date(tgt) == (Satur) or modify_date(tgt) == (Sun)):
                filecnt_add12 += filecnt_
                filecnt12 = filecnt_add12 / filecnt_
            if i == 13 and (modify_date(tgt) == (Mon) or \
            modify_date(tgt) == (Tues) or modify_date(tgt) == (Wednes) or \
            modify_date(tgt) == (Thurs) or modify_date(tgt) == (Fri) or \
            modify_date(tgt) == (Satur) or modify_date(tgt) == (Sun)):
                filecnt_add13 += filecnt_
                filecnt13 = filecnt_add13 / filecnt_
            if i == 14 and (modify_date(tgt) == (Mon) or \
            modify_date(tgt) == (Tues) or modify_date(tgt) == (Wednes) or \
            modify_date(tgt) == (Thurs) or modify_date(tgt) == (Fri) or \
            modify_date(tgt) == (Satur) or modify_date(tgt) == (Sun)):
                filecnt_add9 += filecnt_
                filecnt14 = filecnt_add14 / filecnt_
            if i == 15 and (modify_date(tgt) == (Mon) or \
            modify_date(tgt) == (Tues) or modify_date(tgt) == (Wednes) or \
            modify_date(tgt) == (Thurs) or modify_date(tgt) == (Fri) or \
            modify_date(tgt) == (Satur) or modify_date(tgt) == (Sun)):
                filecnt_add15 += filecnt_
                filecnt15 = filecnt_add15 / filecnt_
            if i == 16 and (modify_date(tgt) == (Mon) or \
            modify_date(tgt) == (Tues) or modify_date(tgt) == (Wednes) or \
            modify_date(tgt) == (Thurs) or modify_date(tgt) == (Fri) or \
            modify_date(tgt) == (Satur) or modify_date(tgt) == (Sun)):
                filecnt_add16 += filecnt_
                filecnt16 = filecnt_add16 / filecnt_
            
   
    for i in range(len(file_list)):
        for j in range(len(file_list[i])):
            filename = file_list[i][j]
            tgt = os.path.join(path, filename)
            size = os.stat(tgt).st_size
            if i == 0 and (modify_date(tgt) == (Mon) or \
            modify_date(tgt) == (Tues) or modify_date(tgt) == (Wednes) or \
            modify_date(tgt) == (Thurs) or modify_date(tgt) == (Fri) or \
            modify_date(tgt) == (Satur) or modify_date(tgt) == (Sun)):
                totalsize += size
            if i == 1 and (modify_date(tgt) == (Mon) or \
            modify_date(tgt) == (Tues) or modify_date(tgt) == (Wednes) or \
            modify_date(tgt) == (Thurs) or modify_date(tgt) == (Fri) or \
            modify_date(tgt) == (Satur) or modify_date(tgt) == (Sun)):
               totalsize1 += size
            if i == 2 and (modify_date(tgt) == (Mon) or \
            modify_date(tgt) == (Tues) or modify_date(tgt) == (Wednes) or \
            modify_date(tgt) == (Thurs) or modify_date(tgt) == (Fri) or \
            modify_date(tgt) == (Satur) or modify_date(tgt) == (Sun)):
                totalsize2 += size
            if i == 3 and (modify_date(tgt) == (Mon) or \
            modify_date(tgt) == (Tues) or modify_date(tgt) == (Wednes) or \
            modify_date(tgt) == (Thurs) or modify_date(tgt) == (Fri) or \
            modify_date(tgt) == (Satur) or modify_date(tgt) == (Sun)):
                totalsize3 += size
            if i == 4 and (modify_date(tgt) == (Mon) or \
            modify_date(tgt) == (Tues) or modify_date(tgt) == (Wednes) or \
            modify_date(tgt) == (Thurs) or modify_date(tgt) == (Fri) or \
            modify_date(tgt) == (Satur) or modify_date(tgt) == (Sun)):
                totalsize4 += size
            if i == 5 and (modify_date(tgt) == (Mon) or \
            modify_date(tgt) == (Tues) or modify_date(tgt) == (Wednes) or \
            modify_date(tgt) == (Thurs) or modify_date(tgt) == (Fri) or \
            modify_date(tgt) == (Satur) or modify_date(tgt) == (Sun)):
                totalsize5 += size
            if i == 6 and (modify_date(tgt) == (Mon) or \
            modify_date(tgt) == (Tues) or modify_date(tgt) == (Wednes) or \
            modify_date(tgt) == (Thurs) or modify_date(tgt) == (Fri) or \
            modify_date(tgt) == (Satur) or modify_date(tgt) == (Sun)):
                totalsize6 += size
            if i == 7 and (modify_date(tgt) == (Mon) or \
            modify_date(tgt) == (Tues) or modify_date(tgt) == (Wednes) or \
            modify_date(tgt) == (Thurs) or modify_date(tgt) == (Fri) or \
            modify_date(tgt) == (Satur) or modify_date(tgt) == (Sun)):
               totalsize7 += size
            if i == 8 and (modify_date(tgt) == (Mon) or \
            modify_date(tgt) == (Tues) or modify_date(tgt) == (Wednes) or \
            modify_date(tgt) == (Thurs) or modify_date(tgt) == (Fri) or \
            modify_date(tgt) == (Satur) or modify_date(tgt) == (Sun)):
                totalsize8 += size
            if i == 9 and (modify_date(tgt) == (Mon) or \
            modify_date(tgt) == (Tues) or modify_date(tgt) == (Wednes) or \
            modify_date(tgt) == (Thurs) or modify_date(tgt) == (Fri) or \
            modify_date(tgt) == (Satur) or modify_date(tgt) == (Sun)):
                totalsize9 += size
            if i == 10 and (modify_date(tgt) == (Mon) or \
            modify_date(tgt) == (Tues) or modify_date(tgt) == (Wednes) or \
            modify_date(tgt) == (Thurs) or modify_date(tgt) == (Fri) or \
            modify_date(tgt) == (Satur) or modify_date(tgt) == (Sun)):
                totalsize10 += size
            if i == 11 and (modify_date(tgt) == (Mon) or \
            modify_date(tgt) == (Tues) or modify_date(tgt) == (Wednes) or \
            modify_date(tgt) == (Thurs) or modify_date(tgt) == (Fri) or \
            modify_date(tgt) == (Satur) or modify_date(tgt) == (Sun)):
                totalsize11 += size
            if i == 12 and (modify_date(tgt) == (Mon) or \
            modify_date(tgt) == (Tues) or modify_date(tgt) == (Wednes) or \
            modify_date(tgt) == (Thurs) or modify_date(tgt) == (Fri) or \
            modify_date(tgt) == (Satur) or modify_date(tgt) == (Sun)):
               totalsize12 += size
            if i == 13 and (modify_date(tgt) == (Mon) or \
            modify_date(tgt) == (Tues) or modify_date(tgt) == (Wednes) or \
            modify_date(tgt) == (Thurs) or modify_date(tgt) == (Fri) or \
            modify_date(tgt) == (Satur) or modify_date(tgt) == (Sun)):
                totalsize13 += size
            if i == 14 and (modify_date(tgt) == (Mon) or \
            modify_date(tgt) == (Tues) or modify_date(tgt) == (Wednes) or \
            modify_date(tgt) == (Thurs) or modify_date(tgt) == (Fri) or \
            modify_date(tgt) == (Satur) or modify_date(tgt) == (Sun)):
                totalsize14 += size
            if i == 15 and (modify_date(tgt) == (Mon) or \
            modify_date(tgt) == (Tues) or modify_date(tgt) == (Wednes) or \
            modify_date(tgt) == (Thurs) or modify_date(tgt) == (Fri) or \
            modify_date(tgt) == (Satur) or modify_date(tgt) == (Sun)):
                totalsize15 += size
            if i == 16 and (modify_date(tgt) == (Mon) or \
            modify_date(tgt) == (Tues) or modify_date(tgt) == (Wednes) or \
            modify_date(tgt) == (Thurs) or modify_date(tgt) == (Fri) or \
            modify_date(tgt) == (Satur) or modify_date(tgt) == (Sun)):
                totalsize16 += size
            
       
    return totalsize,filecnt,totalsize1,filecnt1,totalsize2,filecnt2,\
	totalsize3,filecnt3,totalsize4,filecnt4,totalsize5,filecnt5,totalsize6,\
	filecnt6,totalsize7,filecnt7,totalsize8,filecnt8,totalsize9,filecnt9,\
	totalsize10,filecnt10,totalsize11,filecnt11,totalsize12,filecnt12,\
	totalsize13,filecnt13,totalsize14,filecnt14,totalsize15,filecnt15,\
	totalsize16,filecnt16   


def weekL0(path):
    file_list = []
    totalsize,totalsize1,totalsize2,totalsize3,totalsize4,totalsize5,totalsize6\
    = 0,0,0,0,0,0,0
    filecnt_add,filecnt_add1,filecnt_add2,filecnt_add3,filecnt_add4,\
    filecnt_add5,filecnt_add6 = 0,0,0,0,0,0,0
    filecnt,filecnt1,filecnt2,filecnt3,filecnt4,filecnt5,filecnt6 = \
    0,0,0,0,0,0,0   
    keywords = np.array(["CS_OPER","CS_OPER","CS_OPER","CS_OPER","CS_OPER",\
    "CS_OPER","CS_OPER"])
    for root,dirs,files in os.walk(path):
        file_array = np.asarray(files)
    
    for i in range(len(keywords)):
        file_list.append(file_array[np.char.find(file_array, keywords[i]) > -1])
        
    for i in range(len(file_list)):
        for j in range(len(file_list[i])):
            filename = file_list[i][j]
            tgt = os.path.join(path, filename)
            filecnt_ = len(file_list[i])
            if i == 0 and (modify_date(tgt) == (Mon)):
                filecnt_add += filecnt_
                filecnt = filecnt_add / filecnt_
            if i == 1 and (modify_date(tgt) == (Tues)):
                filecnt_add1 += filecnt_
                filecnt1 = filecnt_add1 / filecnt_
            if i == 2 and (modify_date(tgt) == (Wednes)):
                filecnt_add2 += filecnt_
                filecnt2 = filecnt_add2 / filecnt_
            if i == 3 and (modify_date(tgt) == (Thurs)):
                filecnt_add3 += filecnt_
                filecnt3 = filecnt_add3 / filecnt_
            if i == 4 and (modify_date(tgt) == (Fri)):
                filecnt_add4 += filecnt_
                filecnt4 = filecnt_add4 / filecnt_
            if i == 5 and (modify_date(tgt) == (Satur)):
                filecnt_add5 += filecnt_
                filecnt5 = filecnt_add5 / filecnt_
            if i == 6 and (modify_date(tgt) == (Sun)):
                filecnt_add6 += filecnt_
                filecnt6 = filecnt_add6 / filecnt_
            
   
    for i in range(len(file_list)):
        for j in range(len(file_list[i])):
            filename = file_list[i][j]
            tgt = os.path.join(path, filename)
            size = os.stat(tgt).st_size
            if i == 0 and (modify_date(tgt) == (Mon)):
                totalsize += size
            if i == 1 and (modify_date(tgt) == (Tues)):
                totalsize1 += size
            if i == 2 and (modify_date(tgt) == (Wednes)):
                totalsize2 += size
            if i == 3 and (modify_date(tgt) == (Thurs)):
                totalsize3 += size
            if i == 4 and (modify_date(tgt) == (Fri)):
                totalsize4 += size
            if i == 5 and (modify_date(tgt) == (Satur)):
                totalsize5 += size
            if i == 6 and (modify_date(tgt) == (Sun)):
                totalsize6 += size
                
                totalsiz = totalsize+totalsize1+totalsize2+totalsize3+\
                totalsize4+totalsize5+totalsize6
		filecn = filecnt+filecnt1+filecnt2+filecnt3+filecnt4+filecnt5+\
		filecnt6
    return totalsize,filecnt,totalsize1,filecnt1,totalsize2,filecnt2,\
    totalsize3,filecnt3,totalsize4,filecnt4,totalsize5,filecnt5,totalsize6,\
    filecnt6,totalsiz,filecn 


def weekDOR(path):
    file_list = []
    totalsize,totalsize1,totalsize2,totalsize3,totalsize4,totalsize5,totalsize6\
    = 0,0,0,0,0,0,0
    filecnt_add,filecnt_add1,filecnt_add2,filecnt_add3,filecnt_add4,\
    filecnt_add5,filecnt_add6 = 0,0,0,0,0,0,0
    filecnt,filecnt1,filecnt2,filecnt3,filecnt4,filecnt5,filecnt6 = \
    0,0,0,0,0,0,0    
    keywords = np.array(["CS_OPER","CS_OPER","CS_OPER","CS_OPER","CS_OPER",\
    "CS_OPER","CS_OPER"])
    for root,dirs,files in os.walk(path):
        file_array = np.asarray(files)
    
    for i in range(len(keywords)):
        file_list.append(file_array[np.char.find(file_array, keywords[i]) > -1])
        
    for i in range(len(file_list)):
        for j in range(len(file_list[i])):
            filename = file_list[i][j]
            tgt = os.path.join(path, filename)
            filecnt_ = len(file_list[i])
            if i == 0 and (modify_date(tgt) == (Mon)):
                filecnt_add += filecnt_
                filecnt = filecnt_add / filecnt_
            if i == 1 and (modify_date(tgt) == (Tues)):
                filecnt_add1 += filecnt_
                filecnt1 = filecnt_add1 / filecnt_
            if i == 2 and (modify_date(tgt) == (Wednes)):
                filecnt_add2 += filecnt_
                filecnt2 = filecnt_add2 / filecnt_
            if i == 3 and (modify_date(tgt) == (Thurs)):
                filecnt_add3 += filecnt_
                filecnt3 = filecnt_add3 / filecnt_
            if i == 4 and (modify_date(tgt) == (Fri)):
                filecnt_add4 += filecnt_
                filecnt4 = filecnt_add4 / filecnt_
            if i == 5 and (modify_date(tgt) == (Satur)):
                filecnt_add5 += filecnt_
                filecnt5 = filecnt_add5 / filecnt_
            if i == 6 and (modify_date(tgt) == (Sun)):
                filecnt_add6 += filecnt_
                filecnt6 = filecnt_add6 / filecnt_
            
   
    for i in range(len(file_list)):
        for j in range(len(file_list[i])):
            filename = file_list[i][j]
            tgt = os.path.join(path, filename)
            size = os.stat(tgt).st_size
            if i == 0 and (modify_date(tgt) == (Mon)):
                totalsize += size
            if i == 1 and (modify_date(tgt) == (Tues)):
                totalsize1 += size
            if i == 2 and (modify_date(tgt) == (Wednes)):
                totalsize2 += size
            if i == 3 and (modify_date(tgt) == (Thurs)):
                totalsize3 += size
            if i == 4 and (modify_date(tgt) == (Fri)):
                totalsize4 += size
            if i == 5 and (modify_date(tgt) == (Satur)):
                totalsize5 += size
            if i == 6 and (modify_date(tgt) == (Sun)):
                totalsize6 += size
                
                totalsiz = totalsize+totalsize1+totalsize2+totalsize3+\
                totalsize4+totalsize5+totalsize6
		filecn = filecnt+filecnt1+filecnt2+filecnt3+filecnt4+filecnt5+\
		filecnt6
    return totalsize,filecnt,totalsize1,filecnt1,totalsize2,filecnt2,\
    totalsize3,filecnt3,totalsize4,filecnt4,totalsize5,filecnt5,totalsize6,\
    filecnt6,totalsiz,filecn

	

print 'Starting countdown:'

###############################################################################
# EXCEL EXPORT
###############################################################################
path = r'/Python-3.3.5/download/'  
os.chdir(path)

outfile = TemporaryFile()

book = Workbook()
global_sheet = book.add_sheet('Global Data and weekly data')
l0_sheet = book.add_sheet('L0 Data')
aux_sheet = book.add_sheet('Aux_% Data')
doris_sheet = book.add_sheet('Doris_0 Data')

#global sheet data written in excel file
global_sheet.write(0,0,'Global Data')
row1_1 = global_sheet.row(1)
row1_1.write(0, 'Product')
row1_1.write(1, 'Product Count')
row1_1.write(2, 'Total Size (bytes)')
row2_1 = global_sheet.row(2)
row2_1.write(0, 'L0')
row2_1.write(1, int(float('{1}'.\
format(*getGlobal('/cryosat/ftp-downloads/DSI/L0 files'))))) 
row2_1.write(2, int(float('{0}'.\
format(*getGlobal('/cryosat/ftp-downloads/DSI/L0 files')))))
row3_1 = global_sheet.row(3)
row3_1.write(0, 'AUX_%')
row3_1.write(1, int(float('{1}'.\
format(*getGlobal('/cryosat/ftp-downloads/DSI/auxIliary files')))))
row3_1.write(2, int(float('{0}'.\
format(*getGlobal('/cryosat/ftp-downloads/DSI/auxIliary files')))))
global_sheet.col(0).width = 7000
global_sheet.col(1).width = 7000
global_sheet.col(2).width = 7000
print '======='

# Collated overall global data
row5_1 = global_sheet.row(5)
row5_1.write(0, 'Collected overall Global data')
row6_1 = global_sheet.row(6)
row6_1.write(0, 'Product')
row6_1.write(1, 'Count')
row6_1.write(2, 'Size')
row7_1 = global_sheet.row(7)
row7_1.write(0, 'L0')
row7_1.write(1, int(float('{15}'.\
format(*weekL0('/cryosat/ftp-downloads/DSI/L0 files/LATEST'))))) 
row7_1.write(2, int(float('{14}'.\
format(*weekL0('/cryosat/ftp-downloads/DSI/L0 files/LATEST')))))
row8_1 = global_sheet.row(8)
row8_1.write(0, 'AUX_%')
row8_1.write(1, int(float('{15}'.\
format(*weekL0('/cryosat/ftp-downloads/DSI/auxIliary files/LATEST')))))
row8_1.write(2, int(float('{14}'.\
format(*weekL0('/cryosat/ftp-downloads/DSI/auxIliary files/LATEST')))))
row9_1 = global_sheet.row(9)
row9_1.write(0, 'Doris_0')
row9_1.write(1, int(float('{15}'.\
format(*weekDOR('/cryosat/ftp-downloads/DSI/orbit files/LATEST')))))
row9_1.write(2, int(float('{14}'.\
format(*weekDOR('/cryosat/ftp-downloads/DSI/orbit files/LATEST')))))
print '======<'


#L0 overall sheet data for different file types,
# and also for collected overall files for each day
l0_sheet.write(0,0, 'L0 Data')
row0_2 = l0_sheet.row(1)        #
row1_2 = l0_sheet.row(2)
row2_2 = l0_sheet.row(3)
row3_2 = l0_sheet.row(4)
row4_2 = l0_sheet.row(5)
row5_2 = l0_sheet.row(6)
row6_2 = l0_sheet.row(7)
row7_2 = l0_sheet.row(8)
row8_2 = l0_sheet.row(9)
row9_2 = l0_sheet.row(10)
row10_2 = l0_sheet.row(11)
row11_2 = l0_sheet.row(12)
row12_2 = l0_sheet.row(13)

row0_2.write(0, 'File Type')
row0_2.write(1, 'Count')
row0_2.write(2, 'Size (bytes)')

row1_2.write(0, 'SIR1ACQ')
row1_2.write(1, int(float('{1}'.\
format(*getSize('/cryosat/ftp-downloads/DSI/L0 files/LATEST')))))
row1_2.write(2, int(float('{0}'.\
format(*getSize('/cryosat/ftp-downloads/DSI/L0 files/LATEST')))))

row2_2.write(0, 'SIR1LRC10')
row2_2.write(1, int(float('{3}'.\
format(*getSize('/cryosat/ftp-downloads/DSI/L0 files/LATEST')))))
row2_2.write(2, int(float('{2}'.\
format(*getSize('/cryosat/ftp-downloads/DSI/L0 files/LATEST')))))

row3_2.write(0, 'SIR1LRM_0_')
row3_2.write(1, int(float('{5}'.\
format(*getSize('/cryosat/ftp-downloads/DSI/L0 files/LATEST')))))
row3_2.write(2, int(float('{4}'.\
format(*getSize('/cryosat/ftp-downloads/DSI/L0 files/LATEST')))))

row4_2.write(0, 'SIR1SAC10_')
row4_2.write(1, int(float('{7}'.\
format(*getSize('/cryosat/ftp-downloads/DSI/L0 files/LATEST')))))
row4_2.write(2, int(float('{6}'.\
format(*getSize('/cryosat/ftp-downloads/DSI/L0 files/LATEST')))))

row5_2.write(0, 'SIR1SAR_0_')
row5_2.write(1, int(float('{9}'.\
format(*getSize('/cryosat/ftp-downloads/DSI/L0 files/LATEST')))))
row5_2.write(2, int(float('{8}'.\
format(*getSize('/cryosat/ftp-downloads/DSI/L0 files/LATEST')))))

row6_2.write(0, 'SIR1SIC10_')
row6_2.write(1, int(float('{11}'.\
format(*getSize('/cryosat/ftp-downloads/DSI/L0 files/LATEST')))))
row6_2.write(2, int(float('{10}'.\
format(*getSize('/cryosat/ftp-downloads/DSI/L0 files/LATEST')))))

row7_2.write(0, 'SIR1SIN_0_')
row7_2.write(1, int(float('{13}'.\
format(*getSize('/cryosat/ftp-downloads/DSI/L0 files/LATEST')))))
row7_2.write(2, int(float('{12}'.\
format(*getSize('/cryosat/ftp-downloads/DSI/L0 files/LATEST')))))

row8_2.write(0, 'SIR1TKSA0')
row8_2.write(1, int(float('{15}'.\
format(*getSize('/cryosat/ftp-downloads/DSI/L0 files/LATEST')))))
row8_2.write(2, int(float('{14}'.\
format(*getSize('/cryosat/ftp-downloads/DSI/L0 files/LATEST')))))

row9_2.write(0, 'SIR1TKSI0')
row9_2.write(1, int(float('{17}'.\
format(*getSize('/cryosat/ftp-downloads/DSI/L0 files/LATEST')))))
row9_2.write(2, int(float('{16}'.\
format(*getSize('/cryosat/ftp-downloads/DSI/L0 files/LATEST')))))

row10_2.write(0, 'SIR2SIC10_')
row10_2.write(1, int(float('{19}'.\
format(*getSize('/cryosat/ftp-downloads/DSI/L0 files/LATEST')))))
row10_2.write(2, int(float('{18}'.\
format(*getSize('/cryosat/ftp-downloads/DSI/L0 files/LATEST')))))

row11_2.write(0, 'SIR2SIN_0')
row11_2.write(1, int(float('{21}'.\
format(*getSize('/cryosat/ftp-downloads/DSI/L0 files/LATEST')))))
row11_2.write(2, int(float('{20}'.\
format(*getSize('/cryosat/ftp-downloads/DSI/L0 files/LATEST')))))

row12_2.write(0, 'SIR2STST0')
row12_2.write(1, int(float('{23}'.\
format(*getSize('/cryosat/ftp-downloads/DSI/L0 files/LATEST')))))
row12_2.write(2, int(float('{22}'.\
format(*getSize('/cryosat/ftp-downloads/DSI/L0 files/LATEST')))))

#L0 overall sheet data for different file types,
# and also for collected overall files for each day
print '=====<<'


#Aux_% overall sheet data for different file types,
# and also for collected overall files for each day
aux_sheet.write(0,0, 'Aux_% Data')
row0_3 = aux_sheet.row(1)        #
row1_3 = aux_sheet.row(2)
row2_3 = aux_sheet.row(3)
row3_3 = aux_sheet.row(4)
row4_3 = aux_sheet.row(5)
row5_3 = aux_sheet.row(6)
row6_3 = aux_sheet.row(7)
row7_3 = aux_sheet.row(8)
row8_3 = aux_sheet.row(9)
row9_3 = aux_sheet.row(10)
row10_3 = aux_sheet.row(11)
row11_3 = aux_sheet.row(12)
row12_3 = aux_sheet.row(13)
row13_3 = aux_sheet.row(14)
row14_3 = aux_sheet.row(15)
row15_3 = aux_sheet.row(16)
row16_3 = aux_sheet.row(17)
row17_3 = aux_sheet.row(18)
row18_3 = aux_sheet.row(19)
row19_3 = aux_sheet.row(20)

row0_3.write(0, 'File Type')
row0_3.write(1, 'Count')
row0_3.write(2, 'Size (bytes)')

row1_3.write(0, 'AUX_DORUSO')
row1_3.write(1, int(float('{1}'.\
format(*getSizeaux('/cryosat/ftp-downloads/DSI/auxIliary files/LATEST')))))
row1_3.write(2, int(float('{0}'.\
format(*getSizeaux('/cryosat/ftp-downloads/DSI/auxIliary files/LATEST')))))

row2_3.write(0, 'AUX_IONGIM')
row2_3.write(1, int(float('{3}'.\
format(*getSizeaux('/cryosat/ftp-downloads/DSI/auxIliary files/LATEST')))))
row2_3.write(2, int(float('{2}'.\
format(*getSizeaux('/cryosat/ftp-downloads/DSI/auxIliary files/LATEST')))))

row3_3.write(0, 'AUXIMOG_2D')
row3_3.write(1, int(float('{5}'.\
format(*getSizeaux('/cryosat/ftp-downloads/DSI/auxIliary files/LATEST')))))
row3_3.write(2, int(float('{4}'.\
format(*getSizeaux('/cryosat/ftp-downloads/DSI/auxIliary files/LATEST')))))

row4_3.write(0, 'AUX_MOG_2D')
row4_3.write(1, int(float('{7}'.\
format(*getSizeaux('/cryosat/ftp-downloads/DSI/auxIliary files/LATEST')))))
row4_3.write(2, int(float('{6}'.\
format(*getSizeaux('/cryosat/ftp-downloads/DSI/auxIliary files/LATEST')))))

row5_3.write(0, 'AUXISEAMPS')
row5_3.write(1, int(float('{9}'.\
format(*getSizeaux('/cryosat/ftp-downloads/DSI/auxIliary files/LATEST')))))
row5_3.write(2, int(float('{8}'.\
format(*getSizeaux('/cryosat/ftp-downloads/DSI/auxIliary files/LATEST')))))

row6_3.write(0, 'AUX_SEA_IC')
row6_3.write(1, int(float('{11}'.\
format(*getSizeaux('/cryosat/ftp-downloads/DSI/auxIliary files/LATEST')))))
row6_3.write(2, int(float('{10}'.\
format(*getSizeaux('/cryosat/ftp-downloads/DSI/auxIliary files/LATEST')))))

row7_3.write(0, 'AUX_SURFPS')
row7_3.write(1, int(float('{13}'.\
format(*getSizeaux('/cryosat/ftp-downloads/DSI/auxIliary files/LATEST')))))
row7_3.write(2, int(float('{12}'.\
format(*getSizeaux('/cryosat/ftp-downloads/DSI/auxIliary files/LATEST')))))

row8_3.write(0, 'AUXIU_WIND')
row8_3.write(1, int(float('{15}'.\
format(*getSizeaux('/cryosat/ftp-downloads/DSI/auxIliary files/LATEST')))))
row8_3.write(2, int(float('{14}'.\
format(*getSizeaux('/cryosat/ftp-downloads/DSI/auxIliary files/LATEST')))))

row9_3.write(0, 'AUXIV_WIND')
row9_3.write(1, int(float('{17}'.\
format(*getSizeaux('/cryosat/ftp-downloads/DSI/auxIliary files/LATEST')))))
row9_3.write(2, int(float('{16}'.\
format(*getSizeaux('/cryosat/ftp-downloads/DSI/auxIliary files/LATEST')))))

row10_3.write(0, 'AUX_WETTRP')
row10_3.write(1, int(float('{19}'.\
format(*getSizeaux('/cryosat/ftp-downloads/DSI/auxIliary files/LATEST')))))
row10_3.write(2, int(float('{18}'.\
format(*getSizeaux('/cryosat/ftp-downloads/DSI/auxIliary files/LATEST')))))

row11_3.write(0, 'AUX_SEAMPS')
row11_3.write(1, int(float('{21}'.\
format(*getSizeaux('/cryosat/ftp-downloads/DSI/auxIliary files/LATEST')))))
row11_3.write(2, int(float('{20}'.\
format(*getSizeaux('/cryosat/ftp-downloads/DSI/auxIliary files/LATEST')))))

row12_3.write(0, 'AUXISURFPS')
row12_3.write(1, int(float('{23}'.\
format(*getSizeaux('/cryosat/ftp-downloads/DSI/auxIliary files/LATEST')))))
row12_3.write(2, int(float('{22}'.\
format(*getSizeaux('/cryosat/ftp-downloads/DSI/auxIliary files/LATEST')))))

row13_3.write(0, 'AUX_U_WIND')
row13_3.write(1, int(float('{25}'.\
format(*getSizeaux('/cryosat/ftp-downloads/DSI/auxIliary files/LATEST')))))
row13_3.write(2, int(float('{24}'.\
format(*getSizeaux('/cryosat/ftp-downloads/DSI/auxIliary files/LATEST')))))

row14_3.write(0, 'AUX_V_WIND')
row14_3.write(1, int(float('{27}'.\
format(*getSizeaux('/cryosat/ftp-downloads/DSI/auxIliary files/LATEST')))))
row14_3.write(2, int(float('{26}'.\
format(*getSizeaux('/cryosat/ftp-downloads/DSI/auxIliary files/LATEST')))))

row15_3.write(0, 'AUXIWETTRP')
row15_3.write(1, int(float('{29}'.\
format(*getSizeaux('/cryosat/ftp-downloads/DSI/auxIliary files/LATEST')))))
row15_3.write(2, int(float('{28}'.\
format(*getSizeaux('/cryosat/ftp-downloads/DSI/auxIliary files/LATEST')))))

row16_3.write(0, 'AUX_POLLOC')
row16_3.write(1, int(float('{31}'.\
format(*getSizeaux('/cryosat/ftp-downloads/DSI/auxIliary files/LATEST')))))
row16_3.write(2, int(float('{30}'.\
format(*getSizeaux('/cryosat/ftp-downloads/DSI/auxIliary files/LATEST')))))

row17_3.write(0, 'AUXIIONGIM')
row17_3.write(1, int(float('{33}'.\
format(*getSizeaux('/cryosat/ftp-downloads/DSI/auxIliary files/LATEST')))))
row17_3.write(2, int(float('{32}'.\
format(*getSizeaux('/cryosat/ftp-downloads/DSI/auxIliary files/LATEST')))))

row18_3.write(0, 'AUX_ORBDOP')
row18_3.write(1, int(float('{5}'.\
format(*getSizeorb('/cryosat/ftp-downloads/DSI/orbit files/LATEST')))))
row18_3.write(2, int(float('{4}'.\
format(*getSizeorb('/cryosat/ftp-downloads/DSI/orbit files/LATEST')))))

row19_3.write(0, 'AUX_ORBDOR')
row19_3.write(1, int(float('{1}'.\
format(*getSizeorb('/cryosat/ftp-downloads/DSI/orbit files/LATEST')))))
row19_3.write(2, int(float('{0}'.\
format(*getSizeorb('/cryosat/ftp-downloads/DSI/orbit files/LATEST')))))

#Aux_% overall sheet data for different file types,
# and also for collected overall files for each day
print '====<<<'


#Doris_0 overall sheet data for different file types,
# and also for collected overall files for each day
doris_sheet.write(0,0, 'Doris_0 Data')
row0_4 = doris_sheet.row(1)        #
row1_4 = doris_sheet.row(2)
row2_4 = doris_sheet.row(3)

row0_4.write(0, 'File Type')
row0_4.write(1, 'Count')
row0_4.write(2, 'Size (bytes)')

row1_4.write(0, 'DOR_NAV_0')
row1_4.write(1, int(float('{3}'.\
format(*getSizeorb('/cryosat/ftp-downloads/DSI/orbit files/LATEST')))))
row1_4.write(2, int(float('{2}'.\
format(*getSizeorb('/cryosat/ftp-downloads/DSI/orbit files/LATEST')))))
row2_4.write(0, 'MPL_ORBPRE')
row2_4.write(1, int(float('{7}'.\
format(*getSizeorb('/cryosat/ftp-downloads/DSI/orbit files/LATEST')))))
row2_4.write(2, int(float('{6}'.\
format(*getSizeorb('/cryosat/ftp-downloads/DSI/orbit files/LATEST')))))
#Doris_0 overall sheet data for different file types,
# and also for collected overall files for each day
print '===<<<<'


#WEEKLY COUNTS AND SIZES PER DAY
#I.E. TOP LINE = MONDAY, SECOND LINE = TUESDAY ETC...

# L0 weekly day by day count and sizes

row0_2 = l0_sheet.row(1)        #
row1_2 = l0_sheet.row(2)
row2_2 = l0_sheet.row(3)
row3_2 = l0_sheet.row(4)
row4_2 = l0_sheet.row(5)
row5_2 = l0_sheet.row(6)
row6_2 = l0_sheet.row(7)
row7_2 = l0_sheet.row(8)

row0_2.write(4, 'Day of the week')
row0_2.write(5, 'Size (bytes)')
row0_2.write(6, 'Count')

row1_2.write(4, 'Monday')
row1_2.write(5, int(float('{0}'.\
format(*weekL0('/cryosat/ftp-downloads/DSI/L0 files/LATEST')))))
row1_2.write(6, int(float('{1}'.\
format(*weekL0('/cryosat/ftp-downloads/DSI/L0 files/LATEST')))))

row2_2.write(4, 'Tuesday')
row2_2.write(5, int(float('{2}'.\
format(*weekL0('/cryosat/ftp-downloads/DSI/L0 files/LATEST')))))
row2_2.write(6, int(float('{3}'.\
format(*weekL0('/cryosat/ftp-downloads/DSI/L0 files/LATEST')))))

row3_2.write(4, 'Wednesday')
row3_2.write(5, int(float('{4}'.\
format(*weekL0('/cryosat/ftp-downloads/DSI/L0 files/LATEST')))))
row3_2.write(6, int(float('{5}'.\
format(*weekL0('/cryosat/ftp-downloads/DSI/L0 files/LATEST')))))

row4_2.write(4, 'Thursday')
row4_2.write(5, int(float('{6}'.\
format(*weekL0('/cryosat/ftp-downloads/DSI/L0 files/LATEST')))))
row4_2.write(6, int(float('{7}'.\
format(*weekL0('/cryosat/ftp-downloads/DSI/L0 files/LATEST')))))

row5_2.write(4, 'Friday')
row5_2.write(5, int(float('{8}'.\
format(*weekL0('/cryosat/ftp-downloads/DSI/L0 files/LATEST')))))
row5_2.write(6, int(float('{9}'.\
format(*weekL0('/cryosat/ftp-downloads/DSI/L0 files/LATEST')))))

row6_2.write(4, 'Saturday')
row6_2.write(5, int(float('{10}'.\
format(*weekL0('/cryosat/ftp-downloads/DSI/L0 files/LATEST')))))
row6_2.write(6, int(float('{11}'.\
format(*weekL0('/cryosat/ftp-downloads/DSI/L0 files/LATEST')))))

row7_2.write(4, 'Sunday')
row7_2.write(5, int(float('{12}'.\
format(*weekL0('/cryosat/ftp-downloads/DSI/L0 files/LATEST')))))
row7_2.write(6, int(float('{13}'.\
format(*weekL0('/cryosat/ftp-downloads/DSI/L0 files/LATEST')))))
# L0 weekly day by day count and sizes
print '==<<<<<'


# Aux_% weekly day by day count and sizes

row0_3 = aux_sheet.row(1)        
row1_3 = aux_sheet.row(2)
row2_3 = aux_sheet.row(3)
row3_3 = aux_sheet.row(4)
row4_3 = aux_sheet.row(5)
row5_3 = aux_sheet.row(6)
row6_3 = aux_sheet.row(7)
row7_3 = aux_sheet.row(8)

row0_3.write(4, 'Day of the week')
row0_3.write(5, 'Size (bytes)')
row0_3.write(6, 'Count')

row1_3.write(4, 'Monday')
row1_3.write(5, int(float('{0}'.\
format(*weekL0('/cryosat/ftp-downloads/DSI/auxIliary files/LATEST')))))
row1_3.write(6, int(float('{1}'.\
format(*weekL0('/cryosat/ftp-downloads/DSI/auxIliary files/LATEST')))))

row2_3.write(4, 'Tuesday')
row2_3.write(5, int(float('{2}'.\
format(*weekL0('/cryosat/ftp-downloads/DSI/auxIliary files/LATEST')))))
row2_3.write(6, int(float('{3}'.\
format(*weekL0('/cryosat/ftp-downloads/DSI/auxIliary files/LATEST')))))

row3_3.write(4, 'Wednesday')
row3_3.write(5, int(float('{4}'.\
format(*weekL0('/cryosat/ftp-downloads/DSI/auxIliary files/LATEST')))))
row3_3.write(6, int(float('{5}'.\
format(*weekL0('/cryosat/ftp-downloads/DSI/auxIliary files/LATEST')))))

row4_3.write(4, 'Thursday')
row4_3.write(5, int(float('{6}'.\
format(*weekL0('/cryosat/ftp-downloads/DSI/auxIliary files/LATEST')))))
row4_3.write(6, int(float('{7}'.\
format(*weekL0('/cryosat/ftp-downloads/DSI/auxIliary files/LATEST')))))

row5_3.write(4, 'Friday')
row5_3.write(5, int(float('{8}'.\
format(*weekL0('/cryosat/ftp-downloads/DSI/auxIliary files/LATEST')))))
row5_3.write(6, int(float('{9}'.\
format(*weekL0('/cryosat/ftp-downloads/DSI/auxIliary files/LATEST')))))

row6_3.write(4, 'Saturday')
row6_3.write(5, int(float('{10}'.\
format(*weekL0('/cryosat/ftp-downloads/DSI/auxIliary files/LATEST')))))
row6_3.write(6, int(float('{11}'.\
format(*weekL0('/cryosat/ftp-downloads/DSI/auxIliary files/LATEST')))))

row7_3.write(4, 'Sunday')
row7_3.write(5, int(float('{12}'.\
format(*weekL0('/cryosat/ftp-downloads/DSI/auxIliary files/LATEST')))))
row7_3.write(6, int(float('{13}'.\
format(*weekL0('/cryosat/ftp-downloads/DSI/auxIliary files/LATEST')))))
# Aux_% weekly day by day count and sizes  
print '=<<<<<<'


# Doris_0 weekly day by day count and sizes

row0_4 = doris_sheet.row(1)        #
row1_4 = doris_sheet.row(2)
row2_4 = doris_sheet.row(3)
row3_4 = doris_sheet.row(4)
row4_4 = doris_sheet.row(5)
row5_4 = doris_sheet.row(6)
row6_4 = doris_sheet.row(7)
row7_4 = doris_sheet.row(8)

row0_4.write(4, 'Day of the week')
row0_4.write(5, 'Size(bytes)')
row0_4.write(6, 'Count')

row1_4.write(4, 'Monday')
row1_4.write(5, int(float('{0}'.\
format(*weekDOR('/cryosat/ftp-downloads/DSI/orbit files/LATEST')))))
row1_4.write(6, int(float('{1}'.\
format(*weekDOR('/cryosat/ftp-downloads/DSI/orbit files/LATEST')))))

row2_4.write(4, 'Tuesday')
row2_4.write(5, int(float('{2}'.\
format(*weekDOR('/cryosat/ftp-downloads/DSI/orbit files/LATEST')))))
row2_4.write(6, int(float('{3}'.\
format(*weekDOR('/cryosat/ftp-downloads/DSI/orbit files/LATEST')))))

row3_4.write(4, 'Wednesday')
row3_4.write(5, int(float('{4}'.\
format(*weekDOR('/cryosat/ftp-downloads/DSI/orbit files/LATEST')))))
row3_4.write(6, int(float('{5}'.\
format(*weekDOR('/cryosat/ftp-downloads/DSI/orbit files/LATEST')))))

row4_4.write(4, 'Thursday')
row4_4.write(5, int(float('{6}'.\
format(*weekDOR('/cryosat/ftp-downloads/DSI/orbit files/LATEST')))))
row4_4.write(6, int(float('{7}'.\
format(*weekDOR('/cryosat/ftp-downloads/DSI/orbit files/LATEST')))))

row5_4.write(4, 'Friday')
row5_4.write(5, int(float('{8}'.\
format(*weekDOR('/cryosat/ftp-downloads/DSI/orbit files/LATEST')))))
row5_4.write(6, int(float('{9}'.\
format(*weekDOR('/cryosat/ftp-downloads/DSI/orbit files/LATEST')))))

row6_4.write(4, 'Saturday')
row6_4.write(5, int(float('{10}'.\
format(*weekDOR('/cryosat/ftp-downloads/DSI/orbit files/LATEST')))))
row6_4.write(6, int(float('{11}'.\
format(*weekDOR('/cryosat/ftp-downloads/DSI/orbit files/LATEST')))))

row7_4.write(4, 'Sunday')
row7_4.write(5, int(float('{12}'.\
format(*weekDOR('/cryosat/ftp-downloads/DSI/orbit files/LATEST')))))
row7_4.write(6, int(float('{13}'.\
format(*weekDOR('/cryosat/ftp-downloads/DSI/orbit files/LATEST')))))
# Doris_0 weekly day by day count and sizes
print '<<<<<<<'

book.save('CS_Data.xls')
book.save(outfile)


print 'PROCESSING COMPLETE'
