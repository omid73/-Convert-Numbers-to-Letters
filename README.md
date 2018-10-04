# -Convert-Numbers-to-Letters
num = int(input("Please enter a number between 1 and 9999: "))
w1 = {1: 'one', 2: 'two', 3: 'three',4: 'four', 5: 'five', \
            6:'six', 7: 'seven', 8: 'eight', 9: 'nine', 10: 'ten', \
            11: 'eleven', 12: 'twelve', 13: 'thirteen', 14: 'fourteen', \
            15: 'fifteen', 16: 'sixteen', 17: 'seventeen', 18: 'eighteen', 19: 'nineteen'}
w2 = {10:'ten',20:'twenty',30:'thirty',40:'forty',50:'fifty',60:'sixty',70:'seventy',80:'eighty',90:'ninety'}
w3 = {100:'one hundred',200:'two hundred',300:'three hundred', \
           400:'four hundred',500:'five hundred',600:'six hundred',\
           700:'seven hundred',800:'eight hundred',900:'nine hundred'}
w4 = {1000:'one thousand',2000:'two thousand',3000:'three thousand', \
           4000:'four thousand',5000:'five thousand',6000:'six thousand',\
           7000:'seven thousand',8000:'eight thousand',9000:'nine thousand'}

if (num>=1 and num<=19):
    print(w1.get(num),end="")
elif (num >= 20 and num <= 99):
    num = str(num)
    d = int(num[0]) * 10 
    y = int(num[1])
    if (y==0):
        print("{}".format(w2[d]),end="")
    else:
        print("{} {}".format(w2[d],w1[y]),end="")
elif (num >= 100 and num<=999):
    num = str(num)
    s = int(num[0]) * 100
    d = int(num[1]) * 10
    y = int(num[2])
    if (d==0 and y==0):
        print(w3[s],end="")
    elif (d==0):
        print("{} {}".format(w3[s],w1[y]),end="")
    elif (y==0):
        num = str(num)
        c = int(num[1:])
        if c ==10:
            print("{} {}" .format(w3[s],w1[c]),end="")
        else:
            print("{} {}".format(w3[s],w2[c]),end="")
    else:
        print("{} {} {}".format(w3[s],w2[d],w1[y]),end="")
elif (num>=1000 and num<=9999):
    num=str(num)
    h = int(num[0]) * 1000
    s = int(num[1]) * 100
    d = int(num[2]) * 10
    y = int(num[3])
    if(s==0 and d==0 and y==0):
        print(w4[h],end="")
    elif (s==0 and d==0):
        print("{} {}".format(w4[h],w1[y]),end="")
    elif (d==0  and y==0):
        num = str(num)
        c= int(num[1:])
        print("{} {}".format(w4[h],w3[c]),end="")
    elif(s==0 and y==0):
        num = str(num)
        c = int(num[2:])
        if (c==10):
            print("{} {}".format(w4[h],w1[c]),end="")
        print("{} {}".format(w4[h],w2[c]),end="")
    elif (s==0):
        num = str(num)#9099
        c =int(num[2:4])
        c =str(c)
        c_1 = int(c[0]) * 10
        c_2 = int(c[1])
        print("{} {} {}".format(w4[h],w2[c_1],w1[c_2]),end="")
    elif (d==0):
        num = str(num)
        c =int(num[3])
        print("{} {} {}".format(w4[h],w3[s],w1[c]),end="")
    elif (y==0):
        print("{} {} {}".format(w4[h],w3[s],w2[d]),end="")
    else:    
        z ="{} {} {} {}".format(w4[h],w3[s],w2[d],w1[y])
        print(z,end="")  
