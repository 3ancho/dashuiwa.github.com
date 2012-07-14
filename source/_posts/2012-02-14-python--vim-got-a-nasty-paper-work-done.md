--- 
layout: post
title: "Python + Vim: Got a nasty paper work done "
tags: 
---
You are asked to fill out of Excel with the new eligible members of a group.

What you got: An Excel from the headquarter of this group contains a list of
people, which has a special formatting and equation kinda stuff plus a warning
"formatting couldn't be changed!!!" This Excel also include the existing
members of this group. With "M" in the "Existing Member" column.

Another Excel from a different party, which has a list of people. However
there are more columns in this Excel, and even it shares the same column with
the previous one, they name their value differently. For example, in "major"
column "CPE" is equivalent to "Computer Engg" in another Excel. Another
example, in "First Name" column "Robert Allen" is "Robert" in another Excel.
Why? Simply because one party doesn't care about middle name. The other, do
care, coma, but don't even create a column "Middle Name", thus put middle name
along with first name.

Your goal: The final Excel will have the same format as the first Excel.

My solution: Export both Excels in to .csv files. Manipulate the columns a
little bit using vim macro. First file: list.csv Second file: school.csv
Output file: output.csv

I will copy the output.csv and copy into the first Excel

    
    aaa = open("list.csv", "r")
    bbb = open("school.csv", "r")
    out = open("out.csv", "w")
    
    member = []
    
    ls1 = tbp.readlines()
    for line in ls1:
        words = line.split(",")
        if " " in words[0]:
            words[0] = words[0].split(" ")[0]
        key = (words[0], words[1])
        member.append(key)
    
    ls2 = iit.readlines()
    
    major_dict = {"BME": "Biomedical engg",
                  "CPE": "Computer engg",
                  "EE": "Electrical engg",
                  "ARCE": "Architectural engg",
                  "CE": "Civil engg",
                  "AE": "Aerospace engg",
                  "ME": "Mechanical engg",
                  "CHE": "Chemical engg",
                  "MSE": "Materials science and engg"}
    
    words = []
    for line in ls2:
        if line == " " or line == " ":
            continue
        words = line.split(",")
        words[5].replace(" ", "")
        words[5].replace(" ", "")
    
        if words[5] in major_dict:
            major = major_dict[words[5]]
            fn = words[1]
            ln = words[0]
            sj = words[2]
            if sj == "Junior":
                year = "2013"
            else:
                year = "2012"
            month = "May"
            mem = ""
            for item in member:
                if fn in item and ln in item:
                    mem = "M"
            out.write("{0},{1},{2},{3},{4},{5},{6} ".\
                        format(fn,ln,sj,month,year,major,mem) )
        else:
            print "ERROR! ", line
    tbp.close()
    iit.close()
    out.close()
    

I am not familiar with Excel macro or any trick that could solve this problem,
with grace. 

