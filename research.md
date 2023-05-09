# Researching Commands

`grep`

The command `grep` is a command-line utility which is used to search for text paterns in files. 
This command can be used to look into one or multiple files.
The layout of this command can be simplified to `grep [OPTION]... PATTERN [FILE]...`

* Option in this instance is how `grep` will run
  > We'll look into some of the options that can be used below.

* Pattern refers to the thing you are searching for, may it be a word in a file or part of a file name.

* File is pretty self explanitroy, as it referes to the file or files you want `grep` to search in.

## Options for `grep`

1) -v

> prints only names of files containing **no** match\

**Ex1:**

```
$ grep -v "e" technical/911report/chapter-1.txt

"WE HAVE SOME PLANES"


INSIDE THE FOUR FLIGHTS

IMPROVISING A HOMELAND DEFENSE

NEADS: On its way towards Washington?


NEADS: Okay.

NATIONAL CRISIS MANAGEMENT


What if?
```
> (I cut outa lot of the extra spaces between lines to make it more readable) 

As you can see this returned lines that did have the letter e but in those lines the e was capitalilzed, therefore it does not count as the same thing that -v is avoiding. But at the end we do see a line that does not have the letter e in it, this is because the purpose of -v is to return the lines that do not have the letter e (lowercase) in them. 

**Ex2:**
```
$ grep -v e technical/plos/*.txt

technical/plos/pmed.0020274.txt:
technical/plos/pmed.0020274.txt:        RNA.
technical/plos/pmed.0020274.txt:
technical/plos/pmed.0020274.txt:
technical/plos/pmed.0020274.txt:
technical/plos/pmed.0020275.txt:
technical/plos/pmed.0020275.txt:
technical/plos/pmed.0020275.txt:
technical/plos/pmed.0020275.txt:
technical/plos/pmed.0020275.txt:
technical/plos/pmed.0020275.txt:        which also has implications for policy and planning.
technical/plos/pmed.0020275.txt:
technical/plos/pmed.0020275.txt:
technical/plos/pmed.0020275.txt:
technical/plos/pmed.0020278.txt:
technical/plos/pmed.0020278.txt:
technical/plos/pmed.0020278.txt:
technical/plos/pmed.0020278.txt:
technical/plos/pmed.0020278.txt:
technical/plos/pmed.0020278.txt:        cardiovascular risk [1].
technical/plos/pmed.0020278.txt:        individuals [4].
technical/plos/pmed.0020278.txt:
technical/plos/pmed.0020278.txt:
technical/plos/pmed.0020278.txt:
technical/plos/pmed.0020281.txt:
```

> for this one I cut out a lot of the output to focus on some specific things.

**Woah** That's a lot of lines! 
That's because now we are looking through all the .txt files withing the directory provided (`technical/plos/`)
We can see that it looks through the different files that end with .txt in plos (by looking at the ending numbers) and returns the lines that do not contain the letter e. Also if we look at what I typed into the terminal, I did put the e in quotes.

2) -n

>  prints the line number with output lines

**Ex1: **

