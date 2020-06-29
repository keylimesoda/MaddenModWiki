# PSAL CODES

**code**|**code name**|**val1 type**|**val2 type**|**val3 type**|**Code Description**
:-----:|:-----:|:-----:|:-----:|:-----:|:-----:
1|Run to End Zone|na|na|na| 
2|Chase Ball|na|na|na| 
3|Move Direction for Distance|distance|direction|speed|The player will move given distance in the given direction at the given percentage of his maximum speed.
4|Move Direction for Distance Constant|distance|direction|speed|The player will move like MoveDirDist but using constants for maximum speed not Stats.
5|Face Direction| | | | 
7|QB Scramble| | | | 
8|Receiver Run Route|distance|direction|speed|Wide Receiver Route running assignment
9|Receiver Cut Move|right/left|cut type|na|The player will perform a cutting animation to the left or right.Use during receiver routes if wanted.
10|Receiver Get Open| | | | 
11|Pitch Ball| | | | 
12|Option Hand Off| | | | 
13|Receive Hand Off|distance|direction|speed|The player will move like MoveDirDistConst but the receive ball anim will trigger when needed.Use to receive a handoff from QB
14|PassBlock|time|pass block type|?|The player will perform pass blocking.Do this assignment AND ONLY THIS ASSIGNMENT for players needing to block on passes. Enter 0 for infinite block time. DO NOT TRY TO MOVE PLAYERS TO POSITION THEM FOR THE PLAY UNLESS THEY ARE PULLING!!!!!
15|RunBlock|time|na|na|The player will perform run blocking.Do this assignment AND ONLY THIS ASSIGNMENT for players needing to block on running plays.Enter 0 for infinite block time. DO NOT TRY TO POSITION BLOCKERS BY MOVING THEM!!!!!.
16|Kickoff| | | | 
18|LeadBlock|type of block|hole| | 
19|Man Coverage| | | | 
20|"Cloud| Hard| Soft Flat"|side of field|type
21|"Mid| 3 Rec| Hook"|type|direction
22|"Curl| Seam| Quarter Flat"|side of field|type
23|Deep Zone|area|alignment?|na| 
24|Pass Rush|distance|direction|speed| 
25|Delay|time|na|na|The player Delay for the amount of time given in param 1 (7.0 max)
26|Initial Anim|stance type|direction|?|The player will perform an initial anim from a stance. Param 1 determines Type: 0=Shuffle 1=Backstep(Dir Used) 2=Hop Step 3=Counter Step 4=3PtPull(Dir Used) 5=WR Start 6=RecPitch(Dir Used). Use as 1st Assignment if necessary. Param 2 determines Dir to turn while animating (not always used)
32|Receive Pitch|distance|direction|speed|The player will move like MoveDirDistConst but the player will use a Receive Pitch animation.Use to receive a pitch from QB
34|QB Spy|time?|na|na| 
35|Head Turn Run Route| | | | 
36|Option Route|option 1|option 2|option 3|The receiver will choose from up to 3 different routes
37|Option Route Extra Info|coverage 1|coverage 2|coverage 2|Coverages for option routes (Option Route must be previous assignment).  A DEFAULT ROUTE IS REQUIRED.
41|Rush QB|distance|direction|speed| 
42|Hand Off Fake| | | | 
43|Option Follow|?|?|hole?|This assignment is for a potential pitch receiver.The player will follow behind the player in Option Run so that he can catch the ball if it is pitched to him.
45|Auto Motion|x offset|y offset|speed|This will start the player in the auto motion assignment. The Offset Y should be set to -15 - 0 (negative)for automotion plays and 0 - 15 (positive) for automotion strafe plays
46|Auto Motion Snap|na|na|na| 
47|Auto Motion Defense|x offset|y offset|speed| 
48|Player offset|x offset|y offset|na?|Moves the player to an offset.  Not a pre-snap motion
57|Tells Defender to linup vs formation|?|?|?| 
58|Predetermined Animation|default side anim|flipped side anim|player|Used in runs and play action.  Val1 is animation to default side and Val2 is the animation when the play is flipped.
255|End of PSAL|na|na|na| 
 | | | | | 

