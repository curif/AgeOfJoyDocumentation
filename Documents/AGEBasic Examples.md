
### Comments 

```Basic
10 rem coment
20 ' comment
30 let a=10 'comment
40 end
```

### Calculate the sum of cabinets assigned in all rooms
```Basic
10 REM Program to calculate the sum of cabinets assigned in all rooms
20 LET totalRooms = RoomCount()
30 LET sumOfCabinets = 0

40 FOR roomIndex = 0 TO totalRooms - 1
50     LET roomNameFromIndex = RoomGetName(roomIndex)
60     LET assignedCabinetsInRoom = CabDBCountInRoom(roomNameFromIndex)
70     LET sumOfCabinets = sumOfCabinets + assignedCabinetsInRoom
80 NEXT roomIndex

90 PRINT 0,0, "Sum of Cabinets Assigned: " + STR(sumOfCabinets)
100 END
```

### Replace each cabinet in all rooms with a random cabinet
```Basic
10 REM Replace each cabinet in all rooms with a random cabinet
20 LET totalRooms = RoomCount()
30 LET totalCabinetsDB = CabDbCount()
35 LET cont = 0
37 LET playerRoom = RoomName()

40 REM Loop through each room
50 FOR roomIndex = 0 TO totalRooms - 1
60     LET currentRoomName = RoomGetName(roomIndex)
70     LET totalCabinetsRoom = CabDBCountInRoom(currentRoomName)
72     if (totalCabinetsRoom = 0) then goto 180

75     gosub 500

80     REM Loop through each cabinet in the current room
90     FOR cabinetIndex = 0 TO totalCabinetsRoom - 1

100        LET randomIndex = INT(RND(1, totalCabinetsDB)) - 1
110        LET newCabinetName = CabDbGetName(randomIndex)

115        print 0, 4+cabinetIndex, "#" + str(cabinetIndex) + " by DB #" +str(randomIndex) + ": " + str(newCabinetName) + "        "

120        REM Replace the cabinet in the current room with the random cabinet

129        REM is a cabinet assigned? we need one to proceed to change it.
130        if CabDBGetAssigned(currentRoomName, cabinetIndex) = "" then goto 170

139        rem change the database by assining the cabinet on the old position
140        CALL CabDBAssign(currentRoomName, cabinetIndex, newCabinetName)

149        rem change in current playerRoom if it is the same to see it inmediatly
150        if playerRoom = currentRoomName then call CabRoomReplace(cabinetIndex, newCabinetName)

160        let cont=cont+1

170    NEXT cabinetIndex
180 NEXT roomIndex

190 CALL CabDBSave()
200 goto 10000

500 REM show main info
510 CLS
520 print 0,1, "Rooms: " + str(totalRooms), 0, 0
530 print 0,2, "Cabinets in DB:" + str(totalCabinetsDB), 0, 0
540 print 0,3, "room:" + currentRoomName + " cabs:" + str(totalCabinetsRoom), 1, 0
550 show
560 return

10000 print 0, 23, "replaced: " + str(cont)
10010 print 0, 24, "PRESS B to end", 1
10050 IF ControlActive("JOYPAD_B") THEN END
10060 goto 10050
```

### Randomize two cabinets in a room
```Basic
10 REM Cabinet Randomizer
20 LET numCabinets = CabRoomCount()
30 IF (numCabinets < 2) THEN GOTO 70  
40 LET index1 = INT(RND(0, numCabinets))
50 LET index2 = INT(RND(0, numCabinets))
60 IF (index1 = index2) THEN GOTO 40
70 LET cabinet1 = CabRoomGetName(index1)
80 LET cabinet2 = CabRoomGetName(index2)
90 CALL CabRoomReplace(index1, cabinet2)
100 CALL CabRoomReplace(index2, cabinet1)
110 END
```

### Show some text on the screen
```Basic
10 CLS

20 LET x = 0
30 LET y = 0
35 LET inverted = 0

40 PRINT x, y, "test: "+STR(y), inverted
50 LET y = y+1
55 LET inverted = MOD(y, 2)

60 IF y < 10 THEN GOTO 40

70 PRINT 0, y, "END"
```

---

More examples, related to Cabinets configuration: [[AGEBasic in cabinets]].