```
$ grep -n Alcohol technical/government/Alcohol_Problems/*.txt
technical/government/Alcohol_Problems/DraftRecom-PDF.txt:522:become research priorities. Alcohol and injury, as well as brief
technical/government/Alcohol_Problems/Session2-PDF.txt:6:Identifying ED Patients with Alcohol Problems
technical/government/Alcohol_Problems/Session2-PDF.txt:21:Alcohol problems defined
technical/government/Alcohol_Problems/Session2-PDF.txt:22:Alcohol problems designate a spectrum from risk behavior to
technical/government/Alcohol_Problems/Session2-PDF.txt:48:Institute on Alcohol Abuse and Alcoholism (NIAAA) defines at-risk
technical/government/Alcohol_Problems/Session2-PDF.txt:172:The MAST (Michigan Alcohol-Screening Test), developed in 1971 as
technical/government/Alcohol_Problems/Session2-PDF.txt:180:SAAST (Self-Administered Alcoholism Screening Test) was
technical/government/Alcohol_Problems/Session2-PDF.txt:188:drinkers. WHO developed the AUDIT (Alcohol Use Disorder
technical/government/Alcohol_Problems/Session2-PDF.txt:207:Rapid Alcohol Assessment Screen (RAPS4). Cherpitel screened an ED
technical/government/Alcohol_Problems/Session2-PDF.txt:268:Alcohol concentration
technical/government/Alcohol_Problems/Session2-PDF.txt:438:4. National Institute on Alcohol Abuse and Alcoholism. The
technical/government/Alcohol_Problems/Session2-PDF.txt:439:Physician's Guide to Helping Patients with Alcohol Problems.
technical/government/Alcohol_Problems/Session2-PDF.txt:443:the CAGE, the Brief Michigan Alcoholism Screening Test, and the
technical/government/Alcohol_Problems/Session2-PDF.txt:444:Alcohol Use Disorders Identification Test in screening trauma
technical/government/Alcohol_Problems/Session2-PDF.txt:454:regions of the country. Alcohol Clin Exp Res 1997;21:1391-7.
technical/government/Alcohol_Problems/Session2-PDF.txt:470:Clifford P. Alcohol use among subcritically injured emergency
technical/government/Alcohol_Problems/Session2-PDF.txt:473:alcohol-related problems in general practice. J Stud Alcohol
technical/government/Alcohol_Problems/Session2-PDF.txt:476:with the Alcohol Use Disorders Identification Test (AUDIT) in an
technical/government/Alcohol_Problems/Session2-PDF.txt:484:screening in an ambulatory care setting. J Stud Alcohol
technical/government/Alcohol_Problems/Session2-PDF.txt:487:screening questionnaire. Alcohol 1991;26:81-91.
technical/government/Alcohol_Problems/Session2-PDF.txt:502:version of the Michigan Alcoholism Screening Test. Am J Psychiatry
technical/government/Alcohol_Problems/Session2-PDF.txt:504:27. Selzer M. The Michigan Alcoholism Screening Test: the quest
technical/government/Alcohol_Problems/Session2-PDF.txt:508:Short Michigan Alcoholism Screening Test (SMAST). J Stud Alcohol
technical/government/Alcohol_Problems/Session2-PDF.txt:511:analysis of the Self-Administered Alcoholism Screening Test.
technical/government/Alcohol_Problems/Session2-PDF.txt:512:Alcohol Clin Exp Res 1987;11:269-73.
technical/government/Alcohol_Problems/Session2-PDF.txt:513:30. Davis L, Jr., Morse R. Self-Administered Alcoholism
technical/government/Alcohol_Problems/Session2-PDF.txt:515:computer-administered formats. Alcohol Clin Exp Res
technical/government/Alcohol_Problems/Session2-PDF.txt:517:31. Saunders J, Aasland O, Amundsen A, Grant M. Alcohol
technical/government/Alcohol_Problems/Session2-PDF.txt:520:With Harmful Alcohol Consumption, I. Addiction 1993;88:349-62.
technical/government/Alcohol_Problems/Session2-PDF.txt:522:Development of the Alcohol Use Disorders Identification Test
technical/government/Alcohol_Problems/Session2-PDF.txt:525:pregnancy risk-drinking. Alcohol Clin Exp Res 1994;18:1156-61.
technical/government/Alcohol_Problems/Session2-PDF.txt:530:drinking in the emergency room: the RAPS4. Rapid Alcohol Problems
technical/government/Alcohol_Problems/Session2-PDF.txt:531:Screen. J Stud Alcohol 2000;61:447-9.
technical/government/Alcohol_Problems/Session2-PDF.txt:534:in an emergency room population. J Stud Alcohol 1998;59:420-6.
technical/government/Alcohol_Problems/Session2-PDF.txt:536:the CAGE, the Brief Michigan Alcohol Screening Test, and the
technical/government/Alcohol_Problems/Session2-PDF.txt:537:Alcohol Use Disorders Identification Test in screening trauma
technical/government/Alcohol_Problems/Session2-PDF.txt:544:dependence in the emergency room. Alcohol Clin Exp Res
technical/government/Alcohol_Problems/Session2-PDF.txt:548:Alcohol 1995;56:695-700.
technical/government/Alcohol_Problems/Session2-PDF.txt:549:41. Bradley KA, Boyd-Wickizer J, Powell SH, Burman ML. Alcohol
technical/government/Alcohol_Problems/Session2-PDF.txt:552:Alcoholism. Criteria for the diagnosis of alcoholism. Am J
technical/government/Alcohol_Problems/Session2-PDF.txt:565:instruments. Drug Alcohol Depend 1995;40:151-8.
technical/government/Alcohol_Problems/Session2-PDF.txt:569:transferase (GGT), and mean corpuscular volume (MCV). Alcohol Clin
technical/government/Alcohol_Problems/Session2-PDF.txt:574:Alcohol. 1998;33:304-9.
technical/government/Alcohol_Problems/Session2-PDF.txt:578:Alcohol Clin Exp Res 1998;22:892-6.
technical/government/Alcohol_Problems/Session2-PDF.txt:613:Alcoholism screening in the elderly. J Am Geriatr Soc
technical/government/Alcohol_Problems/Session2-PDF.txt:615:62. Bercsi S, Brickner P, Saha D. Alcohol use and abuse in the
technical/government/Alcohol_Problems/Session2-PDF.txt:617:Alcohol Depend 1993;33:139-49.
technical/government/Alcohol_Problems/Session2-PDF.txt:621:64. Fink A, Hays RD, Moore AA, Beck JC. Alcohol-related
technical/government/Alcohol_Problems/Session3-PDF.txt:6:Intervening with Alcohol Problems
technical/government/Alcohol_Problems/Session3-PDF.txt:256:additional treatment or self-help groups like Alcoholics Anonymous.
technical/government/Alcohol_Problems/Session3-PDF.txt:392:admission and triage system of the emergency settings. Alcohol
technical/government/Alcohol_Problems/Session3-PDF.txt:421:day treatment. Self-help groups like Alcoholics Anonymous, Women
technical/government/Alcohol_Problems/Session3-PDF.txt:559:4. Maio RF, Waller PF, Blow FC, Hill EM, Singer KM. Alcohol
technical/government/Alcohol_Problems/Session3-PDF.txt:562:5. Whiteman PJ, Hoffman RS, Goldfrank LR. Alcoholism in the
technical/government/Alcohol_Problems/Session3-PDF.txt:582:10. Gentilello LM, Donovan DM, Dunn CW, Rivara FP. Alcohol
technical/government/Alcohol_Problems/Session3-PDF.txt:585:11. Lowenstein SR, Weissberg MP, Terry D. Alcohol intoxication,
technical/government/Alcohol_Problems/Session3-PDF.txt:608:analysis of injury by cause among casualty. Alcohol Clin Exp
technical/government/Alcohol_Problems/Session3-PDF.txt:615:18. Gentilello LM, Rivara FP, Donovan DM, et al. Alcohol
technical/government/Alcohol_Problems/Session3-PDF.txt:659:department. Alcohol Alcohol
technical/government/Alcohol_Problems/Session3-PDF.txt:664:abuse consultation team in a trauma center. J Stud Alcohol
technical/government/Alcohol_Problems/Session3-PDF.txt:667:28. Hemphill C, Bennett BE, Watkins, BL. Alcoholism: the
technical/government/Alcohol_Problems/Session3-PDF.txt:678:review of randomized controlled trials. Alcohol Alcohol
technical/government/Alcohol_Problems/Session3-PDF.txt:693:36. Reyna TM, Hollis MW, Hulsebus RC. Alcohol-related trauma:
technical/government/Alcohol_Problems/Session3-PDF.txt:695:37. Miller WR. Alcoholism: toward a better disease model.
technical/government/Alcohol_Problems/Session3-PDF.txt:700:Mental Health Services Administration. Alcohol and Other Drug
technical/government/Alcohol_Problems/Session3-PDF.txt:704:40. Soderstrom CA, Dailey JT, Kerns TJ. Alcohol and other
technical/government/Alcohol_Problems/Session3-PDF.txt:723:for excessive drinkers: the need for caution. Alcohol Alcohol
technical/government/Alcohol_Problems/Session3-PDF.txt:921:and lifestyle change. In: Howard G, editor. Issues in Alcohol Use
technical/government/Alcohol_Problems/Session3-PDF.txt:957:Intervening with Alcohol Problems in
technical/government/Alcohol_Problems/Session3-PDF.txt:1138:of alcohol-related emergency room admission. J Stud Alcohol
technical/government/Alcohol_Problems/Session3-PDF.txt:1140:4. Cherpitel CJ. Alcohol, Injury, and risk-taking behavior:
technical/government/Alcohol_Problems/Session3-PDF.txt:1141:data from a national sample. Alcohol Clin Exp Res
technical/government/Alcohol_Problems/Session3-PDF.txt:1143:5. Dewey KE. Alcohol related attendances at the accident and
technical/government/Alcohol_Problems/Session3-PDF.txt:1145:6. Zink BJ, Maio RF. Alcohol use and trauma. Acad Emerg Med
technical/government/Alcohol_Problems/Session3-PDF.txt:1147:7. Maio RF. Alcohol and injury in the emergency department:
technical/government/Alcohol_Problems/Session3-PDF.txt:1164:of Alcohol-related Problems. Report on Phase II: A Randomized
technical/government/Alcohol_Problems/Session3-PDF.txt:1177:department. Alcohol Alcohol
technical/government/Alcohol_Problems/Session3-PDF.txt:1184:controlled trials. Alcohol Alcohol 1999;34:609-21.
technical/government/Alcohol_Problems/Session3-PDF.txt:1188:CW, et al. Alcohol interventions in a trauma center as a
technical/government/Alcohol_Problems/Session3-PDF.txt:1252:Alcoholics Anonymous session. Consequently, he questioned how
technical/government/Alcohol_Problems/Session4-PDF.txt:250:Treatment" theme of the National Treatment Plan.36 Alcohol problems
technical/government/Alcohol_Problems/Session4-PDF.txt:292:The opposite may be the case. Alcohol-related medical problems,
technical/government/Alcohol_Problems/Session4-PDF.txt:302:Alcohol-related problems occur at lower rates, but in much
technical/government/Alcohol_Problems/Session4-PDF.txt:355:Alcohol use among emergency department patients is not likely a
technical/government/Alcohol_Problems/Session4-PDF.txt:479:Regulations (42 C.F.R. Part 2), Confidentiality of Alcohol and Drug
technical/government/Alcohol_Problems/Session4-PDF.txt:558:treatment. Am J Drug Alcohol Abuse 1996;22:233-46.
technical/government/Alcohol_Problems/Session4-PDF.txt:563:3. Gentilello LM, Rivara FP, Donovan, DM, et al. Alcohol
technical/government/Alcohol_Problems/Session4-PDF.txt:579:hospitalized patients. Am J Drug Alcohol Abuse 1997;23:1-13.
technical/government/Alcohol_Problems/Session4-PDF.txt:587:transition from research into practice. J Stud Alcohol 1994 (12
technical/government/Alcohol_Problems/Session4-PDF.txt:590:Alcohol Health Res World 1989;15:219-20.
technical/government/Alcohol_Problems/Session4-PDF.txt:611:20. Selzer ML. The Michigan Alcoholism Screening Test: the
technical/government/Alcohol_Problems/Session4-PDF.txt:614:21. Krishel S, Richards CF. Alcohol and substance abuse
technical/government/Alcohol_Problems/Session4-PDF.txt:619:Stud Alcohol 2000;61:912-5.
technical/government/Alcohol_Problems/Session4-PDF.txt:621:the Alcohol Use Disorders Identification Test (AUDIT). Addiction
technical/government/Alcohol_Problems/Session4-PDF.txt:623:24. National Institute on Alcohol Abuse and Alcoholism. The
technical/government/Alcohol_Problems/Session4-PDF.txt:624:Physician's Guide to Helping Patients with Alcohol Problems.
technical/government/Alcohol_Problems/Session4-PDF.txt:639:28. Soderstrom CA, Dailey JT, Kerns TJ. Alcohol and other
technical/government/Alcohol_Problems/Session4-PDF.txt:645:30. Babor TF, Higgens-Biddle JC. Alcohol screening and brief
technical/government/Alcohol_Problems/Session4-PDF.txt:649:Alcohol Problems. Washington (DC): National Academy Press;
technical/government/Alcohol_Problems/Session4-PDF.txt:659:drinkers in the emergency department. J Stud Alcohol
technical/government/Alcohol_Problems/Session4-PDF.txt:669:37. Hester RK, Miller WR. Handbook of Alcoholism Treatment
technical/government/Alcohol_Problems/Session4-PDF.txt:675:39. Gerstein DR, editor. Toward the Prevention of Alcohol
technical/government/Alcohol_Problems/Session4-PDF.txt:683:hospitalized patients. Am J Drug Alcohol Abuse 1997;23:1-13.
technical/government/Alcohol_Problems/Session4-PDF.txt:711:49. Gentilello LM, Donovan DM, Dunn CW, and Rivara FP. Alcohol
technical/government/Alcohol_Problems/Session4-PDF.txt:716:51. New York State Office of Alcoholism and Substance Abuse
technical/government/Alcohol_Problems/Session4-PDF.txt:724:53. Rostenberg PO, editor. Alcohol and Other Drug Screening of
technical/government/Alcohol_Problems/Session4-PDF.txt:729:54. Confidentiality of Alcohol and Drug Abuse Patient Records,
technical/government/Alcohol_Problems/Session4-PDF.txt:732:56. National Institute on Alcohol Abuse and Alcoholism. Twelve
technical/government/Alcohol_Problems/Session4-PDF.txt:736:on Alcohol Abuse and Alcoholism; 1995. NIH Publication No.
technical/government/Alcohol_Problems/Session4-PDF.txt:1052:intervention-an Advanced Alcohol Problem Identification and
technical/government/Alcohol_Problems/Session4-PDF.txt:1300:Alcohol Screening Day, an NIAAA-sponsored event, is an opportunity
```

