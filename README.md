MVI A,40H
OUT 81H

MVI A,79H
OUT 81H

MVI A,37H
OUT 81H

; Transmission
MVI A,41H

WAIT: IN 81H
      ANI 01H
      JZ WAIT

      MVI A,41H
      OUT 80H

; Reception
WAIT1: IN 81H
       ANI 02H
       JZ WAIT1

       IN 80H
       STA 2500H

HLT
Output 
Transmitted Character : A
Received Character    : A

Memory:
2500H = 41H
