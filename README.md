work = True




def FinalPrint(filePosition, totalLines, emptyLines, linesWithZ, zCount, linesWithAnd):

    print("File:", filePosition)

    print("Total lines:", totalLines)

    print("Empty lines:", emptyLines)

    print("Lines with ^Z^:", linesWithZ)

    print("^Z^ count:", zCount)

    print("Lines with ^and^:", linesWithAnd)




while work:

    userFilePosition = ""




    userFilePosition = str(input("File "))

    file = userFilePosition




    f = open(file, "r")

    data = f.read()




    dataLines = open(file, "r").readlines();




    _totalLines = 0  #

    _emptyLines = 0  #

    _linesWithZ = 0  #

    _zCount = 0  #

    _linesWithAnd = 0  #




    symbols = len(data)




    if symbols > 0:

        _totalLines = 1

        for i in data:

            if i == "\n":

                _totalLines += 1

            elif i == "Z":

                _zCount += 1

            elif i == "z":

                _zCount += 1




        j = 0

        while j < _totalLines:

            txt = dataLines[j]




            sizeTxt = len(txt)




            if sizeTxt > 1:

                useZInLine = False




                saveStr = ""

                for k in txt:

                    sizeSaveStr = len(saveStr)




                    if sizeSaveStr == 0:

                        if k == "A":

                            saveStr = saveStr + "A"

                        elif k == "a":

                            saveStr = saveStr + "a"

                        else:

                            saveStr = ""




                    elif sizeSaveStr == 1:

                        if k == "N":

                            saveStr = saveStr + "N"

                        elif k == "n":

                            saveStr = saveStr + "n"

                        else:

                            saveStr = ""




                    elif sizeSaveStr == 2:

                        if k == "D":

                            saveStr = saveStr + "D"

                        elif k == "d":

                            saveStr = saveStr + "d"

                        else:

                            saveStr = ""




                    elif sizeSaveStr == 3:




                        _linesWithAnd += 1

                        saveStr = ""




                    if useZInLine != True:

                        if k == "Z":

                            _linesWithZ += 1

                            useZInLine = True

                        elif k == "z":

                            _linesWithZ += 1

                            useZInLine = True

            else:

                _emptyLines += 1




            j += 1




        FinalPrint(userFilePosition, _totalLines, _emptyLines, _linesWithZ, _zCount, _linesWithAnd)

    else:

        print("Цей файл пустий ")




    q = ""




    while True:

        q = str(input("Потрібно проаналізувати ще один файл? YES аба NO "))

        if q == "YES":

            break

        elif q == "NO":

            break




    if q == "NO":

        work = False

        break

print("Program end")