What I just did is look for the world Alcohol (case spesific) in all the .txt files in the directory `technical/government/Alcohol_Problems/` and it returned the lines that "Alcohol" appeared in **AND** the line numbes. 

**Ex2:**

```
$ grep -n 928 technical/government/*/*.txt

```

Now what happened here? Well I searched alllll the .txt files in government and nothing showed up. That's because nothing matched what I was looking for. Despite providing it such a large data set for it to search. 

3) -i

> ignore case distinctions

**Ex1:**
```
$ grep -i Problem technical/government/About_LSC/*
technical/government/About_LSC/Comments_on_semiannual.txt:program monitoring and development, to solve problems, and to
technical/government/About_LSC/Comments_on_semiannual.txt:specific opportunities and problems they face. LSC staff presented
technical/government/About_LSC/commission_report.txt:interpretive problems and fails to resolve the question of when an
technical/government/About_LSC/commission_report.txt:vulnerability of temporary agricultural workers and of problems
technical/government/About_LSC/commission_report.txt:and problems with obtaining workers compensation benefits may all
technical/government/About_LSC/commission_report.txt:legal problem with family members before seeking legal assistance.
technical/government/About_LSC/commission_report.txt:practical problems of representing farmworkers. See March Comments
technical/government/About_LSC/commission_report.txt:problems faced by representation of alien farmworkers generally, as
technical/government/About_LSC/commission_report.txt:number of interpretive problems and fails to resolve the question
technical/government/About_LSC/commission_report.txt:aware of the problems that had arisen under such programs, and of
technical/government/About_LSC/commission_report.txt:most glaring problem was the contractual relationship that existed
technical/government/About_LSC/commission_report.txt:States to visit spouses and children, to address family problems,
technical/government/About_LSC/conference_highlights.txt:i.e., rural with rural, or small with small - for mutual problem
technical/government/About_LSC/diversity_priorities.txt:complex problems), persons with disabilities, unemployed persons,
technical/government/About_LSC/diversity_priorities.txt:and empower all people with legal problems, programs pragmatically
technical/government/About_LSC/diversity_priorities.txt:community's most serious problems.
technical/government/About_LSC/diversity_priorities.txt:problems and see solutions implemented, power sharing, diverse
technical/government/About_LSC/diversity_priorities.txt:address a full-range of legal problems, and have assumed the
technical/government/About_LSC/diversity_priorities.txt:strategies in addressing community problems. State justice
technical/government/About_LSC/LegalServCorp_v_VelazquezDissent.txt:to deal with the problem another way." Id., at 193. This was not,
technical/government/About_LSC/LegalServCorp_v_VelazquezOpinion.txt:The restriction on speech is even more problematic because in
technical/government/About_LSC/LegalServCorp_v_VelazquezSyllabus.txt:more problematic because in cases where the attorney withdraws, the
technical/government/About_LSC/ONTARIO_LEGAL_AID_SERIES.txt:work with us to try to respond to the problems that are being
technical/government/About_LSC/ONTARIO_LEGAL_AID_SERIES.txt:just like us, certain problems:
technical/government/About_LSC/ONTARIO_LEGAL_AID_SERIES.txt:These are pretty serious problems. At times, they even appear
technical/government/About_LSC/ONTARIO_LEGAL_AID_SERIES.txt:civil legal problems. Despite the success of LSC and its many
technical/government/About_LSC/Progress_report.txt:unresolved civil legal problems result in homelessness, loss of
technical/government/About_LSC/Progress_report.txt:are one way to monitor program development, solve problems, and
technical/government/About_LSC/Progress_report.txt:monitor program development, to learn about problems and to suggest
technical/government/About_LSC/Progress_report.txt:analyzing client problems for referral to other resources. Programs
technical/government/About_LSC/reporting_system.txt:the usual kinds of startup problems one would expect of a new data
technical/government/About_LSC/reporting_system.txt:systematically diagnose each applicant's problems and make
technical/government/About_LSC/reporting_system.txt:mistakes that can lead to more serious legal problems and the need
technical/government/About_LSC/reporting_system.txt:of problems, some of them falling within the scope of the program's
technical/government/About_LSC/reporting_system.txt:be criminal matters or civil problems excluded under a grantee's
technical/government/About_LSC/reporting_system.txt:they have a legal problem. One hundred sixty nine grantees reported
technical/government/About_LSC/reporting_system.txt:solutions for complex problems such as domestic violence that raise
technical/government/About_LSC/reporting_system.txt:! Community legal education prevents small problems from getting
technical/government/About_LSC/Special_report_to_congress.txt:civil legal problems. Created in 1974, LSC is charged by Congress
technical/government/About_LSC/Special_report_to_congress.txt:these problems.
technical/government/About_LSC/Special_report_to_congress.txt:consistently find other, more efficient ways to solve problems for
technical/government/About_LSC/Special_report_to_congress.txt:problems exist in the statistical reports received and is taking
technical/government/About_LSC/Special_report_to_congress.txt:steps to identify and correct those problems. The problems
technical/government/About_LSC/Special_report_to_congress.txt:aggressively take steps to correct problems associated with the CSR
technical/government/About_LSC/Special_report_to_congress.txt:legal problems. Despite the success of LSC and its many
technical/government/About_LSC/Special_report_to_congress.txt:to 42 percent. A problem common to all programs was the untimely
technical/government/About_LSC/Special_report_to_congress.txt:closure of cases, although again the extent of the problem in any
technical/government/About_LSC/Special_report_to_congress.txt:4 GAO/GGD-99-135R LSC Case Reporting Problems.
technical/government/About_LSC/Special_report_to_congress.txt:to focus their attention on potential problem areas. As previously
technical/government/About_LSC/Special_report_to_congress.txt:problem and its complexities. Even though quantifiable data was
technical/government/About_LSC/Special_report_to_congress.txt:begin taking actions to address the problems. As previously noted,
technical/government/About_LSC/Special_report_to_congress.txt:attention to problem areas known at that time. Recognizing that
technical/government/About_LSC/Special_report_to_congress.txt:assistance to an eligible client with a legal problem, or set of
technical/government/About_LSC/Special_report_to_congress.txt:closely related legal problems, accepted for assistance supported
technical/government/About_LSC/Special_report_to_congress.txt:same legal problem in the same year. The test as to how similar the
technical/government/About_LSC/Special_report_to_congress.txt:problems, but there have been a large number of clear duplicates
technical/government/About_LSC/Special_report_to_congress.txt:of such problems may be as serious as the loss of a family's only
technical/government/About_LSC/Special_report_to_congress.txt:problem(s) of a client are not of a type prohibited by the LSC
technical/government/About_LSC/Special_report_to_congress.txt:possibly most, of these individuals with these problems would
technical/government/About_LSC/Special_report_to_congress.txt:problems addressed through the innovative service, and ¤ the impact
technical/government/About_LSC/Special_report_to_congress.txt:of the innovative service on the legal problems.
technical/government/About_LSC/Special_report_to_congress.txt:problems or aiding them in learning to handle problems when they
technical/government/About_LSC/Special_report_to_congress.txt:to organizations that can help the clients with their problems -
technical/government/About_LSC/Special_report_to_congress.txt:problems. A survey of selected programs in the spring of 1993, when
technical/government/About_LSC/Special_report_to_congress.txt:children. The legal problems faced by people living in poverty can
technical/government/About_LSC/Special_report_to_congress.txt:information critical to resolving their civil legal problems. In
technical/government/About_LSC/Special_report_to_congress.txt:The hearing heightened awareness of some of the problems LSC was
technical/government/About_LSC/State_Planning_Report.txt:including the legal problems of migrant sheepherders and health and
technical/government/About_LSC/State_Planning_Report.txt:Action Committees. Charged with exploring problems and
technical/government/About_LSC/State_Planning_Report.txt:Problem Solving; User Friendly Pro Se Adjudication; and Legal
technical/government/About_LSC/State_Planning_Report.txt:ILS must look at problems faced by the lowincome community from
technical/government/About_LSC/State_Planning_Report.txt:problems. Others are part of larger organizations that focus on
technical/government/About_LSC/State_Planning_Report.txt:specific populations or legal problems. In addition, Maryland has
technical/government/About_LSC/State_Planning_Report.txt:program to help address the burgeoning problem of law school debt,
technical/government/About_LSC/State_Planning_Report.txt:shared responsibility for addressing problems on a statewide
technical/government/About_LSC/State_Planning_Report.txt:recipients on a wide array of legal problems that can obstacles be
technical/government/About_LSC/State_Planning_Special_Report.txt:problems. LSC is
technical/government/About_LSC/State_Planning_Special_Report.txt:important, sometimes life-threatening, civil legal problems.
technical/government/About_LSC/Strategic_report.txt:developments, to learn about problems, and to develop new
technical/government/About_LSC/Strategic_report.txt:federal funding on the legal problems of people living in poverty.
technical/government/About_LSC/Strategic_report.txt:of the cases sampled in the self-inspection process have problems,
technical/government/About_LSC/Strategic_report.txt:then LSC assumes that there are overall problems within the
technical/government/About_LSC/Strategic_report.txt:reveal problems, grantees are asked to consult with LSC to
technical/government/About_LSC/Strategic_report.txt:people who have legal problems. We want to sustain and grow private
technical/government/About_LSC/Strategic_report.txt:study this problem and to recommend solutions.
```
In this example we can see that I looked up the word "Problem" with a captial P but in the output there are lines where problem is found *uncapitalized/ lowercased*. This could be really helpful when you need a specific word regardless of the case.


