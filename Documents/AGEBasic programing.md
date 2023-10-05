BASIC is a popular programming language known for its simplicity and ease of use. It has been used in various applications, especially in the early days of computing.

`AGEBasic` draws its inspiration from another programming language called [Tiny Basic](https://en.wikipedia.org/wiki/Tiny_BASIC) which is a minimalistic version of BASIC. However, AGEBasic does not strictly adhere to all the rules and limitations of Tiny Basic. Instead, it takes inspiration from Tiny Basic and extends or modifies certain features to better suit the requirements and capabilities designed specifically to be executed in [[Age of Joy]].

With AGEBasic the player can develop it's own functions to run in the simulation. Allows to control parts of the game that there aren't available from the [[YAML]] configuration or the [[Visual configuration]].


> [!warning] the contents of this document applies to [[Age of Joy]] version 0.4-RC04 or superior.

## AGEBasic program storage

The main storage for [[Documents/AGEBasic]] programs is `/sdcard/Android/data/com.curif.AgeOfJoy/AGEBasic` . AGEBasic programs must to end with the `.bas` prefix, like `mixcabinets.bas` or `changecontrols.bas`.

## Variables

AGEBasic supports `numbers` (double precision) and `strings`.
A variable name can contain letters a numbers only. AGEBasic isn't case sensitive, the variable `A` is the same as `a`. 
`booleans` are not variable type, but anything different than `0` is considered `true`.

## Numbered lines

Each line of code should be numbered and be in ascending order.

## Sentences

* `LET`: assign a value to a variable, ex: `LET a=10`
* `LETS`: assign multiple values, ex: `LETS a,b=10,20`
* `REM`: a comment, ex: `REM this is a comment`. It's the only way to register comments in the program.
* `END`: finish the program
* `IF/THEN`: conditional, ELSE is not allowed. Ex: `IF x=1 THEN LET a=2`
* `GOTO`: to jump to a line number. Ex: `GOTO 50`
* `GOSUB`: to jump to a line, and to back using `RETURN`. Ex: `GOSUB 5000`
* `RETURN`: jump back to the next line after the `GOSUB`
* `CALL`: to call a function discarding the result. Ex: `CALL CabRoomReplace(0, "pacman")`
* `FOR/TO/NEXT/STEP`: to create loops. Ex: `for x=0 to 10 step 2 ... next x`
	* Initial, end  and step values can be expressions.
	* Initial value is computed at start of the cycle.
	* The end value is computed during the `NEXT` sentence execution.
	* The `NEXT` sentence evaluates if the cycle should repeat. At least one cycle is executed always.

## Functions


Functions can receive parameters. Parameters must be enclosed.

### Math

- `ABS`, `COS`, `SIN`, `TAN`, `MOD`
- `MAX`, `MIN`: of two numbers, Ex: `LET a = max(10,20)` then `a` is 20
- `RND`: a random between two numbers. `rnd(2,10)` could be `8`.
- `NOT`: The inverse of the boolean expression. Ex: `if NOT(0) then goto 100`

### String

- `LEN`, `UCASE`, `LCASE`, 
- `SUBSTR`: Ex: `susbtr("abc", 1, 2) ` is "bc", starting in 1 and getting two characters.
- `TRIM`, `LTRIM`, `RTRIM`.
- `STR`: Ex: `str(10)` is `"10"`

### Introspection

- `exists(string)`: to know if a variable is defined, returns 1 or 0 (true or false).

### Room related

To get information about rooms

- `RoomName()`: The name of the room where the player is.
- `RoomCount()`: How many Rooms are in the game.
- `RoomGet(number)`: Get the name of the room. Ex: `LET name, desc = RoomGet(0)` to get the name and the description of the Room number zero.
- `RoomGetName(number)`: get the name of the room.
- `RoomGetDesc(number)`: to get the description.

### Cabinets related

Applies to cabinets deployed in the room.

- `CabRoomCount()`: how many cabinets are in the room
- `CabRoomGetName(number)`: get the cabinet name by its index in the room.
- `CabRoomReplace(number, cabinet name)`: replace a cabinet by another.

Applies to cabinet database (`registry.yaml`) and the [[Cabinets database storage]]. 

- `CabDbCount()`: how many cabinets registered in the storage
- `CabDbCountInRoom(string)`: how many cabinets are assigned to one particular room. Ex: `LET count = CabDbCountInRoom("Room001")` 
- `CabDBGetName(number)`: get a cabinet name using the position in the storage. Ex: `CabDBGetName(30)` could return "pacman"
- `CabDBGetAssigned(room, cabinetIndex)`: returns the cabinet name assigned to a position in a room.
- `CabDBDelete(currentRoomName, cabinetIndex)`: delete the cabinet assignment to a room in the database. 
- `CabDBAdd(room, cabinetIndex, newCabinetName)`: to add a new room/position/cabinet in the database, if the position is taken the program will fail.
- `CabDBAssign(room, cabinetIndex, newCabinetName)`: assign a cabinet to a existent position in DB.

Functions that only applies to a cabinet. In programs related with the cabinet, and packed inside a [[Cabinet Asset]].

- `CabPartsCount()`: return the cabinet's parts count. Returns -1 when error (for example if the programmer tries to use it in other place than in a cabinet's asset)
- `CabPartsName(idx)`: given a part number (starting in cero), return the name of the part, eg: "joystick". Returns `""` when error (not in a cabinet's asset, or the part number not exists)
- `CabPartsPosition(name)`: given the name of a part return it's position. Returns `-1` when error (not in a cabinet's asset, or a part doesn't exists with the provider name)
- `CabPartsEnable(idx, enable)`: given a part number and a boolean (remember booleans are numbers, `true` is anything different to cero), will disable or enable it. When a part is disabled you can't see it in VR. Returns `-1` on error.

Read more about cabinet's programs in [[AGEBasic in cabinets]].

## Debug mode

The AGEBasic developer has the option to enable Debug Mode within a program or a setup, such as in a programming YAML subdocument within a cabinet's configuration.

Once DebugMode is engaged, [[Age of Joy]] will generate a report upon completion, detailing the most recent error (both compilation and runtime errors), along with the final program status, encompassing variable specifics like names, types, and values.

- `DebugMode(true/false)`

Eg:

```basic
1000 let i = 100
1010 call DebugMode(1) 'activate the debug mode
1020 let ERROR = "some error message to see in debug"
```

Result:

```txt
Program: myprogram.bas
PROGRAM STATUS ---
PROGRAM: myprogram.bas
Last line parsed: 1020 executed: 3
vars: 
I: 100 [Number]
ERROR: some error message to see in debug [string]
---
```

You can find the result file in the folder: `/sdcard/Android/data/com.curif.AgeOfJoy/AGEBasic`

The name of the file sould be:  `myprogram.bas.debug` (the file name of the program with the `.debug` suffix)

---

If you want to use ChatGPT to ask for programs, just follow this [[AGEBasic prompt for ChatGPT]]

[[AGEBasic Examples]]
