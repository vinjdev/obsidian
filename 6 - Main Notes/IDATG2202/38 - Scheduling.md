16/09/24 17:54
Fag: [[IDATG2102]]
Tags: [[NTNU]]
___

# 38 - Scheduling
assumptions we have to break
1. runs for same amount time
2. arrives at same time
3. once started, runs to completion
4. all jobs use CPU
5. run time is known

turnaround tid fra den vil bruke cpu til den er ferdig

Convoy effekten - shortest job first - Minst turnaround tid

scheduler py
regner ut hva gjennomsnitlig respons tid

hvis det tar 2 sekund
0+2+4+6 skal delses på 4 = 3
dette er hva snitt respons tid er


*round robin* fordeler tiden til alle processene

Mutlti level feedback queue er Round robin, men som prioritets kø
- den med høyest pri kjører
- vis lik, så round robin

Gang og co schedluling


# Review

1. Too many interactive jobs will in total take up to much of the CPU time. effectivly starving it







# Referanse