**Ex2:**

```
$ grep -i mEdIcAL technical/911report/*.txt
technical/911report/chapter-1.txt:    At 8:41, Sweeney told Woodward that passengers in coach were under the impression that there was a routine medical emergency in first class. Other flight attendants were busy at duties such as getting medical supplies while Ong and Sweeney were reporting the events.
technical/911report/chapter-10.txt:                medical assistance teams.
technical/911report/chapter-13.4.txt:                described the two Saudis as sons of a sick father who was seeking medical treatment
technical/911report/chapter-13.5.txt:                Emergency Medical Service data regarding patterns of illness (to spot a potential
technical/911report/chapter-13.5.txt:                Medical Examiner's Office, the WTC attacks killed 2,749 nonterrorists, including
technical/911report/chapter-13.5.txt:                Medical Examiner report, "WTCVictim List," undated (as of July 9, 2004). The
technical/911report/chapter-13.5.txt:                were appropriate is still a subject for medical and scientific debate. See EPA
technical/911report/chapter-3.txt:                the attack, offer medical and technical advice, and coordinate state and local
technical/911report/chapter-3.txt:                medical services, air traffic control, financial services, telephone systems, and
technical/911report/chapter-5.txt:                the cover story that he would be visiting a medical clinic to obtain a new
technical/911report/chapter-5.txt:                    in the German army before obtaining a medical discharge, and lived with Atta and
technical/911report/chapter-5.txt:                    Hamburg in 1998, where he studied medical technology. Soon after moving to
technical/911report/chapter-9.txt:                medical service, and building safety professionals.
technical/911report/chapter-9.txt:            Emergency medical services (EMS) personnel were directed to one of four triage areas
technical/911report/chapter-9.txt:                and medical response from Arlington County at the U.S. military's headquarters-a
technical/911report/chapter-9.txt:                National Medical ResponseTeam, the Bureau of Alcohol, Tobacco, and Firearms, and
```
We can see here the case does not matter at all; no matter where it may be in the word. 

