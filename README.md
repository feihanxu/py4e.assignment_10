# py4e.assignment_10
name = input("Enter file:")
if len(name) < 1 : name = "mbox-short.txt"
handle = open(name)
fh = dict()
for line in handle:
    line = line.rstrip
    if not line.startswith("From "):
        continue
    else:
        words = line.split()
    time = words[5].split[":"]
    fh[time[0]] = fh.get(time[0],0) + 1
    #why we use list? Bcz we want to order the items.
    
lst = list()
for key,value in fh.items():
    # remember .items()! only with items we can have tuples
    lst = append((key,value))
        
lst = sorted(lst)
for hour,count in lst:
    print(hour,count)

