# CBT300
Converted to GitHub via [cbt2git](https://github.com/wizardofzos/cbt2git)

This is still a work in progress. GitHub repos will be deleted and created during this period...

```
//***FILE 300 CONTAINS MANY TSO CPS AND OTHER GOOD THINGS.  CODE    *   FILE 300
//*           FROM JIM MARSHALL (AIR FORCE RETIREE) NOW WITH THE    *   FILE 300
//*           US TREASURY OUTSIDE WASHINGTON DC.  THIS FILE IS      *   FILE 300
//*           IN IEBUPDTE SYSIN FORMAT.  JIM'S CURRENT ADDRESS IS   *   FILE 300
//*                                                                 *   FILE 300
//*                 Jim Marshall, Retired                           *   FILE 300
//*                                                                 *   FILE 300
//*           Please address inquiries to Sam Golob.                *   FILE 300
//*                                                                 *   FILE 300
//*                 email:  sbgolob@cbttape.org                     *   FILE 300
//*                                                                 *   FILE 300
//*       Note:  As of 10-24-02, all occurrences of the MSG macro   *   FILE 300
//*              have been changed to MSGZ, because MSG is now an   *   FILE 300
//*              assembler opcode (as of HLASM Release 4, or        *   FILE 300
//*              OS/390 Release 2.10).                              *   FILE 300
//*                                                                 *   FILE 300
//*       Note:  As of the end of 2012 and the beginning of 2013,   *   FILE 300
//*              we made an effort to fix many of these programs    *   FILE 300
//*              so they will run on z/OS systems, if they didn't   *   FILE 300
//*              work there anymore.  No guarantees, and updated    *   FILE 300
//*              members are usually marked with an ISPF id of      *   FILE 300
//*              SBGOLOB.  We also tried to keep the old versions   *   FILE 300
//*              intact, so they can still be found for MVS 3.8     *   FILE 300
//*              systems and the like.  (SG and BG)                 *   FILE 300
//*                                                                 *   FILE 300
//*       RELEASE 27  -  01 MAY 92                                  *   FILE 300
//*            (SOME MEMBERS WERE UPDATED LATER - SG 8/22)          *   FILE 300
//*                                                                 *   FILE 300
//*       SUMMARY OF THE MODULES CONTAINED.                         *   FILE 300
//*                                                                 *   FILE 300
//*          CP    REL           DESCRIPTION                        *   FILE 300
//*                                                                 *   FILE 300
//*       $#SVCKP   1  -  MACRO USED IN SOME OF THE PROGRAMS TO     *   FILE 300
//*                       INVOKE SVC TO GET ME BACK TO PROBLEM      *   FILE 300
//*                       STATE FROM SUPERVISOR STATE.              *   FILE 300
//*                                                                 *   FILE 300
//*       $#SVCKS   1  -  MACRO USED IN SOME OF THE PROGRAMS TO     *   FILE 300
//*                       INVOKE SVC TO GET ME TO SUPERVISOR STATE  *   FILE 300
//*                       FROM PROBLEM STATE.  YOU SHOULD USE YOUR  *   FILE 300
//*                       OWN SVC MECHANISM HERE.                   *   FILE 300
//*                                                                 *   FILE 300
//*       $DI       6X -  OPERATOR LIKE $DI COMMAND.                *   FILE 300
//*                                                                 *   FILE 300
//*       ABEND#    3X -  NOT A COMMAND BUT A HELP ENTRY FOR ABEND  *   FILE 300
//*                       CODES AND SOME OF THE COMMON REASONS      *   FILE 300
//*                       YOU MAY GET THEM.  UPDATED FOR MVS.       *   FILE 300
//*                                                                 *   FILE 300
//*       ASK       1Y -  CLIST.  USE CMD TO ASK A QUESTION AND     *   FILE 300
//*                       GET A YES OR NO BACK, THUS SETTING A      *   FILE 300
//*                       RETURN CODE.  (WAS AROUND IN MY MVT DAYS  *   FILE 300
//*                       AND IS OBSOLETE WITH MVS CLIST LANGUAGE)  *   FILE 300
//*                                                                 *   FILE 300
//*       ASMG      1Y -  DO ASSEMBLY LANGUAGE COMPILES             *   FILE 300
//*                       INTERACTIVELY IN ASSEM-G.  IS SIMILIAR    *   FILE 300
//*                       TO ONE IN THIS FILE FOR ASSEM-H.  BOTH    *   FILE 300
//*                       SHOULD WORK FOR OS/MVT AND MVS.           *   FILE 300
//*                                                                 *   FILE 300
//*       ASMH      4X -  DO ASSEMBLY LANG COMPILES INTERACTIVELY.  *   FILE 300
//*                       CAN GET IBM PROD WHICH IS SUPERIOR.       *   FILE 300
//*                       THIS IS FREE.  HAVE A 'SYS2.MACLIB'       *   FILE 300
//*                       DEFINED IN THIS ONE FOR USERS GENERALLY   *   FILE 300
//*                       HAVING USER MACLIB.  CHECKED THIS ONE     *   FILE 300
//*                       OUT FOR MVS/XA.                           *   FILE 300
//*                                                                 *   FILE 300
//*       ASMHNOX   1  -  ZAP TO THE IBM P.P. ASSEMBLER H TO FIX A  *   FILE 300
//*                       BUG SAYING 'NOXREF' YOU GET 'XREF(FULL)'. *   FILE 300
//*                       PTF LEVEL-21 MADE XREF DEF TO XREF(FULL)  *   FILE 300
//*                       AND INTRODUCED THE ERROR DESCRIBED ABOVE. *   FILE 300
//*                       NOTE:  ASSEMBLER H IS CLASS C (VERSION 1) *   FILE 300
//*                                                                 *   FILE 300
//*       ASMF      2  -  DO ASSEMBLY LANG COMPILES INTERACTIVE.    *   FILE 300
//*                       CAN GET THE IBM PRODUCT WHICH IS          *   FILE 300
//*                       SUPERIOR, BUT THIS ONE IS FREE.  HAVE A   *   FILE 300
//*                       'SYS2.MACLIB' DEFINED IN THIS ONE FOR     *   FILE 300
//*                       USERS GENERALLY HAVING A USER MACLIB.     *   FILE 300
//*                       THIS ONE USES THE ASMXF (IFOX00).  NOTE   *   FILE 300
//*                       THAT SOURCE FOR THIS IS ASMH PROMPTER     *   FILE 300
//*                       WITH SOME SYSPARMS CHANGED.               *   FILE 300
//*                                                                 *   FILE 300
//*       AUCMD        -  AUTHORIZE A TSO COMMAND BY CALLING IT     *   FILE 300
//*                       THROUGH THIS AUTHORIZED COMMAND.          *   FILE 300
//*                       AS CODED, YOU GET AUTHORIZATION VIA THE   *   FILE 300
//*                       IKJEFTE2 TABLE (AUTHCMD IN PARMLIB).      *   FILE 300
//*                                                                 *   FILE 300
//*       AUCMDA       -  AUTHORIZE A TSO COMMAND BY CALLING IT     *   FILE 300
//*                       THROUGH THIS AUTHORIZED COMMAND, BUT      *   FILE 300
//*                       IF YOU ALLOCATE AN AUTHORIZED LIBRARY     *   FILE 300
//*                       VIA A TASKLIB ALLOCATION, IT WILL GET     *   FILE 300
//*                       THE LOAD MODULE FROM THERE.               *   FILE 300
//*                       AS CODED, YOU GET AUTHORIZATION VIA THE   *   FILE 300
//*                       IKJEFTE2 TABLE (AUTHCMD IN PARMLIB).      *   FILE 300
//*                                                                 *   FILE 300
//*       AUPGM     2X -  AUTHORIZE A PROGRAM AND EXECUTE IT AS     *   FILE 300
//*                       A TSO COMMAND.                            *   FILE 300
//*                                                                 *   FILE 300
//*       CALC      1X -  TSO CALCULATOR PGM.  HAS 1 ACCUMULATOR    *   FILE 300
//*                       AND 9 REGISTERS.  CAN DO FUNCTIONS LIKE   *   FILE 300
//*                       SIN, COS, ETC, OR YOU CAN DEFINE YOUR     *   FILE 300
//*                       OWN.  (PLI-OPT)                           *   FILE 300
//*                       (Compile and install JCL has been fixed   *   FILE 300
//*                       for LE-based PL/I compilers under z/OS)   *   FILE 300
//*                                                                 *   FILE 300
//*       CATPW     1X -  BILL GODFREY:  DISPLAY PASSWORDS TO YOUR  *   FILE 300
//*                       ICF MASTER CATALOG.                       *   FILE 300
//*                                                                 *   FILE 300
//*       CBUF         -  TOOL TO EXAMINE THE COMMAND BUFFER WHEN   *   FILE 300
//*                       A TSO COMMAND IS ENTERED                  *   FILE 300
//*                                                                 *   FILE 300
//*       CDSCB     4  -  ZAP FORMAT-1 DSCB OF DATASETS ON THE FLY. *   FILE 300
//*                       USEFUL FOR SYSTEM TYPES !!!!              *   FILE 300
//*                       (NOW UPDATED BY BILL GODFREY FOR 21ST     *   FILE 300
//*                       CENTURY SUPPORT - SG 9/98.  ALSO BY       *   FILE 300
//*                       GREG PRICE - 2/99. HELP updated 07/99.)   *   FILE 300
//*                       (ADD SMS/NOSMS KEYWORDS TO BE ABLE TO     *   FILE 300
//*                       UNCATALOG DATASETS ON SMS VOLUMES.)       *   FILE 300
//*                       SG - 12/13/22 MAKE POSSIBILITY OF RUNNING *   FILE 300
//*                       TSO-IN-BATCH THE DEFAULT. SG - 11/18/24.  *   FILE 300
//*                                                                 *   FILE 300
//*       CLRSCRN   1X -  CLEAR THE SCREEN ON 3270.                 *   FILE 300
//*                                                                 *   FILE 300
//*       CLR2000   1Y -  CLEAR SCREEN ON HAZELTINE 2000 TTY TUBE   *   FILE 300
//*                                                                 *   FILE 300
//*       CMD          -  EXECUTE TSO COMMANDS (NON-AUTH)           *   FILE 300
//*                       LIKE AUCMDA, BUT THE COMMANDS ARE         *   FILE 300
//*                       EXECUTED NON-AUTHORIZED, PURPOSELY.       *   FILE 300
//*                                                                 *   FILE 300
//*       CMDLOFF   1X -  PASS A TSO COMMAND TO TSO CP AND WHEN IT  *   FILE 300
//*                       COMPLETES THE USER WILL BE LOGGED OFF.    *   FILE 300
//*                       INTERESTING IF YOU THINK ABOUT IT !!!!    *   FILE 300
//*                                                                 *   FILE 300
//*       COBOLCHK  3X -  AFDSC DEVELOPED CHEAP COBOL PROMPTER.     *   FILE 300
//*                       COBOL COMPILES(COBOLVS) INSIDE TSO, ONLY  *   FILE 300
//*                       GIVING ERRS AT TERMINAL.  USES 'SYNTAX'   *   FILE 300
//*                       OPT OF COMPILER AND IS GREAT FOR SLOW     *   FILE 300
//*                       SPEED TERMINALS.                          *   FILE 300
//*                                                                 *   FILE 300
//*       COB2CHK   2X -  VS/COBOL II R3.1 VERSION OF COBOLCHK.     *   FILE 300
//*                                                                 *   FILE 300
//*       COMPARE   3X -  COMPARE 2 FILES IN FOREGROUND. BASED ON   *   FILE 300
//*                       YALE UNIV COMPARE PGM.  OPTIONALLY, YOU   *   FILE 300
//*                       CAN ASK FOR IBM'S IEBCOMPR UTILITY PGM    *   FILE 300
//*                       INSTEAD.  MODIFIED YALE'S COMPARE PGM     *   FILE 300
//*                       AND CALLED IT COMPAREB.                   *   FILE 300
//*                                                                 *   FILE 300
//*       COMPRESS  2  -  COMPRESS A PDS IN FOREGROUND.             *   FILE 300
//*                                                                 *   FILE 300
//*       CONCAT    2X -  CONCAT 2-9 FILES TOGETHER.  MVS ALLOC     *   FILE 300
//*                       CMD CAN DO IT, BUT WE RUN PROGRAM         *   FILE 300
//*                       CONTROL FACILITY (PCF).  THUS IF THE      *   FILE 300
//*                       CUSTOMER FREES A FILE THAT IS SYS1,       *   FILE 300
//*                       THEN THEY CANNOT ALLOCATE IT BACK.        *   FILE 300
//*                                                                 *   FILE 300
//*       COPYPDS   4X -  COPIES A PDS TO ANOTHER PDS. ALLOWS YOU   *   FILE 300
//*                       TO COPY MEMBERS WITH A SELECT STATEMENT   *   FILE 300
//*                       AND ALSO SPECIFY THE ALIAS ENTRIES.       *   FILE 300
//*                                                                 *   FILE 300
//*       COPYSDS   3X -  COPY ONE SEQUENTIAL DATASET TO ANOTHER    *   FILE 300
//*                       SEQUENTIAL DATASET WITH SKIP, MAX NUMBER, *   FILE 300
//*                       ETC, ETC.                                 *   FILE 300
//*                                                                 *   FILE 300
//*       COUNT     2X -  COUNT THE NUMBER OF RECORDS IN A FILE.    *   FILE 300
//*                       (New 31-bit version)                      *   FILE 300
//*                       (Fix. DS1LSTAR is always 0 for a PDSE,    *   FILE 300
//*                        so always read the dataset even if       *   FILE 300
//*                        DS1LSTAR is 0.)                          *   FILE 300
//*                                                                 *   FILE 300
//*       COUNT1    1X -  COUNT THE NUMBER OF RECORDS IN A FILE.    *   FILE 300
//*                       (Old 24-bit version)                      *   FILE 300
//*                       (Fix. DS1LSTAR is always 0 for a PDSE,    *   FILE 300
//*                        so always read the dataset even if       *   FILE 300
//*                        DS1LSTAR is 0.)                          *   FILE 300
//*                                                                 *   FILE 300
//*       CPSCB     1  -  CHANGE YOUR PROTECTED STEP CONTROL BLOCK  *   FILE 300
//*                       (PSCB) ON THE FLY TO GIVE YOURSELF        *   FILE 300
//*                       THINGS LIKE MOUNT AUTHORITY ETC.  SHOULD  *   FILE 300
//*                       PROBABLY RESTRICT THIS TO SYSTEMS ONLY.   *   FILE 300
//*                       (Modified by Sam Golob to give TSO        *   FILE 300
//*                       CONSOLE authority. 04/05)                 *   FILE 300
//*                       (Modified by Sam Golob to give TSO        *   FILE 300
//*                       CONSOLE OPERPARM authority. 05/20)        *   FILE 300
//*                                                                 *   FILE 300
//*       CVD       1X -  BILL GODFREY: CONVERTS HEX NUMBER TO DEC  *   FILE 300
//*                                                                 *   FILE 300
//*       CVX       1X -  BILL GODFREY: CONVERTS DEC NUMBER TO HEX  *   FILE 300
//*                                                                 *   FILE 300
//*       DA        4X -  DISPLAY ACTIVE COMMAND TO GIVE THE USERS  *   FILE 300
//*                       A PICTURE OF THE SYSTEM.  THEY LIKE TO    *   FILE 300
//*                       SEE HOW MUCH TIME THE JOB HAS !!!!        *   FILE 300
//*                       (Fixed for z/OS by Sam Golob. Added       *   FILE 300
//*                       parameters to limit output by category.)  *   FILE 300
//*                       DAOLD is the original version.            *   FILE 300
//*                                                                 *   FILE 300
//*       DAJOB     4X -  DISPLAY ACTIVE CMD, HAS TSO USERS TOO     *   FILE 300
//*                       AND WHAT LOGON PROC THEY USE.             *   FILE 300
//*                       (FIXED FOR XA, ESA, OS/390, z/OS by       *   FILE 300
//*                       Sam Golob - Dec 28, 2012)                 *   FILE 300
//*                                                                 *   FILE 300
//*       DAPF      2X -  DISPLAY APF AUTHORIZED LIBRARY LIST USED  *   FILE 300
//*                       DURING THIS IPL.  PROBABLY WON'T WORK     *   FILE 300
//*                       FOR MVS/ESA 4.3 DYNAMIC AUTHORIZATION,    *   FILE 300
//*                       BUT WILL WORK UNTIL THEN.                 *   FILE 300
//*                       (Fixed for dynamic APF list.)   BG        *   FILE 300
//*                       (Updated to do PUTLINE output.) SG        *   FILE 300
//*                                                                 *   FILE 300
//*       DATE      2X -  GIVES THE DATE AND TIME FROM THE SYSTEM.  *   FILE 300
//*                                                                 *   FILE 300
//*       DDX       4  -  SHORT FORM OF ALLOCATE FOR AN EXISTING    *   FILE 300
//*                       FILE.  IT IS FASTER THAN ALLOCATE.        *   FILE 300
//*                       UPDATED TO LET YOU ALLOCATE A NEW FILE    *   FILE 300
//*                       ALSO. (Fixed for 8-character prefixes)    *   FILE 300
//*                       (Changed name from DD to DDX, because     *   FILE 300
//*                       there is an IBM command (short for        *   FILE 300
//*                       DELDSD which is also called DD.(SG-09/22) *   FILE 300
//*                                                                 *   FILE 300
//*       DDISK        -  DISPLAY ONLINE DASD VOLUMES               *   FILE 300
//*                                                                 *   FILE 300
//*       DECONCAT  2X -  REVERSE OF THE CONCAT COMMAND.            *   FILE 300
//*                                                                 *   FILE 300
//*       DELAY     1  -  SPECIFY A NUMBER OF SECONDS AND           *   FILE 300
//*                       HAVE YOU WAIT THAT LONG.                  *   FILE 300
//*                                                                 *   FILE 300
//*       DEX       1  -  TSO HEXADECMAL CALCULATOR PROGRAM.        *   FILE 300
//*                                                                 *   FILE 300
//*       DISPLAY   1Y -  SHOWS CONTROL BLOCKS LIKE THE UCB ETC.    *   FILE 300
//*                                                                 *   FILE 300
//*       DLINK     2X -  DISPLAY LINKLIST CMD TO SHOW LIBRARIES    *   FILE 300
//*                       WHICH ARE BEING USED THIS IPL.            *   FILE 300
//*                                                                 *   FILE 300
//*       DLPA      2X -  DISPLAY LPA LIST OF LIBRARIES IN EFFECT   *   FILE 300
//*                       FOR THIS IPL.                             *   FILE 300
//*                                                                 *   FILE 300
//*       DLXAUTHC  1  -  THIS CMD IS FROM MIKE LOOS, FAIR, ISAAC   *   FILE 300
//*                       AND CO.  IT WILL ISSUE THE COMMAND        *   FILE 300
//*                       PASSED TO IT AFTER SETTING THE JSCBAUTH   *   FILE 300
//*                       BIT ON.  WHEN THE COMMAND COMPLETES, THE  *   FILE 300
//*                       JSCBAUTH BIT WILL BE SET OFF.  THE JSCB   *   FILE 300
//*                       TAMPERING IS DONE IN A USER SVC (YOUR     *   FILE 300
//*                       OWN).  YOU MUST REPLACE THE USERSVC       *   FILE 300
//*                       MACRO WITH YOUR OWN INTEGRITY VIOLATION.  *   FILE 300
//*                       THIS COMMAND IS ESPECIALLY USEFUL FOR     *   FILE 300
//*                       ENTERING RACF COMMANDS FROM ISPF          *   FILE 300
//*                       DIALOGS.  FOR EXAMPLE:                    *   FILE 300
//*                                                                 *   FILE 300
//*                       DLXAUTHC LISTDSD DA('DSN1.EXAMPLE') ALL   *   FILE 300
//*                                                                 *   FILE 300
//*       DLVLDSS   2X -  DISPLAY DF/DSS LEVEL ON YOUR SYSTEM.      *   FILE 300
//*                                                                 *   FILE 300
//*       DOPROG    1X -  GIVES THE USER THE 'CALL' COMMAND         *   FILE 300
//*                       FUNCTION BY ATTACHING A PROGRAM.          *   FILE 300
//*                                                                 *   FILE 300
//*       DSNCHECK  1X -  GTELABS CMD TO CHECK FOR EXISTENCE OF     *   FILE 300
//*                       CATALOGED DSN NAME AND CAN CHECK FOR A    *   FILE 300
//*                       MEMBER WITHIN A PDS (SETS &LASTCC FOR     *   FILE 300
//*                       CLIST).  Fixed for z/OS 1.13.             *   FILE 300
//*                                                                 *   FILE 300
//*       DSPRIN    1X -  DONATION FROM VPS PEOPLE (LRS) OF AN      *   FILE 300
//*                       EARLY VERSION OF A CMD THAT TAKES         *   FILE 300
//*                       DSPRINT COMMAND ISSUED OUT OF ISPF AND    *   FILE 300
//*                       REFORMATS THE COMMAND INTO A 'PRINTOFF'.  *   FILE 300
//*                       THIS CAME TO LRS BY WAY OF BILL SMITH,    *   FILE 300
//*                       FORMERLY OF SYNTEX.  THANKS ALL !!!!      *   FILE 300
//*                                                                 *   FILE 300
//*       DSPRINT   1X -  BILL GODFREY:  TAKES THE FORMAT OF THE    *   FILE 300
//*                       IBM COMMAND AND DOES IT INSTEAD OF        *   FILE 300
//*                       REFORMATTING THE COMMAND AND ISSUING      *   FILE 300
//*                       A 'PRINTOFF' AS ABOVE.                    *   FILE 300
//*                       (Fixed for 8-character prefixes-z/OS 2.3) *   FILE 300
//*                                                                 *   FILE 300
//*       DSMF      2X -  OPERATOR-LIKE 'D SMF' COMMAND.            *   FILE 300
//*                       --FIXED FOR NEW FORMAT IEEMBRDS--         *   FILE 300
//*                       (FOR WHEN SMF DATASETS COULD HAVE         *   FILE 300
//*                       44-CHARACTER DSNAMES.)                    *   FILE 300
//*                                                                 *   FILE 300
//*       DSVC      1X -  DISPLAY YOUR SVC LIST IN EFFECT FOR IPL.  *   FILE 300
//*                                                                 *   FILE 300
//*       DTOD      1X -  DISPLAY FORMATTED TIME AND DATE FROM A    *   FILE 300
//*                       STCK-FORMAT DATE.  (NEEDS TODCNVRT MACRO  *   FILE 300
//*                       FROM THOMAS RAMSEIER - FILE 483, AND      *   FILE 300
//*                       COPIED TO THIS PDS)  TSO COMMAND.         *   FILE 300
//*                                                                 *   FILE 300
//*       DUDASD    4X -  OPERATOR-LIKE 'D U,DASD' CMD.  UPDATED    *   FILE 300
//*                       WITH NEW UCB SCAN ROUTINE AND ENHANCED    *   FILE 300
//*                       TO SHOW VOLUME STATE, DEVICE TYPE (LIKE   *   FILE 300
//*                       3380), AND WHICH VOLUME IS THE IPL        *   FILE 300
//*                       DEVICE.  ALSO CLEANED UP CODE, DOCUMENT,  *   FILE 300
//*                       ETC.  ALSO CHECKS TO SEE IF THE VTOC IS   *   FILE 300
//*                       INDEXED OR UNINDEXED, AND IF SHARED.      *   FILE 300
//*                                                                 *   FILE 300
//*       DUDASDR   1Y -  OPERATOR-LIKE  D U,DASD CMD (OLD VERSION) *   FILE 300
//*                                                                 *   FILE 300
//*       DUTAPE    3X -  OPERATOR-LIKE  D U,TAPE  CMD. CODED WITH  *   FILE 300
//*                       NEW UCB SCAN ROUTINE AND ENHANCED TO SHOW *   FILE 300
//*                       DEVICE TYPE (LIKE 3380).                  *   FILE 300
//*                                                                 *   FILE 300
//*       DUSER     1X -  SHOW THE USERIDS CURRENTLY LOGGED ON TSO. *   FILE 300
//*                       (FIXED FOR AMODE 31 - SBG)                *   FILE 300
//*                       (NEEDS CPINIT MACRO FIXED FOR AMODE 31)   *   FILE 300
//*                       (FIXED TO SHOW 8-CHARACTER USERIDS)       *   FILE 300
//*                                                                 *   FILE 300
//*       USERS        -  Display TSO users (same program as..)     *   FILE 300
//*       ACTIVE       -  Display Active Address Spaces             *   FILE 300
//*                       The ACTIVE program is an alias of the     *   FILE 300
//*                       USERS load module.  From disassembled     *   FILE 300
//*                       source.  To install, customize and        *   FILE 300
//*                       submit the member USERS.                  *   FILE 300
//*                       (Please see member USERSACT for any       *   FILE 300
//*                       relevant documentation regarding fixes.)  *   FILE 300
//*                       (See member USERSC1 for changes that had  *   FILE 300
//*                       to be made to the disassembled source.)   *   FILE 300
//*                       My recommendation: DA is a better program *   FILE 300
//*                       for displaying active jobs.               *   FILE 300
//*                                                                 *   FILE 300
//*       ECHOHEX   1X -  TYPE IN A LINE AND HAVE IT ECHOED BACK TO *   FILE 300
//*                       THE TERMINAL IN HEX.                      *   FILE 300
//*                                                                 *   FILE 300
//*       EDAIR30   1  -  SUBPROGRAM.  AN ENHANCED VERSION OF       *   FILE 300
//*                       IKJDAIR FOR ALLOCATING A SYSOUT DATASET.  *   FILE 300
//*                                                                 *   FILE 300
//*       EKKO      1  -  Type in a line and have it echoed back    *   FILE 300
//*                       to the terminal using PUTLINE.            *   FILE 300
//*                       One purpose for this command is to run    *   FILE 300
//*                       it in a REXX exec instead of SAY, to be   *   FILE 300
//*                       able to substitute variables into the     *   FILE 300
//*                       displayed string.                         *   FILE 300
//*                                                                 *   FILE 300
//*       ERROR#    2  -  NOT A COMMAND BUT A HELP ENTRY FOR        *   FILE 300
//*                       RETURN CODE YOU CAN GET FROM DAIR         *   FILE 300
//*                       ALLOCATION.  UPDATED FOR MVS.             *   FILE 300
//*                                                                 *   FILE 300
//*       FREEALL   4X -  MVS VERSION OF THE FAMOUS 'FREEALL' CMD   *   FILE 300
//*                       TO FREE DYNAMICALLY ALLOCATED DATASETS.   *   FILE 300
//*                       AFDSC MODIFIED TO FREE ALL DATASETS       *   FILE 300
//*                       WHICH:                                    *   FILE 300
//*                       A.  HAVE BEEN DYNAMICALLY ALLOCATED.      *   FILE 300
//*                       B.  ARE NOT CURRENTLY IN USE.             *   FILE 300
//*                       C.  ARE NOT CURRENTLY OPEN.               *   FILE 300
//*                       D.  ARE NOT ALLOCATED TO DDNAME=SYSPROC.  *   FILE 300
//*                                                                 *   FILE 300
//*       FINDFILE  1  -  DISPLAYS WHERE A DATASET IS CATALOGED     *   FILE 300
//*                       AND LISTS ALL MOUNTED DASD ON WHICH THE   *   FILE 300
//*                       DATASET RESIDES.  NOTE:  ON CBT TAPE AS   *   FILE 300
//*                       'LOCDSN'.  'FINDFILE' MORE DESCRIPTIVE.   *   FILE 300
//*                       (UCBSCAN fixed for z/OS and recent        *   FILE 300
//*                       systems.)                                 *   FILE 300
//*                                                                 *   FILE 300
//*       FORTP     2X -  DO FORTRAN G1 COMPILES INTERACTIVELY.     *   FILE 300
//*                       SEE JCL INSTALL.  IT IS SLICK AND NOT     *   FILE 300
//*                       JUST A SIMPLE COMPILE, LINKEDIT.  NOT     *   FILE 300
//*                       COMPLICATED BUT YOU USE THE SAME          *   FILE 300
//*                       SOURCE CODE WITH SYSPARM OPTIONS TO       *   FILE 300
//*                       COMPILE 2 MODULES.                        *   FILE 300
//*                                                                 *   FILE 300
//*       FORTX     1  -  FORT X (EXTENDED) COMPILES INTERACTIVELY. *   FILE 300
//*                       IBM'S FORT PRODUCT IS SUPERIOR, BUT THIS  *   FILE 300
//*                       IS FREE.                                  *   FILE 300
//*                                                                 *   FILE 300
//*       GDDM      2X -  GDDM PGMS WRITTEN MOSTLY IN FORTRAN.      *   FILE 300
//*                       SPACE SHUTTLE, X-29, ETC.  WILL WORK WITH *   FILE 300
//*                       OS/360 FORTRAN G ON THE TAPE.  FORT-G     *   FILE 300
//*                       RUNS ON MVS/XA FINE, AND FOR THOSE WITH   *   FILE 300
//*                       NO FORTRAN, IT IS BETTER THAN NOTHING.    *   FILE 300
//*                       THE MEMBER HAS '><' IN PLACE OF './' IN   *   FILE 300
//*                       THE './ ADD' CARDS.  LOOK AT THE MEMBER   *   FILE 300
//*                       TO SEE THE SOURCE AND THE SAMPLE JCL.     *   FILE 300
//*                                                                 *   FILE 300
//*       GFREEALL  1  -  GOT FROM GTELABS.  THEIR VERSION OF       *   FILE 300
//*                       SAME CMD CALLED 'FREEALL' THAT IS ON      *   FILE 300
//*                       THIS TAPE.                                *   FILE 300
//*                                                                 *   FILE 300
//*       GSTREAM   1  -  GOT FROM GTELABS. THEIR VERSION OF SAME   *   FILE 300
//*                       CMD CALLED 'INSTREAM' THAT IS ON THIS     *   FILE 300
//*                       TAPE.                                     *   FILE 300
//*                                                                 *   FILE 300
//*       GTEMACS   1  -  MACROS FROM GTELABS NEEDED FOR TSO CMDS   *   FILE 300
//*                       FROM CHUCK HOFFMAN.  USE 'PDSLOAD'        *   FILE 300
//*                       (IEBUPDTE LIKE PGM) FROM FILE 093         *   FILE 300
//*                       TO DOWNLOAD.  OR JUST LOOK AT MACROS.     *   FILE 300
//*                       YOU WILL SEE HOW THE MEMBER IS BUILT.     *   FILE 300
//*                       MACROS:  EQ$R, LINKSAVE, LINKBACK,        *   FILE 300
//*                       GTEDAALC, GTEDADAT, GTEDADOC, GTEDASET.   *   FILE 300
//*                                                                 *   FILE 300
//*       IKJEBMA9  3  -  EXAMPLE OF MVS EDIT SUB-COMMAND TABLE &   *   FILE 300
//*                       WHAT YOU CAN MAKE VALID SUB-COMMANDS.     *   FILE 300
//*                       HAS THE AFDSC SUB-COMMANDS OF EDIT IN     *   FILE 300
//*                       THE TABLE.                                *   FILE 300
//*                                                                 *   FILE 300
//*       IKJCT44B  1X -  USED IN TSO CLIST LANGUAGE TO CREATE OWN  *   FILE 300
//*                       VARIABLES STARTING WITH "&SYSX.." THANKS, *   FILE 300
//*                       CHICAGO SOFT, IT WAS IN 'TSO TIMES'.      *   FILE 300
//*                                                                 *   FILE 300
//*       IKJEFF10  1  -  AFDSC IPO BASED TSO SUBMIT EXIT.          *   FILE 300
//*                       THIS IS RELATIVELY SIMPLE.  FORCES THE    *   FILE 300
//*                       FOLLOWING RESTRICTION ON A TSO USER       *   FILE 300
//*                       1.  JOBNAME ON SUBMITTED JOB CARD         *   FILE 300
//*                       MUST BE USERID PLUS ONE CHARACTER.        *   FILE 300
//*                       2.  PROGRAMMER NAME FIELD (8 OR LESS      *   FILE 300
//*                       CHAR) IN UADS MUST MATCH PROGRAMMER       *   FILE 300
//*                       NAME (8 OR LESS ON JOB CARD).             *   FILE 300
//*                                                                 *   FILE 300
//*       IKJEFF53  1  -  AFDSC IPO BASED TSO 'STATUS/OUTPUT/CANCEL'*   FILE 300
//*                       EXIT.  A LOT OF POSSIBILITIES IN CODE.    *   FILE 300
//*                                                                 *   FILE 300
//*       IKJE9CL   1  -  'COLS'.  2ISG DEVELOPED EDIT SUBCMD PRINT *   FILE 300
//*                       COLUMN NUMBERS ON YOUR TERMINAL.  LIKE    *   FILE 300
//*                       ISPF/PDF OPTION 2  'COLS' CMD.            *   FILE 300
//*                                                                 *   FILE 300
//*       IKJE9CT   1  -  'COUNT'.  AFDSC DEVELOPED EDIT SUBCMD.    *   FILE 300
//*                       GIVES THE NUMBER OF RECORDS YOU ARE       *   FILE 300
//*                       CURRENTLY EDITING.                        *   FILE 300
//*                                                                 *   FILE 300
//*       IKJE9CX   1  -  'CHANGEX'  AFDSC DEVELOPED SUBCOMMAND OF  *   FILE 300
//*                       EDIT.  PERFORMS THE SAME FUNCTION AS      *   FILE 300
//*                       CHANGE, BUT USES HEX STRINGS.             *   FILE 300
//*                                                                 *   FILE 300
//*       IKJE9DU   1  -  'DUP'  AFDSC DEVELOPED EIDT SUBCMD.  SAME *   FILE 300
//*                       FUNCTION AS SPF REPEAT BUT ONLY ON 1 LINE *   FILE 300
//*                       CAN REPEAT EXISTING LINE OR MAKE A COPY   *   FILE 300
//*                       OF AN EXISTING LINE ELSEWHERE & REPEAT IT.*   FILE 300
//*                                                                 *   FILE 300
//*       IKJE9FX   1  -  'FINDX'.  AFDSC DEVELOPED EDIT SUBCMD.    *   FILE 300
//*                       DOES A FIND, SPECIFY A HEX CHAR STRING.   *   FILE 300
//*                                                                 *   FILE 300
//*       IKJE9OF   1  -  'OFFLINE'. AFDSC EDIT SUBCMD TO 'SPINOFF' *   FILE 300
//*                       PRT FILE YOU ARE CURRENTLY EDITING (ARE   *   FILE 300
//*                       NOT REQUIRED TO SAVE 1ST).  CAN 'DEST' TO *   FILE 300
//*                       RMTS, ETC.  SEE THE HELP FOR SPECIFICS.   *   FILE 300
//*                                                                 *   FILE 300
//*       IKJE9LT   1  -  'LISTTABS'. FOUND BY AFDSC. BACK FROM MVT *   FILE 300
//*                       DAYS, CONVERTED BY BOB HANSEN (SEC) FOR   *   FILE 300
//*                       MVS. LISTS YOUR CURRENT EDIT TABS FOR YOU *   FILE 300
//*                                                                 *   FILE 300
//*       IKJE9LX   1  -  'LISTX'.  AFDSC DEVELOPED SUBCMD OF       *   FILE 300
//*                       EDIT TO DISPLAY TO YOUR TERMINAL, LINES   *   FILE 300
//*                       OF A DATASET BEING EDITED IN HEX FORMAT.  *   FILE 300
//*                                                                 *   FILE 300
//*       IKJE9NA   1  -  'NAME'.  AFDSC DEVELOPED SUBCMD OF        *   FILE 300
//*                       EDIT TO TELL THE NAME OF THE FILE OR      *   FILE 300
//*                       MEMBER OF PDS YOU'RE CURRENTLY EDITING.   *   FILE 300
//*                       IT'S EMBARASSING IF YOU FORGET.           *   FILE 300
//*                                                                 *   FILE 300
//*       IKJE9PT   1  -  'PUT'.  AFDSC DEVELOPED SUBCMD OF EDIT TO *   FILE 300
//*                       PUT CHARACTER STRINGS IN CERTAIN COLUMNS. *   FILE 300
//*                       NICE FOR USERS OF ASYNC TERMINALS         *   FILE 300
//*                       WHO DO NOT HAVE SPF.                      *   FILE 300
//*                                                                 *   FILE 300
//*       IKJE9SP   1  -  'SPOT'.  AFDSC DEVELOPED EDIT SUBCMD,     *   FILE 300
//*                       SPOT CHARACTER STRINGS IN DATA.  AGAIN    *   FILE 300
//*                       NICE FOR ASYNCH TERMINALS WHO DO NOT      *   FILE 300
//*                       HAVE SPF.  CONTAINS A SELECT & EXCLUDE    *   FILE 300
//*                       FUNCTION FOR DELETION OF RECS THAT FIT A  *   FILE 300
//*                       PATTERN.  SEE THE HELP ENTRY FOR MORE     *   FILE 300
//*                       DETAILS.                                  *   FILE 300
//*                                                                 *   FILE 300
//*       IKJE9SS   2  -  'SAVESHR'.  AFDSC DEVELOPED EDIT SUBCMD   *   FILE 300
//*                       TO ALLOW SAVE WITH DISP=SHR.  EDIT HAS    *   FILE 300
//*                       NASTY HABIT OF TRYING TO GET DISP=OLD     *   FILE 300
//*                       WHEN YOU SAVE; THUS IF YOU NEED TO SAVE   *   FILE 300
//*                       SOMETHING INTO A FILE ALLOCATED ALL THE   *   FILE 300
//*                       TIME, TOUGH !!!!!  NOTE - APAR AZ57430    *   FILE 300
//*                       APPLIED.                                  *   FILE 300
//*                                                                 *   FILE 300
//*       IKJT9$    1  -  UPDATE SUBCMD TABLE OF TEST FOR           *   FILE 300
//*                       FOLLOWING SUBCMDS:                        *   FILE 300
//*                                                                 *   FILE 300
//*       IKJT9FI   1  -  'FIND' SUBCOMMAND OF THE TSO TEST CMD.    *   FILE 300
//*                                                                 *   FILE 300
//*       IKJT9FIZ  z  -  'FIND' SUBCOMMAND OF THE TSO TEST CMD.    *   FILE 300
//*                                                                 *   FILE 300
//*       IKJT9LB   1  -  'LIST BREAKPOINTS' SUBCMD OF TSO TEST CMD *   FILE 300
//*                                                                 *   FILE 300
//*       IKJT9LBZ  z  -  'LIST BREAKPOINTS' SUBCMD OF TSO TEST CMD *   FILE 300
//*                                                                 *   FILE 300
//*       IKJT9LGZ  z  -  'LIST 64-BIT GPRS' SUBCMD OF TSO TEST CMD *   FILE 300
//*                                                                 *   FILE 300
//*       IKJT9LI   1  -  'LIST' SUBCMD (2ND LOAD) OF TSO TEST CMD. *   FILE 300
//*                                                                 *   FILE 300
//*       IKJT9MAC  1  -  MACROS NEEDED FOR ABOVE ASSEMBLIES.       *   FILE 300
//*                                                                 *   FILE 300
//*       IKJT9Z$$  z  -  JOB TO INSTALL z/OS TEST SUBCOMMANDS      *   FILE 300
//*                       AND ASSOCIATED IKJTSOxx PARMLIB UPDATES.  *   FILE 300
//*                                                                 *   FILE 300
//*       INFOSYS   2X -  TSO CMD, EXECUTE IBM PRODUCT 'INFOSYS'.   *   FILE 300
//*                                                                 *   FILE 300
//*       INMXPARM  2X -  SAMPLE OF THE PARMS FOR TSO/E TRANSMIT &  *   FILE 300
//*                       RECEIVE.                                  *   FILE 300
//*                                                                 *   FILE 300
//*       INMXZ02   2X -  TSO/E TRANSMIT EXIT, NOTIFYING TSO USERS  *   FILE 300
//*                       ON SAME NODE THAT A FILE HAS BEEN SENT    *   FILE 300
//*                       TO THEM. GOTTEN FROM TUCC, JES2 MODS TAPE *   FILE 300
//*                       AND MODIFIED BY ME.  THANKS TUCC.         *   FILE 300
//*                                                                 *   FILE 300
//*       INSTREAM  1  -  AFDSC DEVELOPED CMD TO BE USED IN CLIST   *   FILE 300
//*                       PUT CONTROL CARDS INSIDE OF CLISTS. CAN   *   FILE 300
//*                       BE USER INPUT FROM THE TERMINAL.  NICE.   *   FILE 300
//*                                                                 *   FILE 300
//*       IO       (T) -  LIST I/O COUNTS FOR EACH FILE IN YOUR     *   FILE 300
//*                       TSO SESSION.                              *   FILE 300
//*                       (Fixed for z/OS. Old member is IOOLD.)    *   FILE 300
//*                                                                 *   FILE 300
//*       JCLSCAN   1  -  SAM GOLOB SENT THIS TO ME.  HE RAN IT ON  *   FILE 300
//*                       SP 1.3.5 AND XA 2.2.3 AND LOVES IT FOR    *   FILE 300
//*                       DOING A JCL CHECK PRIOR TO SUBMITTING.    *   FILE 300
//*                       HAS A PGM AND AN SVC TO INSTALL.  TRY IT. *   FILE 300
//*                                                                 *   FILE 300
//*       JULIAN    1X -  RETRIEVE THE DATE AND GREGORIAN DAY       *   FILE 300
//*                       FROM THE SYSTEM.  ALSO CAN RETURN THE     *   FILE 300
//*                       SAME INFO FOR ANY YEAR AND DAY.           *   FILE 300
//*                                                                 *   FILE 300
//*             Modified to accept 4-digit dates, by Steven         *   FILE 300
//*             Peckham - 10/99                                     *   FILE 300
//*                                                                 *   FILE 300
//*       KOMM      1X -  USED IN CLISTS FOR FORMATTING DISPLAYS IN *   FILE 300
//*                       FULL SCREEN SUPPORT, 3270 TYPE TERMINALS. *   FILE 300
//*                                                                 *   FILE 300
//*       LASTCC#   1  -  NOT A TSO COMMAND, BUT A HELP ENTRY OF    *   FILE 300
//*                       LIST OF ERROR CODES THAT CAN OCCUR IN     *   FILE 300
//*                       A CMD PROCEDURE (CLIST) INFO WAS COPIED   *   FILE 300
//*                       FROM MANUAL GC28-0646, TSO CMD LANG REF.  *   FILE 300
//*                                                                 *   FILE 300
//*       LASTIPL   2X -  DISPLAY THE JULIAN, GREGORIAN, AND        *   FILE 300
//*                       CALENDAR DATE PLUS THE TIME IN HH.MM THAT *   FILE 300
//*                       YOUR SYSTEM WAS LAST IPL'ED.  OPERATORS   *   FILE 300
//*                       DO ALWAYS TELL YOU TRUE STORIES ????      *   FILE 300
//*                                                                 *   FILE 300
//*       LIBCALL   1  -  GTELABS CMD TRANSFERS CONTROL TO          *   FILE 300
//*                       MODULES WITH A 'CALL' TYPE PARAMTER       *   FILE 300
//*                       LIST, WITH A 'STEPLIB' OPTION.  LIBCALL   *   FILE 300
//*                       ALSO CAN ACCEOT PGM PARMS IN LOWER        *   FILE 300
//*                       CASE.                                     *   FILE 300
//*                                                                 *   FILE 300
//*       LISTAX    1X -  SAME AS IBM 'LISTA' CMD BUT GIVES YOU     *   FILE 300
//*                       INFO YOU CAN USE, LIKE DDNAME, DISP, ETC  *   FILE 300
//*                       ETC.  MORE SIMILAR TO ISRDDN UNDER ISPF.  *   FILE 300
//*                       (Fixed for z/OS by Sam Golob)             *   FILE 300
//*                                                                 *   FILE 300
//*       LISTMOD   1  -  TSO COMMAND TO LIST LOAD MODULES IN VERY  *   FILE 300
//*                       READABLE FORMAT.  MAKES IT EASY TO READ   *   FILE 300
//*                       LOAD MODULES.  HELPS ALSO, TO SEE IF      *   FILE 300
//*                       ZAPS HAVE BEEN APPLIED.  (FROM S.GOLOB)   *   FILE 300
//*                                                                 *   FILE 300
//*       MACROS    1X -  MACROS IN THE FILE HAVE BEEN PACKAGED     *   FILE 300
//*                       IN THIS MEMBER PRECEDED BY ./ CARDS.      *   FILE 300
//*                                                                 *   FILE 300
//*                       PACKAGED MOST OF THE MACROS PRECEDED BY   *   FILE 300
//*                       '><' CARDS INSTEAD OF './'.  USE          *   FILE 300
//*                       'PDSLOAD' TO LOAD.  SEE INSTALL           *   FILE 300
//*                       JOBSTREAM AND YOU WILL SEE HOW.  DID IT   *   FILE 300
//*                       LIKE THIS FOR MACROS SO JUST DO A         *   FILE 300
//*                       PDSLOAD (LIKE IEBUPDTE) TO RUN THEM       *   FILE 300
//*                       INTO A TEMP PDS FOR YOUR ASSEMBLY.        *   FILE 300
//*                                                                 *   FILE 300
//*                           A-B        C        D-E       F-Z     *   FILE 300
//*                        12345678  12345678  12345678  12345678   *   FILE 300
//*                        $#SVCKP   CPDATA    DO08BLD   GNRLFAIL   *   FILE 300
//*                        $#SVCKS   CPEND     DCS       JVDENTER   *   FILE 300
//*                        $EPILOG   CPENTER   DCSPARS   JVDEQU     *   FILE 300
//*                        $PROLOG   CPENTRY   EQUENT    JVDLEAVE   *   FILE 300
//*                                  CPEXIT    EQUEXT    MSGLPA     *   FILE 300
//*                                  CPINIT    EQUREG    REGEQU     *   FILE 300
//*                                  CVDT      EQUREGS   REGS       *   FILE 300
//*                                  CVRT                TMPMAC     *   FILE 300
//*                                                                 *   FILE 300
//*       LISTCDS   2Y -  LIST THE SMP4 CDS FILE (SYS1.SMPCDS).     *   FILE 300
//*                                                                 *   FILE 300
//*       LISTLPA   2Y -  LIST ATTRIBUTES OF MEMBERS OF LPALIB.     *   FILE 300
//*                       (FIXED FOR 31-BIT ADDRESSES)              *   FILE 300
//*                       Fixed for z/OS 2.n.  Use member LISTLPA1  *   FILE 300
//*                       for older MVS versions, if this source    *   FILE 300
//*                       doesn't work or assemble there.           *   FILE 300
//*                                                                 *   FILE 300
//*       LISTSPC   3X -  LIST SPACE ATTRIBUTES OF A FILE ON DASD.  *   FILE 300
//*                                                                 *   FILE 300
//*       LISTSU    1X -  WORTHLESS CMD, LIST THE SU NUMBERS YOU    *   FILE 300
//*                       HAVE INSTALLED ON YOUR SYSTEM.            *   FILE 300
//*                                                                 *   FILE 300
//*       LISTVTOC     -  PROGRAM TO LIST DATASETS ON A DASD PACK   *   FILE 300
//*                       IN THE ORDER THEY APPEAR IN THE VTOC.     *   FILE 300
//*                       THE REASON FOR THIS IS USUALLY TO FIND    *   FILE 300
//*                       DATASETS THAT HAVE ANOMALIES, OR SOME     *   FILE 300
//*                       PROPERTY, VERY QUICKLY. SEE THE KEYWORDS  *   FILE 300
//*                       THAT ARE AVAILABLE IN THE PROGRAM. THE    *   FILE 300
//*                       PROGRAM READS AN ENTIRE TRACK OF VTOC     *   FILE 300
//*                       ENTRIES WITH ONE EXCP, SO IT CAN BE USED  *   FILE 300
//*                       AS A CODING EXAMPLE TO SEE HOW THIS WAS   *   FILE 300
//*                       DONE.                                     *   FILE 300
//*                                                                 *   FILE 300
//*       LM        1  -  LIST MEMBER NAMES OF A DIRECTORY OF PDS.  *   FILE 300
//*                       (Storage was too small for pds'es with    *   FILE 300
//*                       many members. Raised it at least 12-fold  *   FILE 300
//*                       to accommodate these large pds'es.)       *   FILE 300
//*                                                                 *   FILE 300
//*       LOGOBSC   1  -  EXAMPLE OF VTAM LOGO SCREEN FOR           *   FILE 300
//*                       ACF/VTAM TO IMPRESS MGMT.  PUT A LOT      *   FILE 300
//*                       OF COMMENTS AS TO HOW TO CODE BSC LOGO    *   FILE 300
//*                       SCREEN.  BOOKS ARE NOT VERY CLEAR.        *   FILE 300
//*                       MADE MINE SO ANYONE COULD FILL IN A       *   FILE 300
//*                       PREDEFINED BOX AND USE MY CODE.           *   FILE 300
//*                                                                 *   FILE 300
//*       LOGOSNA   1  -  EXAMPLE OF VTAM LOGO SCREEN FOR           *   FILE 300
//*                       ACF/VTAM TO IMPRESS MGMT.  PUT A LOT      *   FILE 300
//*                       OF COMMENTS AS TO HOW TO CODE SNA LOGO    *   FILE 300
//*                       SCREEN.  BOOKS ARE NOT TOO BAD.  MADE     *   FILE 300
//*                       MINE SO ANYONE COULD FILL IN A            *   FILE 300
//*                       PREDEFINED BOX AND USE MY CODE.           *   FILE 300
//*                                                                 *   FILE 300
//*       LOGTIME   1  -  TSO COMMAND TO TELL THE USER WHEN         *   FILE 300
//*                       HIS/HER LOGON TIME WAS.                   *   FILE 300
//*                       (ADAPTED FROM LASTCLPA PROGRAM ON CBT     *   FILE 300
//*                       FILE 133.)                                *   FILE 300
//*                                                                 *   FILE 300
//*       LPSCB     3X -  LIST PSCB (PROTECTED STEP CONTROL BLK).   *   FILE 300
//*                       (Modified by Sam Golob to more accurately *   FILE 300
//*                       reflect macro IKJPSCB at z/OS 1.6.)       *   FILE 300
//*                       (Fixed to show an extra field in UPT.)    *   FILE 300
//*                       (Fixed to format the LOGON date and time  *   FILE 300
//*                       in PSCBLTIM.  Needs TODCNVRT program.)    *   FILE 300
//*                       (Modified by Sam Golob to show TSO        *   FILE 300
//*                       CONSOLE OPERPARM authority. CNOP 05/20)   *   FILE 300
//*                                                                 *   FILE 300
//*       MEMBER    3X -  SCAN A LIBRARY FOR A MEMBER.  CAN BE      *   FILE 300
//*                       USED TO RUN THE LINK LIST FOR FIRST       *   FILE 300
//*                       OCCURRENCE OF THAT MEMBER. WILL ALSO      *   FILE 300
//*                       DISPLAY LKED ATTRIBUTES, CSECT, IDR       *   FILE 300
//*                       DATA, LINKLIST LIB NUMBER.  SHOWS SPF     *   FILE 300
//*                       STATS FOR SOURCE DATA.                    *   FILE 300
//*                       (Fixed for 8-character prefixes if VOL    *   FILE 300
//*                       keyword is specified. If not, then it     *   FILE 300
//*                       will not find the 8-char prefix unless    *   FILE 300
//*                       it is run on at least z/OS 2.3 or newer)  *   FILE 300
//*                                                                 *   FILE 300
//*       MURPHY    4X -  GET A THOUGHT FOR THE DAY.  MUCH THANKS   *   FILE 300
//*                       TO PAUL BANKS, ALLERGAN PHARMACEUTICALS   *   FILE 300
//*                       IN IRVINE, CA FOR THE IDEA.  THIS VERSION *   FILE 300
//*                       IS FROM ART TANSKY OF SUNGARD IN VOORHEES *   FILE 300
//*                       NEW JERSEY, AND WAS REVISED CONSIDERABLY. *   FILE 300
//*                                                                 *   FILE 300
//*       MURPHYO   3X -  OLD VERSION OF MURPHY.  THIS IS FROM      *   FILE 300
//*                       PAUL BANKS, FORMERLY OF ALLERGAN          *   FILE 300
//*                       PHARMACEUTICALS IN IRVINE, CALIFORNIA.    *   FILE 300
//*                       I HAVE ADDED SOME 'THOUGHTS'.             *   FILE 300
//*                                                                 *   FILE 300
//*       NEWSPACE  1  -  GTELABS CMD FOR EASILY CREATING NEW,      *   FILE 300
//*                       MODERATELY SIZED DATASETS & LIBS.         *   FILE 300
//*                       WRITTEN WITH BEGINNERS IN MIND.           *   FILE 300
//*                       EXECUTED FROM ISPF/PDF CMD LINE FOR       *   FILE 300
//*                       A FILE YOU SUDDENLY NEED.                 *   FILE 300
//*                                                                 *   FILE 300
//*       NEWISPF   1  -  FOUND TSO CMD ON MODS TAPE USED WITH      *   FILE 300
//*                       NEW ISPF/PDF PRODUCT TO GET YOU INTO      *   FILE 300
//*                       THE PDF WITH THE CLIST.  BUT IT USED      *   FILE 300
//*                       THE USER'S PREFIX INSTEAD OF THE USERID.  *   FILE 300
//*                       MADE SOME MINOR CHANGES TO IT AND         *   FILE 300
//*                       CHANGED NAME FROM 'PDF' TO 'NEWISPF'.     *   FILE 300
//*                                                                 *   FILE 300
//*       OPERA     1Y -  ALLOWS CONSOLE COMMANDS (EXCEPT JES2)     *   FILE 300
//*                       TO BE ENTERED FROM YOUR TSO TERMINAL.     *   FILE 300
//*                       USER MUST HAVE OPERATOR AUTHORITY.        *   FILE 300
//*                       (Fixed to use MGCRE instead of MGCR.)     *   FILE 300
//*                       (Old copy still there, as OPERA00)        *   FILE 300
//*                                                                 *   FILE 300
//*       OUTPRINT  1Y -  PRINTS A DATASET CREATED BY THE TSO       *   FILE 300
//*                       'OUTPUT' CMD, BUT YOU WILL GET PROPER     *   FILE 300
//*                       CARRIAGE CONTROL.  SEE DOCUMENTATION      *   FILE 300
//*                       IN THE CODE FOR ALL THE FINE POINTS.      *   FILE 300
//*                                                                 *   FILE 300
//*       PLIF      TY -  PL/1 F LEVEL PROMPTER.  HAVE NOT TRIED    *   FILE 300
//*                       IT BECAUSE WE DO NOT RUN PL/1 F.  SO      *   FILE 300
//*                       YOU ARE ON YOUR OWN.                      *   FILE 300
//*                                                                 *   FILE 300
//*       POF       3  -  TSO CMD TO LET YOU DO VTAM COMMANDS FROM  *   FILE 300
//*                       YOUR TSO TERMINAL.  BRIAN SCOTT, US POST  *   FILE 300
//*                       SERVICE, TOPEKA, KS. SENT ME THIS ONE.    *   FILE 300
//*                       VERY EASY TO INSTALL.  SEE CODE FOR SOME  *   FILE 300
//*                       AUTHORITY CHECKING AND PASSWORD FOR THE   *   FILE 300
//*                       VTAM ACB.  HE GOT FROM FEDERAL EXPRESS.   *   FILE 300
//*                                                                 *   FILE 300
//*       PPXIT     1Y -  TEST YOUR PREPROMPT EXIT (IKJEFLD) WITH   *   FILE 300
//*                       THIS ROUTINE LOGON JUST AS IF YOU WOULD   *   FILE 300
//*                       LOGON ORDINARILY, EXCEPT INSTEAD OF       *   FILE 300
//*                       'LOGON USER' YOU SAY 'PPXIT USER'.  IT    *   FILE 300
//*                       WILL GIVE YOU ALL THE MSGS AND IF YOU     *   FILE 300
//*                       ABEND, AUTOMATICALLY GO INTO TEST FOR     *   FILE 300
//*                       DEBUGGING.  SEE COMMENTS IN CODE.         *   FILE 300
//*                                                                 *   FILE 300
//*       PRINTOFF  3X -  AFDSC MODIFIED CMD.  HAS 'ASA' ADDED TO   *   FILE 300
//*                       ALLOW PRTER TO USE 'ASA' CARRIAGE         *   FILE 300
//*                       CONTROL EVEN IF IT WAS NOT IN THE DCB OF  *   FILE 300
//*                       THE FILE TO BE PRINTED, HAS THE 'GTE'     *   FILE 300
//*                       MODS FOR FCB SUPPORT, ETC.  CORRECTED 7   *   FILE 300
//*                       CHAR DEST CODE LIMIT.  FIXED THE          *   FILE 300
//*                       LIMITATION OF ONLY HAVING 7 CHARACTER     *   FILE 300
//*                       DESTID'S FOR JES2.  NOT COOL, BOOK SAYS   *   FILE 300
//*                       YOU CAN HAVE 8 CHARACTERS.                *   FILE 300
//*                                                                 *   FILE 300
//*       PUNCH     1  -  PUNCH A CARD DECK.  HAS THE OPTION TO     *   FILE 300
//*                       HOLD THE OUTPUT FOR REVIEW BEFORE YOU     *   FILE 300
//*                       LET IT GO TO BE PUNCHED.                  *   FILE 300
//*                                                                 *   FILE 300
//*       QCB       1Y -  REPLACEMENT FOR WHOHAS CMD.  MORE         *   FILE 300
//*                       POWERFUL MAY NEED TO BE REWORKED FOR      *   FILE 300
//*                       MVS/SP1.3.                                *   FILE 300
//*                                                                 *   FILE 300
//*       QLIST     1X -  AFDSC DEVELOPED COMMAND TO DO MOST OF     *   FILE 300
//*                       ALL THE IBM TSO DATA UTIL 'LIST' DOES     *   FILE 300
//*                       BUT IN SOME AREAS IT IS FASTER & MORE     *   FILE 300
//*                       EFFICIENT.                                *   FILE 300
//*                                                                 *   FILE 300
//*       RACFALT   1Y -  THIS PROGRAM FROM MIKE LOOS, FAIR, ISAAC  *   FILE 300
//*                       AND CO.  IT WILL GENERATE A CLIST TO      *   FILE 300
//*                       CHANGE THE VOLUME SERIAL NUMBERS IN RACF  *   FILE 300
//*                       PROFILES OF ALL NONVSAM DATASETS ON A     *   FILE 300
//*                       SPECIFIC VOLUME.                          *   FILE 300
//*                                                                 *   FILE 300
//*       RACFCLST  1Y -  PROGRAM IS FROM MIKE LOOS, FAIR, ISAAC    *   FILE 300
//*                       AND CO.  IT WILL GENERATE A CLIST TO      *   FILE 300
//*                       REDEFINE (VIA RACF CMDS DELSD, ADDSD,     *   FILE 300
//*                       AND PERMIT) FOR ALL DATASETS ON A         *   FILE 300
//*                       SPECIFIED VOLUME.  DUE TO USE OF RACF     *   FILE 300
//*                       INTERNAL MACROS THIS PROGRAM MUST BE      *   FILE 300
//*                       RUN AUTHORIZED.  IF SYSIN IS PRESENT,     *   FILE 300
//*                       YOU CAN INCLUDE CMDS TO SELECT BY DSN     *   FILE 300
//*                       GROUP ON A VOLUME AND/OR DATASET NAME     *   FILE 300
//*                       WITH OR WITHOUT VOLUME SPECIFICATION.     *   FILE 300
//*                       WARNING:  IF SYSIN IS PRESENT AND         *   FILE 300
//*                       DUMMIED OUT OR EMPTY THEN A NULL CLIST    *   FILE 300
//*                       WILL BE CREATED.                          *   FILE 300
//*                                                                 *   FILE 300
//*       REVIEW    6Y -  FULL SCREEN BROWSE, 3270 TYPE             *   FILE 300
//*                       TERMINALS.  RESEMBLANCE TO ISPF BROWSE    *   FILE 300
//*                       IS PURELY A CHANCE OF FATE.  ARE SOME     *   FILE 300
//*                       BUGS IF YOU TRY TO BROWSE SMF FILES       *   FILE 300
//*                       (VARIABLE LENGTH RECS) BUT SHOULD BE      *   FILE 300
//*                       FINE FOR SANE THINGS LIKE PDS'S AND       *   FILE 300
//*                       SOURCE.  SMF CODE HAS BEEN EXPANDED       *   FILE 300
//*                       AND 'FINDSMF' SUBCMD ADDED.               *   FILE 300
//*                 (THIS ONE IS OLD - USE "REVIEW" FROM FILE 134.) *   FILE 300
//*                                                                 *   FILE 300
//*       REVSMF    1Y -  SUBROUTINE NEEDED BY REVIEW WHEN          *   FILE 300
//*                       LOOKING AT SMFDATA.                       *   FILE 300
//*                 (THIS ONE IS OLD - USE "REVSMF" FROM FILE 134.) *   FILE 300
//*                                                                 *   FILE 300
//*       RLSE      3  -  AFDSC MODIFIED CMD.  RELEASE SPACE OUT    *   FILE 300
//*                       OF A PDS OR SEQ FILE.  PREVIOUS VERSIONS  *   FILE 300
//*                       RELEASED ALL THE SPACE.  OURS WILL ALLOW  *   FILE 300
//*                       YOU TO RELEASE DOWN TO PRIMARY EXTENT OR  *   FILE 300
//*                       OR SPECIFY THE AMOUNT TO BE RELEASED.     *   FILE 300
//*                                                                 *   FILE 300
//*       SAFECOPY  1  -  GTELABS COPY CMD, ENABLES SEVERAL USERS   *   FILE 300
//*                       TO UPDATE SAME DSN SIMULTANEOUSLY,        *   FILE 300
//*                       WITHOUT CONFLICT WITH EACH OTHER OR WITH  *   FILE 300
//*                       USERS WHO ARE READING DSN.  SAFECOPY IS   *   FILE 300
//*                       USEFUL IN CLISTS THAT WRITE TO A COMMON   *   FILE 300
//*                       DSN.                                      *   FILE 300
//*                                                                 *   FILE 300
//*       SCRATCH   TY -  SCRATCH A DSN AND NOT GO THROUGH CATALOG. *   FILE 300
//*                       (Fixed by Updater - 08/12/2017)           *   FILE 300
//*                                                                 *   FILE 300
//*       SHELP     1X -  OBTAIN SUB-COMMAND HELPS FOR CMDS WITHOUT *   FILE 300
//*                       ACTUALLY BEING IN THAT COMMAND.           *   FILE 300
//*                                                                 *   FILE 300
//*       SHOWDS    4X -  BILL GODFREY:  DISPLAYS THE DATASET       *   FILE 300
//*                       ATTRIBUTES AND SPACE ALLOCATION.          *   FILE 300
//*                       (This is Greg Price's improvement.)       *   FILE 300
//*                       (Fixed for 8-character TSO prefixes.)     *   FILE 300
//*                                                                 *   FILE 300
//*       SHOWSPC   1X -  SHOW THE SPACE ALLOCATION FOR DATASETS    *   FILE 300
//*                       ON A DISK.  CAN MASK FOR THE NAMES.       *   FILE 300
//*                       LOOK AT IT FOR ALL CAPABILITIES.          *   FILE 300
//*                                                                 *   FILE 300
//*       SHOWSS    3X -  DISPLAYS SUBSYSTEM VECTOR TABLE AND SEE   *   FILE 300
//*                       SUBSYSTEMS CURRENTLY ACTIVE.  OPTIONALLY  *   FILE 300
//*                       CAN RESET THE ADDRESS TO ZEROES IN CASE   *   FILE 300
//*                       SUBSYSTEM HAS ABENDED AND HAS NOT RESET   *   FILE 300
//*                       ADDRESS TO ZEROES.  IF ZERO CAPABILITY    *   FILE 300
//*                       IS USED THEN YOU MUST BE AUTHORIZED.      *   FILE 300
//*                       (Fixed for above 16M addresses - SBG)     *   FILE 300
//*                       (Fixed for 8-character userid support)    *   FILE 300
//*                                                                 *   FILE 300
//*       SOLICIT   1  -  MAKE YOUR 3270 TYPE TERMINAL LOOK LIKE    *   FILE 300
//*                       IT WAS LOGGED OFF AND BACK TO 'NETSOL'.   *   FILE 300
//*                       THINK OF YOUR OWN USES FOR THIS ONE.      *   FILE 300
//*                                                                 *   FILE 300
//*       SORTLNK   1X -  FRONT-END FOR SORT FROM TSO.  KEEPS FROM  *   FILE 300
//*                       GIVING SECURITY ACCESS FOR TSO CALL IF    *   FILE 300
//*                       SORT IS IN THE LINKLIST.                  *   FILE 300
//*                                                                 *   FILE 300
//*       SPFCOPY   1X -  INVOKER OF IEBCOPY INTERACTIVELY UNDER    *   FILE 300
//*                       'ISPF' MENU 3.1 IEBCOPY MUST BE           *   FILE 300
//*                       AUTHORIZED AND SPF IS NOT. (PROBLEMS)     *   FILE 300
//*                       THIS GIZMO GETS THE AUTHORIZATION THRU    *   FILE 300
//*                       THE SPFSVC.                               *   FILE 300
//*                                                                 *   FILE 300
//*       SPFSVC    1  -  SVC TO ALLOW ISPF/PDF MENU 3.1 COMPRESS.  *   FILE 300
//*                                                                 *   FILE 300
//*       SPZAP     1  -  TSO CP TO INVOKE 'AMASPZAP'               *   FILE 300
//*                                                                 *   FILE 300
//*       SUBMITX   2Y -  SUB FROM TSO JOB TO SECONDARY JES2.       *   FILE 300
//*                       IBM SAYS YOU CAN'T DO IT.  BILL           *   FILE 300
//*                       GODFREY, PRC CORP HAS IT WORKING.         *   FILE 300
//*                       INCLUDED IN THIS CMD ARE ALIASES OF       *   FILE 300
//*                       OUTPUTX, STATUSX, AND CANCELX.  READ      *   FILE 300
//*                       COMMENTS IN THE BEGINNING OF CODE FOR     *   FILE 300
//*                       SOME POINTS OF INTEREST.  SEE SRC FILE    *   FILE 300
//*                       FOR MEMBER JESXRDR FOR SUBMITING FROM     *   FILE 300
//*                       AN INTRDR TO A SECONDARY JES2.  ALL       *   FILE 300
//*                       NEEDS SOME REFINEMENT BUT IT WORKS SO     *   FILE 300
//*                       FAR.  IN MVS/XA THIS PROBABLY DOES NOT    *   FILE 300
//*                       WORK.                                     *   FILE 300
//*                                                                 *   FILE 300
//*       SYSDSN    1  -  GTELABS CMD LIST NAMES OF EVERYONE        *   FILE 300
//*                       WHO HAS A DSN ALLOCATED, OR IS WAITING    *   FILE 300
//*                       FOR ALLOC.  VERY USEFUL AFTER 'DATASET    *   FILE 300
//*                       IN USE' AND 'WAITING FOR DATASETS' MSGS.  *   FILE 300
//*                                                                 *   FILE 300
//*       SYSID     1X -  GETS MVS CONTROL BLK INTO ISPF VARIABLE,  *   FILE 300
//*                       CAN BE USED IN ISPF DIALOG.  DONE IN ALC. *   FILE 300
//*                       IS CODED 'REENTRANT'!  YOU WILL SEE HOW.  *   FILE 300
//*                                                                 *   FILE 300
//*       SYSOUT99  1  -  SUBPROGRAM.  ALLOCATES A SYSOUT DATASET.  *   FILE 300
//*                                                                 *   FILE 300
//*       SYSTEM    3X -  DISPLAY THE SYSTEM RELEASE, CPU ID,       *   FILE 300
//*                       MAIN STORAGE AMOUNT ONLINE & SYSTEM       *   FILE 300
//*                       IPL'D & IF RUNNING AS VM GUEST.           *   FILE 300
//*                                                                 *   FILE 300
//*       S99DAIR   1  -  SUBPROGRAM.  ENHANCED VERSION OF IKJDAIR  *   FILE 300
//*                       FOR ALLOCATING '0008' (DSNAME),           *   FILE 300
//*                       '001C' (TERMINAL), AND '0030' (SYSOUT).   *   FILE 300
//*                                                                 *   FILE 300
//*       TO        1X -  SHORTHAND FOR DOING TSO SEND CMD.  DON'T  *   FILE 300
//*                       HAVE TO WORRY ABOUT QUOTES.  EX AS        *   FILE 300
//*                       FOLLOWS:                                  *   FILE 300
//*                         TO TSOUSER WE AIN'T DUMMIES, LET'S QUIT *   FILE 300
//*                       (Fixed for 8-character TSO userids)       *   FILE 300
//*                       (Fixed for issuing under ISPF, which      *   FILE 300
//*                        requires an even number of quotes in     *   FILE 300
//*                        a message.  This version reduces two     *   FILE 300
//*                        consecutive single quotes to one.        *   FILE 300
//*                        The old version is here also, as member  *   FILE 300
//*                        TO00, so if you don't like reducing      *   FILE 300
//*                        two quotes to one, you can use that      *   FILE 300
//*                        version of TO.)                          *   FILE 300
//*                                                                 *   FILE 300
//*       TPRINT    1Y -  DISPLAYS A MSG FROM A CLIST AT A          *   FILE 300
//*                       TERMINAL.  OBSOLETE IN MVS TSO BUT        *   FILE 300
//*                       WORKS AND IS FAST.                        *   FILE 300
//*                                                                 *   FILE 300
//*       TSOCP     1  -  PROGRAM TO EXECUTE A TSO COMMAND FROM     *   FILE 300
//*                       ANY LIBRARY ALLOCATED TO THE DDNAME OF    *   FILE 300
//*                       TASKLIB.                                  *   FILE 300
//*                                                                 *   FILE 300
//*       TSOEXEC   1  -  USE THIS RYO VERSION OF TSOEXEC IF YOU DO *   FILE 300
//*                       NOT HAVE TSO/E R2.  THANKS TO PAUL BANKS, *   FILE 300
//*                       ALLERGAN PHARMACEUTICALS IN IRVINE, CA.   *   FILE 300
//*                                                                 *   FILE 300
//*       UADLST       -  TSO COMMAND CONVERTED FROM UADLIST BATCH  *   FILE 300
//*                       PROGRAM ON FILE 316. LISTS CONTENTS OF    *   FILE 300
//*                       SYS1.UADS DATASET OR A COPY OF IT.        *   FILE 300
//*                       (WORKS ON Z/OS.)                          *   FILE 300
//*                                                                 *   FILE 300
//*       UADS      1  -  LIST A UADS ENTRY LEAVING OUT PASSWORD.   *   FILE 300
//*                       GOOD FOR TECH SUPPORT PEOPLE.             *   FILE 300
//*                       NOTE:  MUST BE ABLE TO HAVE               *   FILE 300
//*                       'SYS1.UADS' ALLOCATION PRIVILEGES THOUGH. *   FILE 300
//*                       (FIXED FOR Z/OS.)                         *   FILE 300
//*                       AFTER LOOKING AT ALL THE USERIDS IN UADS  *   FILE 300
//*                       WITH UADLST, YOU CAN DRILL DOWN TO GET    *   FILE 300
//*                       MORE INFO BY USING UADS AFTERWARDS.       *   FILE 300
//*                                                                 *   FILE 300
//*       UADS@     1  -  MACRO NEEDED FOR ASSEMBLY OF UADS.        *   FILE 300
//*                                                                 *   FILE 300
//*       UCBSCAN   2X -  NEAT CODE LOOKING AT MVS/XA UCB, GOOD     *   FILE 300
//*                       EXAMPLES HOW TO LOOK AT UCB/CHPIDS/PATHS  *   FILE 300
//*                       AND OTHER GOOD THINGS.  CAME FROM MARK    *   FILE 300
//*                       V. HEDGES.                                *   FILE 300
//*                                                                 *   FILE 300
//*       UNITS     4  -  TSO CMD SHOWS UNIT NAMES IN DEVICE NAME   *   FILE 300
//*                       TABLE, CHANNEL-UNIT-ADDR ASSOCIATED WITH  *   FILE 300
//*                       EACH UNIT NAME. LOOK IN THE CODE FOR SOME *   FILE 300
//*                       AUTH CHECKING AND DISABLE IN YOUR SHOP.   *   FILE 300
//*                 (MVS/XA, MVS/ESA 3 VERSION FROM MORRIS KARLIN)  *   FILE 300
//*                                                                 *   FILE 300
//*        (THERE ARE SEVERAL VERSIONS OF THE UNITS COMMAND HERE.   *   FILE 300
//*          UNITS01 IS FOR MVS/370 SYSTEMS.  UNITS02 IS FOR XA     *   FILE 300
//*          THRU ESA 4 WITHOUT DYNAMIC UCB'S.  UNITS IS FOR        *   FILE 300
//*          z/OS WITH DYNAMIC UCB SUPPORT AND 4-DIGIT DEVICE       *   FILE 300
//*          NUMBERS.                                               *   FILE 300
//*                                                                 *   FILE 300
//*       VSFORT    1X -  VS/FORTRAN PROMPTER FROM JOHN SILL OF     *   FILE 300
//*                       'CHICAGO BRIDGE & IRON' (HE IS NOT IN     *   FILE 300
//*                       CHICAGO, DOESN'T BUILD BRIDGES, AND DON'T *   FILE 300
//*                       WORK WITH IRON).  THANKS JOHN !!!!!!!!!!  *   FILE 300
//*                                                                 *   FILE 300
//*       VTOC      1  -  ONE OF THE SLICKEST CMDS FOR FINDING OUT  *   FILE 300
//*                       WHAT IS ON A DISK.  LOOK AT THE HELP FOR  *   FILE 300
//*                       THE COMPLETE INFORMATION.                 *   FILE 300
//*                                                                 *   FILE 300
//*       VSMRGN    1  -  SHOWS ADDRESS AND SIZE OF PRIVATE STORAGE *   FILE 300
//*                       BOTH BELOW THE LINE, AND ABOVE THE LINE.  *   FILE 300
//*                       (TSO command that simulates the VSMRGEN   *   FILE 300
//*                       macro action and displays the results.)   *   FILE 300
//*                                                                 *   FILE 300
//*       WHATIF    2  -  ALLOWS CONDITIONAL EXECUTION OF           *   FILE 300
//*                       TSOCMD FROM A CLIST BASED ON ANY OF       *   FILE 300
//*                          THE COMBINATIONS:                      *   FILE 300
//*                       1. WHETHER A FILE IS ALLOCATED.           *   FILE 300
//*                       2. WHETHER A FILE IS ALLOCATED TO A       *   FILE 300
//*                          SPECIFIC FILE NAME                     *   FILE 300
//*                       3. WHETHER A FILE IS CATALOGED.           *   FILE 300
//*                       4. WHETHER TWO STRINGS BEAR A SPECIFIED   *   FILE 300
//*                          RELATION TO EACH OTHER.                *   FILE 300
//*                                                                 *   FILE 300
//*       WHOHAS    2Y -  AFDSC MODIFIED AND CORRECTED.             *   FILE 300
//*                       DISCOVERED BUG, DID NOT SHOW THE ENQ      *   FILE 300
//*                       CHAIN PROPERLY.  IT STOPPED AFTER THE     *   FILE 300
//*                       1ST OCCURENCE OF DISP=OLD.  WILL SHOW     *   FILE 300
//*                       'WHOHAS' FILE ALLOCATED & THE ENQ CHAIN.  *   FILE 300
//*                                                                 *   FILE 300
//*       WTC       2X -  EVER SEND MSG TO OPERATOR WITH SEND AND   *   FILE 300
//*                       THEY CLAIM IT NEVER CAME (ROLLED OFF      *   FILE 300
//*                       THE SCREEN).  NOW SEND THE MSG AND RING   *   FILE 300
//*                       THE CONSOLE ALARM, HIGHLIGHT THE MSG,     *   FILE 300
//*                       AND MAKE IT NON-ROLLABLE !!!!!!!!!        *   FILE 300
//*                                                                 *   FILE 300
//*       ZAP          -  UPDATED VERSION OF UCLA FULL SCREEN ZAP   *   FILE 300
//*                       PROGRAM FROM CBT FILE 134.  UPDATES ARE   *   FILE 300
//*                       FROM BRUCE BORDONARO AND GREG PRICE.      *   FILE 300
//*                       OLDER VERSION IS CALLED ZAPO.  (WHY USE   *   FILE 300
//*                       OLD STUFF WHEN MUCH NEWER STUFF IS        *   FILE 300
//*                       NOW AVAILABLE ?)                          *   FILE 300
//*                                                                 *   FILE 300
```
