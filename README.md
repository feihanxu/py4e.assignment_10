# py4e.assignment_10
name = input("Enter file:")
if len(name) < 1 : name = "mbox-short.txt"
handle = open(name)
fh = dict()
for line in handle:
    line = line.rstrip()
    if not line.startswith('From '): 
        continue
    else:
    	words = line.split()
    time = words[5].split(":")
    fh[time[0]] = fh.get(time[0], 0) + 1
        
lst = list()
for key,value in fh.items():
    lst.append((key,value))
lst = sorted(lst)

for hour,count in lst:
    print(hour,count)