4) -c

> prints *only* a count of matching lines per file

**Ex1:**
```
$ grep -c popular technical/government/*/*.txt
technical/government/About_LSC/Comments_on_semiannual.txt:0
technical/government/About_LSC/commission_report.txt:0
technical/government/About_LSC/conference_highlights.txt:0
technical/government/About_LSC/CONFIG_STANDARDS.txt:0
technical/government/About_LSC/diversity_priorities.txt:1
technical/government/About_LSC/LegalServCorp_v_VelazquezDissent.txt:0
technical/government/About_LSC/LegalServCorp_v_VelazquezOpinion.txt:0
technical/government/About_LSC/LegalServCorp_v_VelazquezSyllabus.txt:0
technical/government/About_LSC/ODonnell_et_al_v_LSCdecision.txt:0
technical/government/About_LSC/ONTARIO_LEGAL_AID_SERIES.txt:0
technical/government/About_LSC/Progress_report.txt:0
technical/government/About_LSC/Protocol_Regarding_Access.txt:0
technical/government/About_LSC/reporting_system.txt:0
technical/government/About_LSC/Special_report_to_congress.txt:0
technical/government/About_LSC/State_Planning_Report.txt:1
technical/government/About_LSC/State_Planning_Special_Report.txt:0
technical/government/About_LSC/Strategic_report.txt:2
technical/government/Alcohol_Problems/DraftRecom-PDF.txt:0
technical/government/Alcohol_Problems/Session2-PDF.txt:0
technical/government/Alcohol_Problems/Session3-PDF.txt:0
technical/government/Alcohol_Problems/Session4-PDF.txt:1
technical/government/Env_Prot_Agen/1-3_meth_901.txt:0
technical/government/Env_Prot_Agen/atx1-6.txt:0
technical/government/Env_Prot_Agen/bill.txt:0
technical/government/Env_Prot_Agen/ctf1-6.txt:0
technical/government/Env_Prot_Agen/ctf7-10.txt:0
technical/government/Env_Prot_Agen/ctm4-10.txt:0
technical/government/Env_Prot_Agen/final.txt:0
technical/government/Env_Prot_Agen/jeffordslieberm.txt:0
technical/government/Env_Prot_Agen/multi102902.txt:1
technical/government/Env_Prot_Agen/nov1.txt:0
technical/government/Env_Prot_Agen/ro_clear_skies_book.txt:0
technical/government/Env_Prot_Agen/section-by-section_summary.txt:0
technical/government/Env_Prot_Agen/tech_adden.txt:0
technical/government/Env_Prot_Agen/tech_sectiong.txt:0
technical/government/Gen_Account_Office/ai00134.txt:0
technical/government/Gen_Account_Office/ai2132.txt:0
technical/government/Gen_Account_Office/ai9868.txt:1
technical/government/Gen_Account_Office/d01121g.txt:0
technical/government/Gen_Account_Office/d01145g.txt:0
technical/government/Gen_Account_Office/d01186g.txt:0
technical/government/Gen_Account_Office/d01376g.txt:1
technical/government/Gen_Account_Office/d01591sp.txt:2
technical/government/Gen_Account_Office/d0269g.txt:0
technical/government/Gen_Account_Office/d02701.txt:0
technical/government/Gen_Account_Office/d03232sp.txt:0
technical/government/Gen_Account_Office/d03273g.txt:0
technical/government/Gen_Account_Office/d03419sp.txt:0
technical/government/Gen_Account_Office/ffm.txt:0
technical/government/Gen_Account_Office/gg96118.txt:0
technical/government/Gen_Account_Office/GovernmentAuditingStandards_yb2002ed.txt:0
technical/government/Gen_Account_Office/im814.txt:0
technical/government/Gen_Account_Office/InternalControl_ai00021p.txt:0
technical/government/Gen_Account_Office/July11-2001_gg00172r.txt:0
technical/government/Gen_Account_Office/June30-2000_gg00135r.txt:0
technical/government/Gen_Account_Office/Letter_Walkeraug17let.txt:0
technical/government/Gen_Account_Office/Letter_WalkerJan30-2001.txt:0
technical/government/Gen_Account_Office/May1998_ai98068.txt:1
technical/government/Gen_Account_Office/Oct15-1999_gg00026t.txt:0
technical/government/Gen_Account_Office/Oct15-2001_d0224.txt:0
technical/government/Gen_Account_Office/og96009.txt:0
technical/government/Gen_Account_Office/og96011.txt:0
technical/government/Gen_Account_Office/og96012.txt:0
technical/government/Gen_Account_Office/og96014.txt:0
technical/government/Gen_Account_Office/og96015.txt:0
technical/government/Gen_Account_Office/og96020.txt:0
technical/government/Gen_Account_Office/og96021.txt:0
technical/government/Gen_Account_Office/og96022.txt:0
technical/government/Gen_Account_Office/og96023.txt:0
technical/government/Gen_Account_Office/og96026.txt:0
technical/government/Gen_Account_Office/og96027.txt:0
technical/government/Gen_Account_Office/og96028.txt:0
technical/government/Gen_Account_Office/og96031.txt:0
technical/government/Gen_Account_Office/og96032.txt:0
technical/government/Gen_Account_Office/og96033.txt:0
technical/government/Gen_Account_Office/og96034.txt:0
technical/government/Gen_Account_Office/og96036.txt:0
technical/government/Gen_Account_Office/og96037.txt:0
technical/government/Gen_Account_Office/og96038.txt:0
technical/government/Gen_Account_Office/og96040.txt:0
technical/government/Gen_Account_Office/og96041.txt:0
technical/government/Gen_Account_Office/og96042.txt:0
technical/government/Gen_Account_Office/og96043.txt:0
technical/government/Gen_Account_Office/og96045.txt:0
technical/government/Gen_Account_Office/og96047.txt:0
technical/government/Gen_Account_Office/og97001.txt:0
technical/government/Gen_Account_Office/og97002.txt:0
technical/government/Gen_Account_Office/og97003.txt:0
technical/government/Gen_Account_Office/og97011.txt:0
technical/government/Gen_Account_Office/og97019.txt:0
technical/government/Gen_Account_Office/og97020.txt:0
technical/government/Gen_Account_Office/og97023.txt:0
technical/government/Gen_Account_Office/og97028.txt:0
technical/government/Gen_Account_Office/og97032.txt:0
technical/government/Gen_Account_Office/og97038.txt:0
technical/government/Gen_Account_Office/og97039.txt:0
technical/government/Gen_Account_Office/og97041.txt:0
technical/government/Gen_Account_Office/og97043.txt:0
technical/government/Gen_Account_Office/og97045.txt:0
technical/government/Gen_Account_Office/og97046.txt:0
technical/government/Gen_Account_Office/og97050.txt:0
technical/government/Gen_Account_Office/og97051.txt:0
technical/government/Gen_Account_Office/og97052.txt:0
technical/government/Gen_Account_Office/og98018.txt:0
technical/government/Gen_Account_Office/og98019.txt:0
technical/government/Gen_Account_Office/og98022.txt:0
technical/government/Gen_Account_Office/og98024.txt:0
technical/government/Gen_Account_Office/og98026.txt:0
technical/government/Gen_Account_Office/og98029.txt:0
technical/government/Gen_Account_Office/og98030.txt:0
technical/government/Gen_Account_Office/og98032.txt:0
technical/government/Gen_Account_Office/og98040.txt:0
technical/government/Gen_Account_Office/og98041.txt:0
technical/government/Gen_Account_Office/og98044.txt:0
technical/government/Gen_Account_Office/og98045.txt:0
technical/government/Gen_Account_Office/og98046.txt:0
technical/government/Gen_Account_Office/og99036.txt:0
technical/government/Gen_Account_Office/Paper_Walker11-2002_acpro122.txt:0
technical/government/Gen_Account_Office/pe1019.txt:2
technical/government/Gen_Account_Office/Sept14-2002_d011070.txt:0
technical/government/Gen_Account_Office/Sept27-2002_d02966.txt:0
technical/government/Gen_Account_Office/Statements_Feb28-1997_volume.txt:0
technical/government/Gen_Account_Office/Testimony_cg00010t.txt:1
technical/government/Gen_Account_Office/Testimony_d01609t.txt:0
technical/government/Gen_Account_Office/Testimony_Jul15-2002_d02940t.txt:0
technical/government/Gen_Account_Office/Testimony_Jul17-2002_d02957t.txt:0
technical/government/Media/5_Legal_Groups.txt:0
technical/government/Media/A_helping_hand.txt:0
technical/government/Media/A_Perk_of_Age.txt:0
technical/government/Media/Abuse_penalties.txt:0
technical/government/Media/Advocate_for_Poor.txt:0
technical/government/Media/agency_expands.txt:0
technical/government/Media/Aid_Gets_7_Million.txt:0
technical/government/Media/All_May_Have_Justice.txt:0
technical/government/Media/Annual_Fee.txt:0
technical/government/Media/Anthem_Payout.txt:0
technical/government/Media/AP_LawSchoolDebts.txt:0
technical/government/Media/Assuring_Underprivileged.txt:0
technical/government/Media/Attorney_gives_his_time.txt:0
technical/government/Media/Avoids_Budget_Cut.txt:0
technical/government/Media/balance_scales_of_justice.txt:0
technical/government/Media/Barnes_new_job.txt:0
technical/government/Media/Barnes_pro_bono.txt:0
technical/government/Media/Barnes_Volunteers.txt:0
technical/government/Media/Barr_sharpening_ax.txt:0
technical/government/Media/BergenCountyRecord.txt:0
technical/government/Media/Bias_on_the_Job.txt:0
technical/government/Media/Boone_legal_service.txt:0
technical/government/Media/Bridging_legal_aid_gap.txt:0
technical/government/Media/BusinessWire.txt:0
technical/government/Media/BusinessWire2.txt:0
technical/government/Media/Butler_Co_attorneys.txt:0
technical/government/Media/Campaign_Pays.txt:0
technical/government/Media/City_Council_Budget.txt:0
technical/government/Media/Civil_Matters.txt:0
technical/government/Media/Commercial_Appeal.txt:0
technical/government/Media/CommercialAppealMemphis2.txt:0
technical/government/Media/Coup_Reshapes_Legal_Aid.txt:0
technical/government/Media/Court_Keeps_Judge_From.txt:0
technical/government/Media/Crains_New_York_Business.txt:0
technical/government/Media/defend_yourself.txt:0
technical/government/Media/Disaster_center.txt:0
technical/government/Media/Do-it-yourself_divorce.txt:0
technical/government/Media/Domestic_violence_aid.txt:0
technical/government/Media/Domestic_Violence_Ruling.txt:0
technical/government/Media/Donald_Hilliker.txt:0
technical/government/Media/Entities_Merge.txt:0
technical/government/Media/Eviction_law.txt:0
technical/government/Media/families_saved.txt:0
technical/government/Media/Farm_workers.txt:0
technical/government/Media/Federal_agency.txt:0
technical/government/Media/Few_who_need.txt:0
technical/government/Media/fight_domestic_abuse.txt:0
technical/government/Media/Fire_Victims_Sue.txt:0
technical/government/Media/Firm_to_the_Poor_Needs_Help.txt:0
technical/government/Media/FortWorthStarTelegram.txt:0
technical/government/Media/Free_Legal_Assistance.txt:0
technical/government/Media/Free_legal_service.txt:0
technical/government/Media/Funding_cuts_force.txt:0
technical/government/Media/Funding_May_Limit.txt:0
technical/government/Media/Funds_Shortage.txt:0
technical/government/Media/FY_04_Budget_Outlook.txt:0
technical/government/Media/Ginny_Kilgore.txt:0
technical/government/Media/Good_guys_reward.txt:0
technical/government/Media/grants_fail_to_come.txt:0
technical/government/Media/Greedy_Generous.txt:0
technical/government/Media/GreensburgDailyNews.txt:0
technical/government/Media/Hard_to_Get.txt:0
technical/government/Media/help_rent-to-own_tenants.txt:0
technical/government/Media/Helping_Hands.txt:0
technical/government/Media/Helping_Out.txt:0
technical/government/Media/Higher_court.txt:1
technical/government/Media/Higher_Registration_Fees.txt:0
technical/government/Media/highlight_Senior_Day.txt:0
technical/government/Media/IOLTA_INTEREST_RATE.txt:0
technical/government/Media/It_Pays_to_Know.txt:0
technical/government/Media/Justice_for_all.txt:0
technical/government/Media/Justice_requests.txt:0
technical/government/Media/Kiosks_for_court_forms.txt:0
technical/government/Media/Law_Award_from_College.txt:0
technical/government/Media/Law_Schools.txt:0
technical/government/Media/Law-school_grads.txt:0
technical/government/Media/Lawyer_Web_Survey.txt:0
technical/government/Media/Legal_Aid_attorney.txt:0
technical/government/Media/Legal_Aid_campaign.txt:0
technical/government/Media/Legal_Aid_in_Clay_County.txt:0
technical/government/Media/Legal_Aid_looks_to_legislators.txt:0
technical/government/Media/Legal_Aid_Society.txt:0
technical/government/Media/Legal_hotline.txt:0
technical/government/Media/Legal_services_for_poor.txt:0
technical/government/Media/Legal_system_fails_poor.txt:0
technical/government/Media/Legal-aid_chief.txt:0
technical/government/Media/less_legal_aid.txt:0
technical/government/Media/Library_Lawyers.txt:1
technical/government/Media/Lindsays_legacy.txt:0
technical/government/Media/Local_Attorneys.txt:0
technical/government/Media/Lockyer_Warns.txt:0
technical/government/Media/Low-income_children.txt:0
technical/government/Media/Major_Changes.txt:0
technical/government/Media/Making_a_case.txt:0
technical/government/Media/man_on_national_team.txt:0
technical/government/Media/Marylands_Legal_Aid.txt:0
technical/government/Media/New_funding_sources.txt:0
technical/government/Media/New_Online_Resources.txt:0
technical/government/Media/NJ_Legal_Services.txt:0
technical/government/Media/Nonprofit_Buys.txt:0
technical/government/Media/not_accessible_to_disabled.txt:0
technical/government/Media/Oregon_Poor.txt:0
technical/government/Media/Owning_a_Piece.txt:0
technical/government/Media/Paralegal_Honored.txt:0
technical/government/Media/Philly_Lawyers.txt:0
technical/government/Media/Politician_Practices.txt:0
technical/government/Media/Poor_Lacking_Legal_Aid.txt:0
technical/government/Media/Poverty_Lawyers.txt:0
technical/government/Media/predatory_loans.txt:0
technical/government/Media/pro_bono_efforts.txt:0
technical/government/Media/Pro_Bono_Services.txt:0
technical/government/Media/Pro-bono_road_show.txt:0
technical/government/Media/Program_Lodges.txt:0
technical/government/Media/Providing_Legal_Aid.txt:0
technical/government/Media/Raising_the_Bar.txt:0
technical/government/Media/Rental_rules.txt:0
technical/government/Media/residents_sue_city.txt:0
technical/government/Media/Retirement_Has_Its_Appeal.txt:0
technical/government/Media/RoanokeTimes.txt:0
technical/government/Media/Rumble_in_the_Bronx.txt:0
technical/government/Media/Self-Help_Website.txt:0
technical/government/Media/Service_Agency.txt:0
technical/government/Media/State_funding.txt:0
technical/government/Media/Supporting_Legal_Center.txt:0
technical/government/Media/Survey.txt:0
technical/government/Media/Targeting_Domestic_Violence.txt:0
technical/government/Media/Terrorist_Attack.txt:0
technical/government/Media/Texas_Lawyer.txt:0
technical/government/Media/Texas_Supreme_Court.txt:0
technical/government/Media/The_Bend_Bulletin.txt:0
technical/government/Media/The_Columbian.txt:0
technical/government/Media/The_State_of_Pro_Bono.txt:3
technical/government/Media/Too_Crucial_to_Take_Cut.txt:0
technical/government/Media/Towson_Attorney.txt:0
technical/government/Media/Understanding.txt:0
technical/government/Media/Unusual_Woodburn.txt:0
technical/government/Media/Using_Tech_Tools.txt:0
technical/government/Media/Valley_Needing_Legal_Services.txt:0
technical/government/Media/Volunteers_Step_Up.txt:0
technical/government/Media/water_fees.txt:0
technical/government/Media/Weak_economy.txt:0
technical/government/Media/Wilmington_lawyer.txt:0
technical/government/Media/Wingates_winds.txt:0
technical/government/Media/Workers_aid_center.txt:0
technical/government/Media/Working_for_Free.txt:0
technical/government/Post_Rate_Comm/Cohenetal_comparison.txt:0
technical/government/Post_Rate_Comm/Cohenetal_Cost_Function.txt:0
technical/government/Post_Rate_Comm/Cohenetal_CreamSkimming.txt:0
technical/government/Post_Rate_Comm/Cohenetal_DeliveryCost.txt:0
technical/government/Post_Rate_Comm/Cohenetal_RuralDelivery.txt:0
technical/government/Post_Rate_Comm/Cohenetal_Scale.txt:0
technical/government/Post_Rate_Comm/Gleiman_EMASpeech.txt:0
technical/government/Post_Rate_Comm/Gleiman_gca2000.txt:0
technical/government/Post_Rate_Comm/Mitchell_6-17-Mit.txt:0
technical/government/Post_Rate_Comm/Mitchell_RMVancouver.txt:0
technical/government/Post_Rate_Comm/Mitchell_spyros-first-class.txt:0
technical/government/Post_Rate_Comm/Redacted_Study.txt:0
technical/government/Post_Rate_Comm/ReportToCongress2002WEB.txt:0
technical/government/Post_Rate_Comm/WolakSpeech_usps.txt:0
```
**WOAH!** I didn't realize that it would tell me 0 if word or what I am searching for is not present in the file. This could help if you need the file with the most of some word or character, or least of it. 

__Ex2:__

```
$ grep -c rhythm technical/biomed/1471-213X-1-9.txt
58
```

This command can also be used for a singular file. Remember that it will only display the amount that something appears, it will not tell you where they appear.

*All these options were found by using `grep --help` in my terminal*