### Val Type Definitions
**distance:**  0 to 32, in 0.125 yard increments

**direction:** 0 to 127, in 2.8125 degree increments.  Counted CCW from 0 (facing east).

**speed:** 0 to 255, percentage of top speed, in .39 percent increments

**right/left**:  1-cut right, 2-cut left

**cut type**:  
1 = 45
2 = 90
3 = 22
4 = 67
5 = Curl
7 = HitchComback
8 = HitchGoIn
9 = HitchGoOut
10 = OutAndUp
11 = Smash
13 = WRScrn
14 = 90Inside
15 = HitchCombackInside
16 = 180Partial
17 = SmashQuick
18 = Hitch
19 = Normal
20 = ShakeCut
21 = StutterCut
22 = HingeCut
23 = PostCorner
24 = Zig
25 = StutterStreak
26 = WR Swing
28 = Sluggo
29 = Out n Up

**time**:  0 to 255, in .027 second increments

**pass block type**:  0=None, 1=Force Cut Block, 2=Protect Receiver, 3=Cut Block AND Protect Receiver

**hole**:  gap to target with lead block (0-9).  -1 to use play value (PLRD-> hole)

**stance type**:  
0 = Shuffle
1 = Backstep(direction used)
2 = Hop Step
3 = Counter Step
4 = 3PtPull(direction used)
5 = WR Start
6 = RecPitch


**(code 20) side of field**:  9 = Defenses Right, 10 = Defenses Left

**(code 20) type**:  0 = Cloud Flat, 1 = Hard Flat, 2 = Soft Squat

**(code 21) type**:  0 = Mid Read, 1 = 3 Rec Hook, 2 = Hook Curl, (Defenses) Right, 3 = Hook Curl, (Defenses) Left, 4 = Vert Hook, (Defenses) Right, 5 = Vert Hook, (Defenses) Left

**(code 22) side of field**:  11 = Defenses Right, 12 = Defenses Left

**(code 22) type**:  0 = Curl Flat, 1 = Seam Flat, 2 = Quarter Flat

**(code 23) area**:  
0 = Half Defenses Right
1 = Half Defenses Left
2 = Third Defenses Right
3 = Third Middle
4 = Third Defenses Left
5 = Quarter Outside Defenses Right
6 = Quarter Inside Defenses Right
7 = Quarter Outside Defenses Left
8 = Quarter Inside Defenses Left

**(code 23) alignment**:  0 = Normal Deep Quarter Alignment, 1 = Palms, 2 = Show Press

*NOTE*:  Option routes provide up to three different routes that the receiver may run, based on which coverage is seen.  

Code 36 lays out all the route choices (1-3).  Code 37 lays out which coverages trigger which option.
  
**(code 36) option1, option2, option3**: 
0 = Curl Lt
1 = Curl Rt
2 = Post Rt
3 = Corner Lt
5 = Slant Rt
6 = Fade/Streak Lt
7 = Slant Lt (not used)
8 = Fade/Streak Rt
9 = In/Out Rt
10 = In/Out Lt
11 = Fade Lt (not used)
12 = Hitch Lt
13 = Hitch Rt
15 = 180 Partial
16 = 180 Partial
17 = Drag Rt
18 = Drag Lt
19 = Hitch Rt
20 = Hitch Lt

**(code 37) coverage1, coverage2, coverage3**:  Add the numbers to indicate to which coverages the option route applies.  So for example, if you want the receiver to run option1 when they see (Man 0, Man 1, Man 2, or Man 3) then coverage1 = 1+2+4+8 = 15

0 = Default (Required for at least one route)
1 = Man (0 Deep)
2 = Man (1 Deep)
4 = Man (2 Deep)
8 = Man (3 Deep and up)
16 = Cover 2
32 = Cover 3
64 = Cover 4
128 = Hot Blitz

**x offset**:  -99 to 99, from left to right, in 1/6th yard increments

**y offset**:  -33 to 30, from line of scrimmage, in 1/6th yard increments
