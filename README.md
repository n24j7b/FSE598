java c
FSE598 Project   1
(Assignment   1: 50 points and Assignment 2: 50   Points)
Computational Thinking and VIPLE   Programming
IntroductionThe   aim   of   this project   is to make   sure that   you   have   read   the   lectures   and   have   understood   the   concepts covered   in   the   lectures,   including   the   computer   organization,   computational   thinking   concepts,   VIPLE   basics,   and   programming   concepts   behind   VIPLE.   By   the   end   of the   project,   you   should   have   a   good   understanding   of the   concepts   and   have   applied   these   concepts   in   developing   operational   programs.   The   assignment is an individual assignment. No collaboration is allowed. All students must submit   independently developed applications. You cannot repeat the   examples given   in   the   book   or   lecture   slides.   You can follow the examples, but significant changes must be made.
Practice Exercises and Preparation (No submission required)
1.       Read   lectures   and   the   VIPLE   Tutorial   athttps://venus.sod.asu.edu/VIPLE/IntroductionVIPLE.pdf
in English. Alternatively, you can read the Chinese version:
https://www.public.asu.edu/~ychen10/book/IntroCS2edindex.html
2.       Understanding maze navigation algorithm by program your first maze program in VIPLE Web2D   Simulator:https://venus.sod.asu.edu/VIPLE/Web2DSimulator/indexcn.html
3.       You can start to implement your   algorithm here:   
What   kind   of   algorithm   does   this   code   implement?
Left-wall following?                Right-wall following?          One-distance   greedy algorithm?          Local best?
4.       Download   and   install   VIPLE:https://venus.sod.asu.edu/VIPLE/   
The Installation version is   at:
https://venus.sod.asu.edu/VIPLE/Install/publish.htm
It may require ASU VPN in order to run the installation program.   In this case, you use the   download   version   at:
https://venus.sod.asu.edu/VIPLE/Release.zip
5.       Follow the tutorial to run the drive-by-wire program using the Unity simulator 2. Note, in   order to   start you program, you need to:
1)      After you started to Run “Unity   Simulator 2”, you need to go back to VIPLE, to   click   the
"Start" button", the green arrow. Then, the Control window will appear,   showing   that   the robot is running.
2)      When you are controlling the robot using the keyboard, you must keep the Control   window   (RunWindow) on the top in active mode, not in background.   
6.       Basic Racecar Implementation in   C#
The purpose of   this exercise is to program the TORCS racecar to drive autonomously through   the
racetrack. The goal is to use minimum amount of   time to complete   the racetrack.   You   must   read   the
TORCS website （http://torcs.sourceforge.net/）   and the lecture PPTs to learn more and to write more   efficient code than the one   given.
Step   1. Implement the following VIPLE   code:   
For the Code Activity, you can enter the   following   code:using   System;using   System.Collections.Generic;   [Serializable]public class TorcsController   : CodeUtilities.CodeBase   {public TorcsController(){          }          // To execute your code,   you   must   override   the   Execute   method.   public override void Execute(){// The values are passed in as an   object, need   to   unbox   it.var inputDictionary = Input as Dictionary;                      // Returning   a   dictionary   allows us   toreference the values by name.var toReturn = new Dictionary()   {{"accel", 0.3},      {"brake", 0.0},   {"gear", 2},// Need to cast these values to doubles, as they are passed in   as   objects.{"steer", (double)inputDictionary["angle"] - (double)inputDictionary["trackPos"]   * 0.5},{"clutch", 0.2}};                      Output   = toReturn;}   }
Step 2. Configure the Controller and devices   as   follows.
Step 3:   Start   simulator
When you start TORCS in VIPLE for the first time,   it   should   link   you   to   the   TORCS   download   site.   If   it   does   not, you   can   goto   TORCS   official   site   to   download   it,   or   directly   goto:
http://torcs.sourceforge.net/index.php?name=Sectionsop=viewarticleartid=3#linux-src-all-win
Install TORCS into your VIPLE directory at: Documents\VIPLE_Files\TORCS\wtorcs.exe
Step 4. Choose   Race
Once TORCS   Simulator is running, choose Race   
Step 5. Choose Basic   Quick   Race   
Step 6. Choose New   Race   
Step 7. Now, start your VIPLE program by clicking the green triangle:   
The racecar should start now. Observe the race and   answer   the   following   questions:
Is the racecar running perfectly? How much time does it take to complete the racetrack? Can   you   improve   the   time   if   you   were   driving   the   racecar?
7.       Improve race formula
Double click the “Code Activity”, as shown in the   following   figure.   
The race is determined the parameters, including accel, brake, gear, steer,   angle, trackPos,   and   clutch.   Try   to modify these parameter values by trial-and-error to improve the race performance.
Notice that constant values are used for all the parameters, including   acceleration, brake, gear,   and   clutch.   To improve the race performance, you may want to give different values in   different   situations.   For
example, accelerate more at代 写FSE598 Project 1 Computational Thinking and VIPLE ProgrammingPython
代做程序编程语言 straight track, increase brake at   curve track,   etc.
8.       Racecar Implementation in Python
Implement the race activity as a Python   Code Activity.
Project Assignments: Advanced VIPLE Programming (Submission Required)
The project consists of   two assignments. Each assignment has a   different   due   date.
Assignment   1 (50 points)
Before   you   start   this   part   of the   assignment,   you   need   to   follow   the   lecture   slides   and   the   tutorial   in   the   Practice Exercise section in this document to get   started with programming   in VIPLE workflow.
Q1      You are given the circuit of   a two-bit adder in   the   following   figure:                                                                                                                [25 points]
Two-bit adder
1.1      Use a custom activity to implement each   type   of   gate.                                                                    [5]
1.2      Use a custom activity to implement   one-bit   adder.   Then, implement   the   two-bit   adder   in   VIPLE   Main   activity or as a custom activity using the   one-bit   adder   as   components.                                            [10]
1.3      Automated   Testing: Use   a   Counter   custom   activity   (module) to   generate the   decimal number   0,   1,   2,   3,   4,   …   ,   14,   15,   and   use   another   module   to   convert   the   decimal   numbers   into   binary   number   as   test input to the two-bit adder.                                                                        [10]
Q2      Robot maze navigation using Unity   Simulator 2.                                                                                                                                                                                                       [25 points]
2.1      Follow the   lecture to   implement the basic   right-wall-following program.   You   may   need   to   adjust   the parameter values,                                           [15]
2.2      Implement   an   enhanced   (modified)   right-wall-following   program   that   uses   less   turns   or   travels   a   shorter   distance to the   exit point. For   example, you   can   detect   the   cul-de-sac   (dead   end   road).      In   the   given   right-wall-following   program,   the   robot   will   make   a   90   degree   turn,   move   forward,   and   then   make   another   90   degree   turn   in   a   cul-de-sac.   In   the   enhanced program,   you   can   use   more   sensors   to   make the robot turn   180   degrees   after detecting that   there   are no   ways   on   both   sides,   as   shown   in   the   following figure.                                                            [10]You   could   make   other   enhancement,   as   long   as   your   algorithm   can   use   fewer   turns. Note,   using   the   left-wall-following   algorithm   is not   an   enhancement in   general   and is not   acceptable.   It   enhances   the   performance for this maze but can perform. worse in a different maze.
Submission: Adder2.viple that contains all the code for question   1   and   code   for 2.1   and   the   code   for   2.2,   including following VIPLE codes for Assignment   1:
•         Adder2.viple


•         Maze1.viple
•         Maze2.viple
Put all the document and codes in all   questions   in   one   folder,   zip   the   folder,   and   submit   the   zip   file.
Assignment 2 (50   points)Q3.   Based on the   practice exercise in in the first   part of   this document, and follow Module   1, Unit 2, Lecture
5 to implement an advanced racecar program.                                                                   [50 points]
3.1          Submit the complete VIPLE   program (it can include C#   and/or Python program   as   code   activity) that   can be executed on TA’s   computer.
3.2          A screenshot that includes the race performance (time in   seconds).
Grading: This project question is a competition and will be graded to your relative performance in the   class.
•         Top 10% (using least   time   to complete   race) among   the submitted   programs:   100% =   40   points.
•       Next   10%   (top   11% –   20%)   among the   submitted programs:   95%   =   38 points.
•       Next   10% (top   21% –   30%)   among   the   submitted programs:   90%   =   36 points.
•       Next   10% (top   31% –   40%)   among   the   submitted programs:   85%   =   34 points.
•       Next   10% (top   41% –   50%)   among   the   submitted programs:   80%   =   32 points.
•       Next   10% (top   51% –   60%)   among   the   submitted programs:   75%   =   30 points.
•       Next   10% (top   61% –   70%)   among   the   submitted programs:   72.5%   =   29 points.
•       Next   10%   (top 71% –   80%)   among   the   submitted programs:   70%   =   28 points.
•       Next   10%   (top   81% – 90%)   among   the   submitted programs:   67.5%   =   27 points.
•       Next   10%   (top   91% –   100%) among   the   submitted programs:   65%   =   26 points.
Submit the following VIPLE codes for   Assignment 2:
•         Race.vipl   and   screenshot.
Put all the document and codes in all   questions   in   one   folder,   zip   the   folder,   and   submit   the   zip   file.
   





         
加QQ：99515681  WX：codinghelp
