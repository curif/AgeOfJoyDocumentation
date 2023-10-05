```

You are a developer expert in AGEBasic. AGEBasic is un subset from the BASIC programming language, after read and understand the AGEBasic specification I want to ask you for some programs to do specific task. Please let me know when you are ready. 
## Variables

AGEBasic supports numbers (double precision) and strings.
A variable name can contain letters a numbers only. AGEBasic isn't case sensitive, the variable A is the same as a. booleans are not variable type, but anything different than 0 or "" is considered true.

Numbered lines: Each line of code should be numbered and be in ascending order.

Instruction set. Each line number is followed by an instruction

* LET: assign a value to a variable, ex: LET a=10
* LETS: assign multiple values, ex: LETS a,b=10,20
* REM: a comment, ex: 10 REM this is a comment. It's the only way to register comments in the program.
* END: finish the program
* IF/THEN: conditional, ELSE is not allowed. Ex: IF x=1 THEN LET a=2
* GOTO: to jump to a line number. Ex: GOTO 50
* GOSUB: to jump to a line, and to back using RETURN. Ex: GOSUB 5000
* RETURN: jump back to the next line after the GOSUB
* CALL: to call a function discarding the result. Ex: CALL CabRoomReplace(0, "pacman")
* FOR/TO/NEXT: to create loops. Ex: "for x=0 to 10 ... next x" Initial and end values can be expressions. Initial value is computed at start of the cycle. The end value is computed during the `NEXT` sentence execution. The `NEXT` sentence evaluates if the cycle should repeat. At least one cycle is executed always.

Functions: Functions can receive parameters. Parameters must be enclosed in ().

Math Functions:
- ABS, COS, SIN, TAN, MOD
- MAX, MIN: of two numbers, Ex: LET a = max(10,20) max will return 20
- RND: a random between two numbers. rnd(2,10) could be 8.
- NOT: the inverse of the boolean expression. Ex: "if NOT(0) then goto 100"

Introspection
- exists(string): to know if a variable is defined, returns 1 or 0 (true or false).

String functions
- LEN, UCASE, LCASE, 
- SUBSTR: Ex: susbtr("abc", 1, 2)  is "bc", starting in 1 and getting two characters.
- TRIM, LTRIM, RTRIM.
- STR: Ex: str(10) is "10"

Room related
To get information about rooms

- RoomName(): The name of the room where the player is.
- RoomCount(): How many Rooms are in the game.
- RoomGet(number): Get the name of the room. Ex: LET name, desc = RoomGet(0) to get the name and the description of the Room number zero.
- RoomGetName(number): get the name of the room.
- RoomGetDesc(number): to get the description.

### Cabinets related

Applies to cabinets deployed in the room.

- CabRoomCount(): how many cabinets are in the room
- CabRoomGetName(number): get the cabinet name by its index in the room.
- CabRoomReplace(number, cabinet name): replace a cabinet by another.

Applies to cabinet database

- CabDbCount(): returns the cabinet quantity registered.
- CabDbCountInRoom(string): how many cabinets are registered in one particular room. Ex: LET count = CabDbCountInRoom("Room001") 
- CabDBGetName(number): get a cabinet name using the position. Ex: CabDBGetName(30) could return "pacman"
- CabDBDelete(currentRoomName, cabinetIndex): delete the cabinet assignment in the database. 
- CabDBAdd(currentRoomName, cabinetIndex, newCabinetName): assign a cabinet to a position in a room.
- CabDBAssign(room, cabinetIndex, newCabinetName): assign a cabinet to a existent position in DB.
- CabDBGetAssigned(room, cabinetIndex): returns the cabinet name assigned to a position in a room.

```

Response (example):

```
Great! I'm ready to help you develop a program in AGEBasic. Before we dive into coding, let's clarify the requirements and what you want the program to do. Please let me know what kind of program you want to build or what specific task you want it to perform using AGEBasic. Additionally, if you have any specific questions or doubts about the language, feel free to ask. Once we have a clear objective, we can start writing the AGEBasic code together.
```

Then ask for a program:

  
> [!Quote] I need an AGEBasic program to change cabinets randomically in the room. The program runs, and the cabinets change by others.

Response:
```basic
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
