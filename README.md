# CBT183
Converted to GitHub via [cbt2git](https://github.com/wizardofzos/cbt2git)

This is still a work in progress. 
Due to amazing work by Alison Zhang and Jake Choi repos are no longer deleted.

```
//***FILE 183 is from Gilbert Saint-flour.  This is a collection    *   FILE 183
//*           of utilities and other highly useful things for       *   FILE 183
//*           system programmers to have.  The following is a       *   FILE 183
//*           summary of this file's contents.                      *   FILE 183
//*                                                                 *   FILE 183
//*           We are hoping to add to this file from time to time   *   FILE 183
//*           from Gilbert's personal libraries, to perpetuate his  *   FILE 183
//*           memory, and to show our enormous gratefulness to him  *   FILE 183
//*           for his devoted and skilled work.                     *   FILE 183
//*                                                                 *   FILE 183
//*           Sam Golob is working on Gilbert's free programs.      *   FILE 183
//*           Carlos Aguilera is working on Gilbert's programs      *   FILE 183
//*           written for pay.  See www.gsf-soft.com for both.      *   FILE 183
//*                                                                 *   FILE 183
//*           Please address all questions and inquiries to         *   FILE 183
//*           Sam Golob.  Thanks.                                   *   FILE 183
//*                                                                 *   FILE 183
//*           email:  sbgolob@cbttape.org                           *   FILE 183
//*                                                                 *   FILE 183
//*           or to Carlos Aguilera....                             *   FILE 183
//*                                                                 *   FILE 183
//*           email:  carlos@gsf-soft.com                           *   FILE 183
//*                                                                 *   FILE 183
//*              --> LAST UPDATE: 15Dec20 (for CBT500)              *   FILE 183
//*                                                                 *   FILE 183
//*                .--------------------------------.               *   FILE 183
//*                |  CBT TAPE - Index of file 183  |               *   FILE 183
//*                '--------------------------------'               *   FILE 183
//*                                                                 *   FILE 183
//*        website:  http://gsf-soft.com/Freeware                   *   FILE 183
//*                                                                 *   FILE 183
//*  ----------------- TSO and ISPF commands -------------------    *   FILE 183
//*                                                                 *   FILE 183
//*  ADDTRK    The ADDTRK EDIT macro (written in REXX) that         *   FILE 183
//*            invokes PDS86 to add a new extent to the PDS         *   FILE 183
//*            being edited.                                        *   FILE 183
//*                                                                 *   FILE 183
//*  BR        TSO command - Browse most data sets under            *   FILE 183
//*            ISPF/PDF, using BRIF.  Supports VSAM, BDAM,          *   FILE 183
//*            multi-volume, RECFM=VBS, BLKSIZE=0, etc.             *   FILE 183
//*                                                                 *   FILE 183
//*            To use it, just enter BR instead of B on the         *   FILE 183
//*            Data Set List utility screen.  BR has its own        *   FILE 183
//*            point-and-shoot capability and can grab a dsname     *   FILE 183
//*            on the screen, wherever the cursor is located.       *   FILE 183
//*                                                                 *   FILE 183
//*  CLS       A 5-line "clear screen" command for TSO              *   FILE 183
//*                                                                 *   FILE 183
//*  COMPRCMD  TSO Command Processor written in Assembler           *   FILE 183
//*                                                                 *   FILE 183
//*            Compress a PDS with DISP=SHR using standard ISPF     *   FILE 183
//*            and LINK-EDIT protection.  Uses the TSO/E service    *   FILE 183
//*            routine to invoke IEBCOPY and, therefore, does not   *   FILE 183
//*            require any authorization of its own.  Accepts       *   FILE 183
//*            generic dsnames (such as GSFSOFT.*) and offers a     *   FILE 183
//*            few other options.                                   *   FILE 183
//*                                                                 *   FILE 183
//*  COMPRESS  The COMPRESS EDIT macro (written in REXX) that       *   FILE 183
//*            allows you to compress the PDS you're editing        *   FILE 183
//*            just by typing "COMPRESS" on the command line.       *   FILE 183
//*                                                                 *   FILE 183
//*  CONCAT    A REXX exec to add a data set to a concatenation.    *   FILE 183
//*                                                                 *   FILE 183
//*  CUT       REXX EDIT Macro - CUT & PASTE package                *   FILE 183
//*  PASTE     REXX EDIT Macro - CUT & PASTE package                *   FILE 183
//*  CUTPGM    Assembler program used in CUT & PASTE.               *   FILE 183
//*  CUTHLP1   Help screen for CUT                                  *   FILE 183
//*  CUTHLP2   Help screen for PASTE                                *   FILE 183
//*                                                                 *   FILE 183
//*            My own version of a classic.                         *   FILE 183
//*            Requires MVS/ESA 4.2.2 or above.                     *   FILE 183
//*            Uses data spaces, name/token pairs and compression.  *   FILE 183
//*            Supports multiple clip-boards and the APPEND option. *   FILE 183
//*                                                                 *   FILE 183
//*  DAHANDBK  Program to create a "handbook" of control block      *   FILE 183
//*            displacements from the assembly of mapping           *   FILE 183
//*            macros.                                              *   FILE 183
//*  DAHANDJ   Sample job to create a handbook.                     *   FILE 183
//*                                                                 *   FILE 183
//*  DSLIST    REXX exec - Point-and-shoot Dataset List Utility     *   FILE 183
//*                                                                 *   FILE 183
//*            This REXX program allows you to invoke the data      *   FILE 183
//*            set list function of ISPF/PDF (option 3.4) with      *   FILE 183
//*            the DSNAME LEVEL field preset to the data set name   *   FILE 183
//*            under which the cursor is currently positionned.     *   FILE 183
//*                                                                 *   FILE 183
//*            DSLIST may be invoked from any ISPF screen simply    *   FILE 183
//*            by typing:                                           *   FILE 183
//*                                                                 *   FILE 183
//*               TSO %DSLIST                                       *   FILE 183
//*                                                                 *   FILE 183
//*            on the command line, then by moving the cursor       *   FILE 183
//*            under a data set name on your screen and pressing    *   FILE 183
//*            "enter".  You may also define it as a command in     *   FILE 183
//*            the ISPF command table, or set it up as a PFK.       *   FILE 183
//*                                                                 *   FILE 183
//*  DSNLIST   TSO command - returns in &var the dsnames            *   FILE 183
//*                          allocated to &ddn                      *   FILE 183
//*            Example:                                             *   FILE 183
//*                                                                 *   FILE 183
//*              ALLOC DD(SYSPROC) SHR -                            *   FILE 183
//*                    DS('IPO1.CMDPROC' 'GSFSOFT.CLIST')           *   FILE 183
//*              DSNLIST DDNAME(SYSPROC) SETVAR(VAR2)               *   FILE 183
//*                                                                 *   FILE 183
//*              is equivalent to:                                  *   FILE 183
//*                                                                 *   FILE 183
//*              SET VAR2 = 'IPO1.CMDPROC' 'GSFSOFT.CLIST'          *   FILE 183
//*                                                                 *   FILE 183
//*  EXECPGM   TSO command - invoke a utility program or compiler   *   FILE 183
//*            with an alternate ddname list, as follows:           *   FILE 183
//*               EXECPGM IEV90           +                         *   FILE 183
//*                 PARM(NOOBJECT,NODECK,NOXREF,NORLD) +            *   FILE 183
//*                 SYSIN(TEMPWK2)        +                         *   FILE 183
//*                 SYSUT1(TEMPWK1)       +                         *   FILE 183
//*                 SYSLIB(ASMLIB)        +                         *   FILE 183
//*                 SYSPRINT(ASMH$PRT)    +                         *   FILE 183
//*                 STEPLIB(LINKLIST)                               *   FILE 183
//*                                                                 *   FILE 183
//*  EXECUTE   REXX EXEC - Run an in-stream EXEC or CLIST in a TSO  *   FILE 183
//*            batch job, or execute EDIT data as a CLIST or EXEC.  *   FILE 183
//*                                                                 *   FILE 183
//*  FASTPATH  This assembler program allows the use of fast-path   *   FILE 183
//*            commands without requiring customization of the      *   FILE 183
//*            ISPF environment.                                    *   FILE 183
//*            Fastpath provides two types of functions:            *   FILE 183
//*            (Correct mistake in SHOWzOS ISPF table invocation)   *   FILE 183
//*                                                                 *   FILE 183
//*            1. Initialization                                    *   FILE 183
//*              a. add 20 fast-path commands to the user's         *   FILE 183
//*                 in-storage copy of ISPCMDS                      *   FILE 183
//*              b. pre-load specific modules to enhance            *   FILE 183
//*                 performance and allow access from a private     *   FILE 183
//*                 LOAD library                                    *   FILE 183
//*              c. issue STIMER to prevent S522 time-out abends    *   FILE 183
//*            2. Processing                                        *   FILE 183
//*              a. invoke EDIT, BROWSE, VIEW, WorkPlace and SDSF   *   FILE 183
//*                 with the appropriate NEWAPPL parameter          *   FILE 183
//*              b. store and retrieve parameters associated        *   FILE 183
//*                 with user-specified tags                        *   FILE 183
//*              c. retrieve a dsname under which the cursor        *   FILE 183
//*                 is positioned and invoke EDIT, BROWSE,          *   FILE 183
//*                 VIEW or the Workplace                           *   FILE 183
//*              d. Edit your ISPCTLn or SPFTEMPn.CNTL data set     *   FILE 183
//*              e. View a member in SYS1.MACLIB or SYS1.MODGEN     *   FILE 183
//*              f. TSO Full-screen                                 *   FILE 183
//*              g. misc others                                     *   FILE 183
//*                                                                 *   FILE 183
//*  FASTPDOC  Documentation for the FASTPATH utility               *   FILE 183
//*            http://gsf-soft.com/Freeware/FASTPATH.shtml          *   FILE 183
//*                                                                 *   FILE 183
//*  FASTNOTE  Note from Sam Golob about invoking FASTPATH          *   FILE 183
//*                                                                 *   FILE 183
//*  FASTP149  Previous version of FASTPATH utility                 *   FILE 183
//*                                                                 *   FILE 183
//*  FILE183   CLIST to provide an easy access to REXX execs and    *   FILE 183
//*            programs distributed in this library                 *   FILE 183
//*            http://gsf-soft.com/Freeware/FILE183.shtml           *   FILE 183
//*                                                                 *   FILE 183
//*  FREEDIR   The FREEDIR EDIT macro (written in REXX) invokes     *   FILE 183
//*            PDS86 to add or delete directory blocks to change    *   FILE 183
//*            the size of the directory of the PDS being edited.   *   FILE 183
//*                                                                 *   FILE 183
//*  FSHELP    REXX EXEC - Full-screen TSO HELP which uses STEMVIEW *   FILE 183
//*            to display the output produced by the TSO HELP cmd.  *   FILE 183
//*                                                                 *   FILE 183
//*  FULLDSN   REXX Function - return the real dsname of an alias   *   FILE 183
//*            or the fully-qualified dsname from a relative        *   FILE 183
//*            generation.                                          *   FILE 183
//*                                                                 *   FILE 183
//*  FTP       REXX EDIT Macro - Transmit the data being edited     *   FILE 183
//*            using text-mode FTP                                  *   FILE 183
//*                                                                 *   FILE 183
//*  IKJEFLN2  TSO/E Logon Exit - enable the Reconnect option       *   FILE 183
//*            in the TN3270 environment.                           *   FILE 183
//*                                                                 *   FILE 183
//*  INITKSDS  Initialize a KSDS after it's been DEFINE'd           *   FILE 183
//*                                                                 *   FILE 183
//*            This program prevents OPEN from failing when         *   FILE 183
//*            opening with MACRF=(IN,OUT) or STRNO=2 a KSDS        *   FILE 183
//*            that has just been defined.  Can be invoked as       *   FILE 183
//*            a batch program, a TSO command, or a sub-routine.    *   FILE 183
//*                                                                 *   FILE 183
//*  IPADDR    REXX exec - retrieve the IP address associated with  *   FILE 183
//*            a VTAM terminal using NETSTAT TELNET.                *   FILE 183
//*                                                                 *   FILE 183
//*  IRXEHCIR  Interface to IKJEHCIR for REXX and COBOL             *   FILE 183
//*                                                                 *   FILE 183
//*            This small assembler program allows a REXX EXEC      *   FILE 183
//*            or a COBOL program to invoke IKJEHCIR, the TSO/E     *   FILE 183
//*            Catalog Information Routine.                         *   FILE 183
//*                                                                 *   FILE 183
//*  ISPTASK   Program - prevent S522 abends while in ISPF          *   FILE 183
//*                                                                 *   FILE 183
//*            Just link it into your ISPLLIB or STEPLIB, then      *   FILE 183
//*            re-enter ISPF, and you won't time out any more.      *   FILE 183
//*                                                                 *   FILE 183
//*            Also preloads some ISRxxxx modules for               *   FILE 183
//*            performance, even if they're in PLPA (YES,           *   FILE 183
//*            in ESA 4.3, you can pre-load PLPA modules!!)         *   FILE 183
//*                                                                 *   FILE 183
//*  ISREDIT2  Program - speed up EDIT macros                       *   FILE 183
//*                                                                 *   FILE 183
//*            Executed once at the beginning of an EDIT macro.     *   FILE 183
//*                                                                 *   FILE 183
//*  LC        REXX EXEC - Full-screen IDCAMS LISTCAT               *   FILE 183
//*                                                                 *   FILE 183
//*            This TSO/ISPF REXX EXEC invokes IDCAMS then          *   FILE 183
//*            invokes STEMVIEW to display the output.              *   FILE 183
//*                                                                 *   FILE 183
//*            To use it, just enter LC as a line command on the    *   FILE 183
//*            Data Set List (3.4) or the WorkPlace (11) Utility    *   FILE 183
//*            screens                                              *   FILE 183
//*                                                                 *   FILE 183
//*  LCAT      TSO command - Full-screen IDCAMS LISTCAT             *   FILE 183
//*                                                                 *   FILE 183
//*            This TSO/ISPF command invokes IDCAMS then            *   FILE 183
//*            uses BRIF to display the output.                     *   FILE 183
//*                                                                 *   FILE 183
//*            To use it, just enter LCAT as a line command         *   FILE 183
//*            on the Data Set List Utility screen.                 *   FILE 183
//*                                                                 *   FILE 183
//*  LCAT92    TSO command - Full-screen IDCAMS LISTCAT             *   FILE 183
//*            1992 version of LCAT for OS/390 R2 and older         *   FILE 183
//*                                                                 *   FILE 183
//*  LLIBDEF1  Prevent some S806-4 abends when using LIBDEF with    *   FILE 183
//*            ISPLLIB                                              *   FILE 183
//*                                                                 *   FILE 183
//*            This program allows you to pre-load a REUS or        *   FILE 183
//*            RENT module from a LOAD library defined via          *   FILE 183
//*            LIBDEF.  This can prevent S806-4 abends that         *   FILE 183
//*            occur when a program that is not LIBDEF-aware        *   FILE 183
//*            tries to access another program via LOAD or LINK.    *   FILE 183
//*                                                                 *   FILE 183
//*  LISTDSI   REXX EXEC - Display output of LISTDSI function       *   FILE 183
//*                                                                 *   FILE 183
//*            This EXEC helps the REXX programmer implement        *   FILE 183
//*            the LISTDSI function by displaying the value of      *   FILE 183
//*            all of the variables returned by LISTDSI for the     *   FILE 183
//*            specified data set, as well as providing the         *   FILE 183
//*            syntax, return codes and reason codes in the         *   FILE 183
//*            form of comments at the end of the source.           *   FILE 183
//*                                                                 *   FILE 183
//*  LOCKTERM  TSO command written in assembler.                    *   FILE 183
//*            Lock TSO terminal, enter LOGON password to unlock.   *   FILE 183
//*            (Fixed April 2016 by Garry Green.)                   *   FILE 183
//*            (Adjusted to show 8-character userids.)              *   FILE 183
//*                                                                 *   FILE 183
//*  LPA24     REXX EXEC - Display PLPA usage below the 16MB line   *   FILE 183
//*                                                                 *   FILE 183
//*  LPR       REXX EDIT Macro - Print the data being edited        *   FILE 183
//*            using TCP/IP's LPR command                           *   FILE 183
//*                                                                 *   FILE 183
//*  LVL       REXX EDIT macro - Compress Level Numbers for         *   FILE 183
//*            FB-80 PDS members with STATS ON and NUMBER STD.      *   FILE 183
//*                                                                 *   FILE 183
//*            LVL reuses "gas levels", i.e. levels which           *   FILE 183
//*            are not used in any record in the member,            *   FILE 183
//*            and adjusts pos 79-80 of the records accordingly.    *   FILE 183
//*                                                                 *   FILE 183
//*            If the macro invocation includes a number,           *   FILE 183
//*            then levels up to the specified number are           *   FILE 183
//*            reset to zero.                                       *   FILE 183
//*                                                                 *   FILE 183
//*  NEWAPPL   REXX EXEC - Start a new ISPF application using       *   FILE 183
//*            LIBDEF and ALTLIB.                                   *   FILE 183
//*                                                                 *   FILE 183
//*  OBEYFILE  EDIT Macro written in REXX - Allows the TCP/IP       *   FILE 183
//*            administrator to use the data being edited as        *   FILE 183
//*            input to the TCP/IP OBEYFILE command without         *   FILE 183
//*            having to SAVE it.                                   *   FILE 183
//*                                                                 *   FILE 183
//*  RESET5    Initial EDIT macro that issues a "RESET" command     *   FILE 183
//*                                                                 *   FILE 183
//*            Type "IMACRO !RESET" once, and you won't be          *   FILE 183
//*            bothered by these annoying messages anymore.         *   FILE 183
//*                                                                 *   FILE 183
//*  REXXTRY   TSO command processor written in assembler.          *   FILE 183
//*                                                                 *   FILE 183
//*            REXXTRY can be used in a CLIST or in ISPF to         *   FILE 183
//*            execute a one-line REXX exec as a sub-routine.       *   FILE 183
//*            The REXX exec can be a single REXX instruction or    *   FILE 183
//*            multiple instructions separated by semi-colons.      *   FILE 183
//*                                                                 *   FILE 183
//*            REXXTRY can also be invoked in batch mode, in which  *   FILE 183
//*            case the REXX code is not specified as an argument   *   FILE 183
//*            to the command, but consists on all the input lines  *   FILE 183
//*            present after the REXXTRY command in SYSTSIN.        *   FILE 183
//*                                                                 *   FILE 183
//*  ROUTE     REXX EDIT Macro - Print the data being edited.       *   FILE 183
//*  ROUTEPGM  Assembler program used in ROUTE to speed things up   *   FILE 183
//*  ROUTEHLP  Help screen                                          *   FILE 183
//*                                                                 *   FILE 183
//*            This edit macro writes the data you're editing to    *   FILE 183
//*            a SYSOUT data set, with the CLASS and DEST you       *   FILE 183
//*            specify, a title line and 60 lines per page.         *   FILE 183
//*            Works with EDIF because what gets printed is the     *   FILE 183
//*            data being edited, NOT the data stored on disk.      *   FILE 183
//*                                                                 *   FILE 183
//*  RXSMS     Assembler program; can be invoked in a REXX exec     *   FILE 183
//*            to retrieve information from the SMS sub-system      *   FILE 183
//*            or from a volume's VTOC.                             *   FILE 183
//*                                                                 *   FILE 183
//*  SFE       REXX program to invoke the Search-For Extended       *   FILE 183
//*            utility.  Can be invoked from the Data Set List      *   FILE 183
//*            panel or as an EDIT macro.                           *   FILE 183
//*                                                                 *   FILE 183
//*  SHOWDASD  ISPF Dialog to display on-line DASD devices.         *   FILE 183
//*            (fixed for 64-bit ULUT - ULUT Type 3)                *   FILE 183
//*            (also works on older systems, so it supersedes       *   FILE 183
//*            the older version - member SHOWDAS1)                 *   FILE 183
//*                                                                 *   FILE 183
//*  SHOWDPNL  Requires the RXSMS program.                          *   FILE 183
//*                                                                 *   FILE 183
//*  SHOWVTOC  Panel for option V                                   *   FILE 183
//*                                                                 *   FILE 183
//*  SHOWJPAQ  TSO command - Display contents of Job Pack Area      *   FILE 183
//*            Queue (JPAQ)                                         *   FILE 183
//*                                                                 *   FILE 183
//*  SHOWTIOT  REXX exec - Display contents of Task Input-Output    *   FILE 183
//*            Table (TIOT)                                         *   FILE 183
//*                                                                 *   FILE 183
//*  STEMEDIT  REXX sub-routine written in assembler.               *   FILE 183
//*            Browse, View or Edit stem variables using BRIF,      *   FILE 183
//*            VIIF or EDIF.  A nice addition to OUTTRAP.           *   FILE 183
//*            View data from the stack also. ISPF V5 only.         *   FILE 183
//*                                                                 *   FILE 183
//*     Note:  An update to STEMEDIT, and some other modificatons,  *   FILE 183
//*            was written by Rainer Nowak, and is included in      *   FILE 183
//*            this pds, as member STEMEDI#.  This member was also  *   FILE 183
//*            repeated on the CBT Tape, as File 895.               *   FILE 183
//*                                                                 *   FILE 183
//*  STEMVIEW  REXX sub-routine written in assembler.               *   FILE 183
//*            Browse or View stem variables using BRIF or EDIF.    *   FILE 183
//*            View data from the stack also. ISPF V2, V3, V4.      *   FILE 183
//*                                                                 *   FILE 183
//*  SWAREQ    REXX exec - Convert an SVA to a 31-bit address       *   FILE 183
//*                                                                 *   FILE 183
//*  SWAREQ22  REXX exec - Convert an SVA to a 31-bit address on    *   FILE 183
//*            a z/OS 2.2 system or higher.  (from Don Poitras)     *   FILE 183
//*                                                                 *   FILE 183
//*  TALLY     REXX exec for ISPF 3.4 - Display the total number of *   FILE 183
//*            tracks used up by the data sets on the DSLIST panel. *   FILE 183
//*                                                                 *   FILE 183
//*  TLMS      Display a VMF record under PDF 3.4                   *   FILE 183
//*                                                                 *   FILE 183
//*            This program reads the VMF record for the            *   FILE 183
//*            first volume of a tape data set, formats it          *   FILE 183
//*            pretty much like the CATLTSO command, then           *   FILE 183
//*            invokes BRIF to display the result.  May only        *   FILE 183
//*            be used as a line command on the Data Set            *   FILE 183
//*            List panel (Option 3.4 of ISPF/PDF).                 *   FILE 183
//*                                                                 *   FILE 183
//*  TMS       Display a TMC record under PDF 3.4                   *   FILE 183
//*            Same as TLMS, but for CA1/TMS 5.0                    *   FILE 183
//*                                                                 *   FILE 183
//*  VALLOC    Generate ALLOCATE commands for data set list         *   FILE 183
//*                                                                 *   FILE 183
//*            EDIT macro written in REXX.  Reads a list of data    *   FILE 183
//*            set names starting in pos 1 of each line and         *   FILE 183
//*            generates a set of corresponding ALLOCATE commands.  *   FILE 183
//*                                                                 *   FILE 183
//*  VARS      TSO/ISPF command written in REXX.                    *   FILE 183
//*            Display in-storage ISPF vars.                        *   FILE 183
//*                                                                 *   FILE 183
//*  VDL       TSO/ISPF command written in REXX.  VIEW Data set     *   FILE 183
//*            List: makes the list of data set created by DSLIST   *   FILE 183
//*            available as data in a VIEW session.                 *   FILE 183
//*                                                                 *   FILE 183
//*  VML       TSO/ISPF command - Read the directory of the         *   FILE 183
//*            specified PDS and VIEW the Member List               *   FILE 183
//*                                                                 *   FILE 183
//*  VSAMVIEW  TSO/ISPF command - View a VSAM data set using VIIF   *   FILE 183
//*                                                                 *   FILE 183
//*  VSAMVW95  1995 version of VSAMVIEW for ISPF V2, V3 and V4.     *   FILE 183
//*                                                                 *   FILE 183
//*  VSAVE     ISPF EDIT macro - Save a member in VIEW mode         *   FILE 183
//*                                                                 *   FILE 183
//*  WHEREIS   REXX EXEC - Look for all occurences of a member in   *   FILE 183
//*            the libraries currently allocated to your TSO        *   FILE 183
//*            session.  If multiple versions of the member are     *   FILE 183
//*            present in a concatenation, they are all shown,      *   FILE 183
//*            along with their ISPF stats, when present.           *   FILE 183
//*                                                                 *   FILE 183
//*  WHOAMI    REXX EXEC - Displays the user-ID and system-ID       *   FILE 183
//*            in large letters, plus a few other things            *   FILE 183
//*                                                                 *   FILE 183
//*  WP        REXX exec - Invoke the Work-place from DSLIST.       *   FILE 183
//*                                                                 *   FILE 183
//*  XDELETE   REXX exec - Delete data sets "en masse" using a      *   FILE 183
//*            generic filter such as "ABC*.D%.**.E%F*GH.*.TEMP".   *   FILE 183
//*                                                                 *   FILE 183
//*  XRENAME   REXX exec - Rename data sets "en masse"              *   FILE 183
//*                                                                 *   FILE 183
//*  XDEL      REXX EDIT macro - Delete current member              *   FILE 183
//*                                                                 *   FILE 183
//*  XREN      REXX EDIT macro - Rename current member              *   FILE 183
//*                                                                 *   FILE 183
//*  ------------------ Batch Programs --------------------------   *   FILE 183
//*                                                                 *   FILE 183
//*  BLKSIZE2  Scan a PDS and print the size of each block and      *   FILE 183
//*            the track balance                                    *   FILE 183
//*                                                                 *   FILE 183
//*            This is a batch program, for people interested       *   FILE 183
//*            in what a PDS looks like, from the inside.           *   FILE 183
//*                                                                 *   FILE 183
//*  BYPASSNQ  Assembler program.  Scratch or Rename a Data Set     *   FILE 183
//*            without SYSDSN ENQ                                   *   FILE 183
//*                                                                 *   FILE 183
//*            BYPASSNQ is a driver that allows you to run any      *   FILE 183
//*            utility program (such as IEHPROGM or IDCAMS) and     *   FILE 183
//*            bypass dsname ENQ that is normally performed by      *   FILE 183
//*            the DYNALLOC, SCRATCH and RENAME SVCs.               *   FILE 183
//*            This technique allows data sets to be deleted or     *   FILE 183
//*            renamed using standard MVS services and is fully     *   FILE 183
//*            compatible with indexed VTOCs and SMS.               *   FILE 183
//*                                                                 *   FILE 183
//*  CANMSGCL  Purge current job's held output after a few hours.   *   FILE 183
//*            Useful for those jobs that work OK 99% of the time   *   FILE 183
//*            (must be authorized)                                 *   FILE 183
//*                                                                 *   FILE 183
//*            Example:                                             *   FILE 183
//*                                                                 *   FILE 183
//*              //MYJOB    JOB ACCT#,CLASS=A,MSGCLASS=X            *   FILE 183
//*              //COPY1   EXEC PGM=IEBCOPY                         *   FILE 183
//*              //...      DD   ...                                *   FILE 183
//*              //CONDPURG EXEC PGM=CANMSGCL,PARM=2,               *   FILE 183
//*              //              COND=(0,NE,COPY1)                  *   FILE 183
//*                                                                 *   FILE 183
//*              The number in the parm is a number of hours.       *   FILE 183
//*              If the 'COPY1' step ends at 10:28 with a           *   FILE 183
//*              return code equal to zero, the 'CONDPURG' step     *   FILE 183
//*              executes and issues the following command:         *   FILE 183
//*                                                                 *   FILE 183
//*                $TA,T=12.28,'$OJ01234,Q=X,CANCEL'                *   FILE 183
//*                                                                 *   FILE 183
//*  COB2JOB   Retrieve Job-related information in COBOL            *   FILE 183
//*                                                                 *   FILE 183
//*  COB2SYS   Retrieve System-related information in COBOL         *   FILE 183
//*                                                                 *   FILE 183
//*  COB2TSO   Issue TSO commands in COBOL                          *   FILE 183
//*                                                                 *   FILE 183
//*  CLEANUP   Assembler program.  Automatically searches the MVS   *   FILE 183
//*            catalog for non-GDG data sets that will be created   *   FILE 183
//*            in subsequent steps of your job and deletes them.    *   FILE 183
//*            HSM-migrated data sets are deleted with HDELETE.     *   FILE 183
//*                                                                 *   FILE 183
//*                  //MYJOB   JOB  acct#                           *   FILE 183
//*                  //*                                            *   FILE 183
//*                  //CLEANUP EXEC PGM=CLEANUP                     *   FILE 183
//*                  //*                                            *   FILE 183
//*                  //STEP1   EXEC PGM=MYPROG1                     *   FILE 183
//*                  //OUTDD    DD  DSN=MY.FILE1,DISP=(,CATLG)      *   FILE 183
//*                  //STEP2   EXEC PGM=MYPROG2                     *   FILE 183
//*                  //OUTDD    DD  DSN=MY.FILE2,DISP=(,CATLG)      *   FILE 183
//*                                                                 *   FILE 183
//*            Can also be executed as the LAST step of a job to    *   FILE 183
//*            delete non-GDG data sets that were created during    *   FILE 183
//*            job execution.                                       *   FILE 183
//*                                                                 *   FILE 183
//*  CMDJ      Send a JES2 command with the current job's number    *   FILE 183
//*            (must be authorized)                                 *   FILE 183
//*                                                                 *   FILE 183
//*            Example:                                             *   FILE 183
//*                                                                 *   FILE 183
//*               //PURGEJOB EXEC PGM=CMDJES2,PARM=P                *   FILE 183
//*                                                                 *   FILE 183
//*            If the current job's number is JOB01234,             *   FILE 183
//*            then the following command is issued:                *   FILE 183
//*                                                                 *   FILE 183
//*                  $PJ  01234                                     *   FILE 183
//*                                                                 *   FILE 183
//*  DCODADDR  Assembler module to convert an address passed by     *   FILE 183
//*            its invoker into a character string that indicates   *   FILE 183
//*            what module, CSECT within the module, and offset     *   FILE 183
//*            within the CSECT the address points to.              *   FILE 183
//*              DCODADDR uses the Binder API and can be invoked    *   FILE 183
//*            by recovery routines or any other modules.           *   FILE 183
//*                                                                 *   FILE 183
//*  DONTFAIL  Prevent job failure caused by uncataloged data       *   FILE 183
//*            sets (ESA only, must be authorized)                  *   FILE 183
//*                                                                 *   FILE 183
//*  GSFLKED   Front-end to the linkage editor to recover           *   FILE 183
//*            from SD37 on SYSLMOD (must be authorized)            *   FILE 183
//*                                                                 *   FILE 183
//*            This program may be invoked instead of the DFP       *   FILE 183
//*            linkage editor. It calls the linkage editor and,     *   FILE 183
//*            if an SD37 abend occurs, calls IEBCOPY to compress   *   FILE 183
//*            the SYSLMOD PDS, then calls the linkage editor       *   FILE 183
//*            again.                                               *   FILE 183
//*                                                                 *   FILE 183
//*            Another feature of this program is to                *   FILE 183
//*            conditionally append a PDS member to SYSLIN, if      *   FILE 183
//*            that member exists.                                  *   FILE 183
//*                                                                 *   FILE 183
//*  ISGECMON  Assemble and Link Job for SYS1.SAMPLIB(ISGECMON)     *   FILE 183
//*                                                                 *   FILE 183
//*            The ISGECMON program runs as a never ending task     *   FILE 183
//*            that checks dataset contention at periodic           *   FILE 183
//*            intervals and sends messages to TSO users asking     *   FILE 183
//*            them to free datasets that are causing contention.   *   FILE 183
//*                                                                 *   FILE 183
//*  JOBRLSE   Release a job by number (must be authorized)         *   FILE 183
//*                                                                 *   FILE 183
//*            This program issues a $A command to release a job    *   FILE 183
//*            previously submitted to JES2 with "TYPRUN=HOLD".     *   FILE 183
//*                                                                 *   FILE 183
//*            To prevent "multiple jobs found" conditions,         *   FILE 183
//*            this program uses the sub-system interface           *   FILE 183
//*            to inquire about the status of homonym jobs.         *   FILE 183
//*            Then, it issues a $A command with the job            *   FILE 183
//*            number of the first job found in the input           *   FILE 183
//*            queue in held status (for example: $A J1234).        *   FILE 183
//*                                                                 *   FILE 183
//*            Sample execution JCL:                                *   FILE 183
//*                                                                 *   FILE 183
//*              //RLSENEXT EXEC PGM=JOBRLSE,PARM=PAYROL22          *   FILE 183
//*                                                                 *   FILE 183
//*  LINKLLA   Link-edit and refresh LLA in a single step           *   FILE 183
//*            (MVS/ESA only, must be authorized)                   *   FILE 183
//*                                                                 *   FILE 183
//*            Invokes the linkage-editor, then issues LLACOPY      *   FILE 183
//*            for the member specified on the //SYSLMOD DD.        *   FILE 183
//*            If there is no //SYSLIN DD in the step's JCL,        *   FILE 183
//*            issues LLACOPY for the member on //SYSLMOD,          *   FILE 183
//*            or for all of the members in the //SYSLMOD           *   FILE 183
//*            library if no member name has been specified.        *   FILE 183
//*                                                                 *   FILE 183
//*  LOADMLPA  Load a reentrant module into the MLPA                *   FILE 183
//*            (must be authorized)                                 *   FILE 183
//*                                                                 *   FILE 183
//*            This program allows you to load a RENT module        *   FILE 183
//*            from an authorized library into the MLPA.            *   FILE 183
//*            Also supports the DELETE function to undo            *   FILE 183
//*            LOAD.  Invoker must have update authority to         *   FILE 183
//*            SYS1.PARMLIB.                                        *   FILE 183
//*                                                                 *   FILE 183
//*            This program has been designed to prevent jobs       *   FILE 183
//*            that accept multiple inputs from failing in the      *   FILE 183
//*            middle of the night because of a "typo" in a data    *   FILE 183
//*            set name.  When DONTFAIL detects that an input       *   FILE 183
//*            data set is not cataloged, it converts it to a       *   FILE 183
//*            null data set and allows the job to run with         *   FILE 183
//*            partial input.                                       *   FILE 183
//*                                                                 *   FILE 183
//*  PACKOFF   Unpack a file packed by ISPF/PDF or XEDIT            *   FILE 183
//*                                                                 *   FILE 183
//*            This is a sample program that reads                  *   FILE 183
//*            fixed-length records and unpacks them.               *   FILE 183
//*                                                                 *   FILE 183
//*  PLI2JOB   Retrieve Job-related information in PL/I             *   FILE 183
//*                                                                 *   FILE 183
//*  PLI2TSO   Issue TSO commands in PL/I                           *   FILE 183
//*                                                                 *   FILE 183
//*  RECALL    Batch program - Issues HRECALL commands for every    *   FILE 183
//*            migrated data sets used in subsequent steps of the   *   FILE 183
//*            JOB in which it is executed.  Pre-staging data       *   FILE 183
//*            sets in this manner reduces HSM tape mount           *   FILE 183
//*            activity.                                            *   FILE 183
//*                                                                 *   FILE 183
//*  SCANMODL  This assembler module loads a control-block map      *   FILE 183
//*            from SYS1.MIGLIB and returns the offset & length     *   FILE 183
//*            of a field.  It is used to write programs that       *   FILE 183
//*            access JES2 control blocks without using HASPSRC     *   FILE 183
//*            and consequently, are release-independent.           *   FILE 183
//*                                                                 *   FILE 183
//*  SVCUPDTE  Install a type-3 SVC routine (must be authorized)    *   FILE 183
//*                                                                 *   FILE 183
//*            This program installs an SVC routine from PLPA,      *   FILE 183
//*            MLPA, or from an authorized library.                 *   FILE 183
//*            The installation can be permanent or temporary.      *   FILE 183
//*            If the installation is temporary, SVCUPDTE waits     *   FILE 183
//*            until a STOP or CANCEL command is issued, then       *   FILE 183
//*            restores the old SVC entry and terminates.           *   FILE 183
//*                                                                 *   FILE 183
//*            PARM=(nnn,mmmmmmm,hhmm,userid)                       *   FILE 183
//*                                                                 *   FILE 183
//*              nnn is the SVC number you want to install;         *   FILE 183
//*              you must specify a 3-digit number                  *   FILE 183
//*                                                                 *   FILE 183
//*              mmmmmmmm is the name of a load module (or alias)   *   FILE 183
//*              that you want to install as SVC nnn;  it MUST      *   FILE 183
//*              come from an authorized library (STEPLIB or        *   FILE 183
//*              link-list)                                         *   FILE 183
//*                                                                 *   FILE 183
//*              hhmm is the optional automatic shut-down time,     *   FILE 183
//*              in 24-hour clock format.  When the specified       *   FILE 183
//*              time is reached, SVCUPDTE automatically stops.     *   FILE 183
//*                                                                 *   FILE 183
//*              userid is the optional userid that will be given   *   FILE 183
//*              access to the new SVC.  Jobs submitted by other    *   FILE 183
//*              users will keep on using the old SVC.              *   FILE 183
//*                                                                 *   FILE 183
//*  SYSMOVE   Unload a PDS to a sequential data set in             *   FILE 183
//*            IEHMOVE format.  Compatible with SMS.                *   FILE 183
//*                                                                 *   FILE 183
//*  UNITAFF   Dynamically sets UNIT=AFF for input tape files       *   FILE 183
//*            (must be authorized)                                 *   FILE 183
//*                                                                 *   FILE 183
//*            This program was originally designed to reduce       *   FILE 183
//*            the number of tape drives used by user-submitted     *   FILE 183
//*            SAS steps.  It scans the SWA for the next step       *   FILE 183
//*            and changes some of the SIOT's fields to force       *   FILE 183
//*            all input tape data sets to the same drive.          *   FILE 183
//*                                                                 *   FILE 183
//*            It must be executed immediately before the           *   FILE 183
//*            step to process (SAS, SORT, or any other             *   FILE 183
//*            program that reads a variable number of tape         *   FILE 183
//*            files, one at a time).                               *   FILE 183
//*                                                                 *   FILE 183
//*            Sample jcl:                                          *   FILE 183
//*                                                                 *   FILE 183
//*              //UNITAFF EXEC PGM=UNITAFF                         *   FILE 183
//*              //STEPLIB  DD  DSN=SYS2.AUTHLIB,DISP=SHR           *   FILE 183
//*              //*                                                *   FILE 183
//*              //STEP53  EXEC PGM=SAS                             *   FILE 183
//*              //OSIN     DD DSN=USER1.X,DISP=SHR                 *   FILE 183
//*              //         DD DSN=UPQE.DQE40530(-1),DISP=SHR       *   FILE 183
//*              //OSIN2    DD DSN=UPQR.DQR02150(0),DISP=SHR        *   FILE 183
//*              //OSIN3    DD DSN=USER1.X,DISP=SHR                 *   FILE 183
//*              //         DD DSN=UPBG.DBGA0240(-1),DISP=SHR       *   FILE 183
//*              //OSIN4    DD DSN=USER1.X,DISP=SHR                 *   FILE 183
//*              //         DD DSN=USER1.YY,DISP=SHR                *   FILE 183
//*              //         DD DSN=UPQR.DQR02140(-1),DISP=SHR       *   FILE 183
//*                                                                 *   FILE 183
//*            The program only supports cataloged data sets;       *   FILE 183
//*            relative generation numbers are handled              *   FILE 183
//*            correctly via the GDGNT.                             *   FILE 183
//*                                                                 *   FILE 183
//*            Restriction: No distinction is made between 3420,    *   FILE 183
//*            3480 or 3490 device types; this will cause           *   FILE 183
//*            problems if the input to a step is mixed.            *   FILE 183
//*                                                                 *   FILE 183
//*                                                                 *   FILE 183
//*  ------------------ Assembler Macros ------------------------   *   FILE 183
//*                                                                 *   FILE 183
//*  BUILDCDE  Make storage allocated with GETMAIN appear as a      *   FILE 183
//*            load-module in a dump.                               *   FILE 183
//*                                                                 *   FILE 183
//*            BUILDCDE uses the "loader" form of IDENTIFY to       *   FILE 183
//*            create a major CDE and corresponding XL, then        *   FILE 183
//*            issues a LOAD SVC to create an LLE and associate     *   FILE 183
//*            the CDE with the current TCB.  Don't worry, you      *   FILE 183
//*            don't have to understand how it works to use it.     *   FILE 183
//*                                                                 *   FILE 183
//*            EXAMPLE:                                             *   FILE 183
//*                                                                 *   FILE 183
//*                  GETMAIN RU,LV=20000                            *   FILE 183
//*                  BUILDCDE LENGTH=(0),ADDR=(1),EP=DYNAM20        *   FILE 183
//*                                                                 *   FILE 183
//*            The 20K storage area will appear in a dump           *   FILE 183
//*            as a load-module called "DYNAM20".                   *   FILE 183
//*                                                                 *   FILE 183
//*  EASYSORT  Invoke an internal SORT with OPEN/PUT/GET logic      *   FILE 183
//*                                                                 *   FILE 183
//*            Allows you to do internal sorts without any          *   FILE 183
//*            knowledge of parameter lists or exit routine         *   FILE 183
//*            linkage conventions.                                 *   FILE 183
//*                                                                 *   FILE 183
//*            Example:                                             *   FILE 183
//*                                                                 *   FILE 183
//*                      EASYSORT OPEN,                             *   FILE 183
//*                            FIELDS=(1,22,CH,A),                  *   FILE 183
//*                            TYPE=F,LENGTH=64,                    *   FILE 183
//*                            OPTION='EQUALS,RESINV=500K'          *   FILE 183
//*                      .     .                                    *   FILE 183
//*              READ    GET   FILEIN                               *   FILE 183
//*                      EASYSORT PUT,(1)   pass record to SORT     *   FILE 183
//*                      B     READ                                 *   FILE 183
//*                      .     .                                    *   FILE 183
//*              REWRITE EASYSORT GET,      get sorted record       *   FILE 183
//*                            SET=(R3),                            *   FILE 183
//*                            EODAD=ENDSORT                        *   FILE 183
//*                      PUT   FILEOUT,(R3)                         *   FILE 183
//*                      B     REWRITE                              *   FILE 183
//*                      .     .                                    *   FILE 183
//*              ENDSORT EASYSORT CLOSE                             *   FILE 183
//*                                                                 *   FILE 183
//*  GETDIR    Read a directory sequentially with a BPAM DCB        *   FILE 183
//*                                                                 *   FILE 183
//*            This macro offers a simple way to read directory     *   FILE 183
//*            entries and members with a single BPAM DCB.          *   FILE 183
//*                                                                 *   FILE 183
//*  GETPUT31  Issue GET, PUT or PUTX while in AMODE31              *   FILE 183
//*                                                                 *   FILE 183
//*            This member contains GET31, PUT31 and PUTX31,        *   FILE 183
//*            which are modified versions of GET, PUT and          *   FILE 183
//*            PUTX.  They allow a program running with             *   FILE 183
//*            RMODE24 and AMODE31 to issue QSAM GET, PUT and       *   FILE 183
//*            PUTX without having to switch to AMODE24.            *   FILE 183
//*            GET31 allows specification of an end-of-file         *   FILE 183
//*            routine (EODAD).                                     *   FILE 183
//*                                                                 *   FILE 183
//*  STRING    Provides functions similar to PL/I's                 *   FILE 183
//*            PUT EDIT or COBOL's STRING.                          *   FILE 183
//*                                                                 *   FILE 183
//*            This is the only non-IBM macro you need to           *   FILE 183
//*            assemble the programs in this file.                  *   FILE 183
//*                                                                 *   FILE 183
//*            This member contains the macro, a test job,          *   FILE 183
//*            and the documentation.                               *   FILE 183
//*                                                                 *   FILE 183
//*                                                                 *   FILE 183
//*  ---------------------- Miscellaneous -----------------------   *   FILE 183
//*                                                                 *   FILE 183
//*  DEFGDGSR  Sub-routine - invokes SVC 26 to define a GDG base    *   FILE 183
//*                                                                 *   FILE 183
//*            May be invoked from a COBOL program, like this:      *   FILE 183
//*                                                                 *   FILE 183
//*                  05  DSNAME   PIC X(44) VALUE 'MY.DSNAME'.      *   FILE 183
//*                  05  GDGLIMIT PIC   999 VALUE 027.              *   FILE 183
//*                                                                 *   FILE 183
//*                      CALL 'DEFGDGSR' USING DSNAME,              *   FILE 183
//*                                            GDGLIMIT.            *   FILE 183
//*                                                                 *   FILE 183
//*  FILLDASD  Asm pgm to fill free DASD space with binary zeroes   *   FILE 183
//*                                                                 *   FILE 183
//*  HANDBOOK  Job - Creates an on-line copy of the DATA AREAS      *   FILE 183
//*            (aka Debugging Handbook) manuals                     *   FILE 183
//*                                                                 *   FILE 183
//*            This job assembles macros from SYS1.MACLIB and       *   FILE 183
//*            SYS1.MODGEN and stores the assembly listings         *   FILE 183
//*            into PDS members.  It is set up for over 60          *   FILE 183
//*            commonly used MVS control blocks (such as CVT,       *   FILE 183
//*            TCB, JFCB, etc) and may be easily modified to        *   FILE 183
//*            support other ones.                                  *   FILE 183
//*                                                                 *   FILE 183
//*            The assembly listing for each macro is stored        *   FILE 183
//*            into the output PDS under the control block          *   FILE 183
//*            name.  For example, the assembly listing for         *   FILE 183
//*            "IKJTCB" is stored into the "TCB" member.            *   FILE 183
//*                                                                 *   FILE 183
//*            To conserve dasd space, the LMCOPY service of        *   FILE 183
//*            ISPF/PDF is used to pack the output of the           *   FILE 183
//*            assembler.                                           *   FILE 183
//*                                                                 *   FILE 183
//*  IEC149I   MPF Exit.  Display the dsname from the HDR1 label    *   FILE 183
//*            after a 813-04 or 237-08 abend.                      *   FILE 183
//*                                                                 *   FILE 183
//*  SYSDEBUG  General Purpose ESTAE Routine.  Simplifies abend     *   FILE 183
//*            resolution by formatting and writing out important   *   FILE 183
//*            MVS control blocks in an easy-to-read fashion.       *   FILE 183
//*                                                                 *   FILE 183
//*  TCTDCTR   Sub-routine - Prints the EXCP count for each DD      *   FILE 183
//*            in the job step                                      *   FILE 183
//*                                                                 *   FILE 183
//*            May be invoked at the end of a program for           *   FILE 183
//*            debugging or tuning purposes.                        *   FILE 183
//*                                                                 *   FILE 183
//*  TRIMMAC   Job - Creates a reduced-size MACLIB that may be      *   FILE 183
//*            used instead of the SYS1.MACLIB/SYS1.MODGEN          *   FILE 183
//*            concatenation to improve the performance of the      *   FILE 183
//*            assembler.                                           *   FILE 183
//*                                                                 *   FILE 183
//*            The "TRIMMAC" library is built as follows:           *   FILE 183
//*                                                                 *   FILE 183
//*            1. selected macros are read from ddname "SYSLIB",    *   FILE 183
//*               trimmed from PL/AS code and other comment         *   FILE 183
//*               lines, then written to a temporary data set.      *   FILE 183
//*                                                                 *   FILE 183
//*            2. the SORT utility is invoked to sort the macros    *   FILE 183
//*               in ascending sequence of their size.              *   FILE 183
//*                                                                 *   FILE 183
//*            3. the sorted macros are written to SYSPUNCH         *   FILE 183
//*               as an IEBUPDTE sysin stream.                      *   FILE 183
//*                                                                 *   FILE 183
//*            4. IEBUPDTE is executed in the last step to          *   FILE 183
//*               load the macros into the "TRIMMAC" library,       *   FILE 183
//*               the smallest macros being loaded first.           *   FILE 183
//*                                                                 *   FILE 183
//*            You may customize the member list and the input      *   FILE 183
//*            concatenation to add other macros and/or macro       *   FILE 183
//*            libraries, as needed.                                *   FILE 183
//*                                                                 *   FILE 183
//*            Use the "TRIMMAC" library instead of the             *   FILE 183
//*            MACLIB/AMODGEN concatenation to assemble a           *   FILE 183
//*            program and compare the before/after values for      *   FILE 183
//*            the elapsed time, excp count and I/O connect         *   FILE 183
//*            time.  Expect savings of 30 to 60 percent when       *   FILE 183
//*            "TRIMMAC" is used.                                   *   FILE 183
//*                                                                 *   FILE 183
//*            My "TRIMMAC" PDS is currently allocated as           *   FILE 183
//*            follows:                                             *   FILE 183
//*                                                                 *   FILE 183
//*                UNIT=3390,SPACE=(CYL,(9,,18)),                   *   FILE 183
//*                DCB=(RECFM=FB,LRECL=80,BLKSIZE=29720)            *   FILE 183
//*                                                                 *   FILE 183
//*  USERCMDS  Job - Update USERCMDS in batch                       *   FILE 183
//*                                                                 *   FILE 183
//*            This is a TMP job that uses an in-line REXX exec     *   FILE 183
//*            and ISPF table services to append a set of in-line   *   FILE 183
//*            commands to the original USERCMDS table.             *   FILE 183
//*                                                                 *   FILE 183
//*            The resulting USERCMDS table may be given any        *   FILE 183
//*            name and go to any library you choose.               *   FILE 183
//*                                                                 *   FILE 183
//*  ZAPONTR0  Patch job - Bypass STEPLIB for ILBOxxx routines      *   FILE 183
//*                                                                 *   FILE 183
//*            This patch to ILBONTR0 eliminates                    *   FILE 183
//*            JOBLIB/STEPLIB directory searches for OS/VS          *   FILE 183
//*            COBOL ILBOxxx modules when SYS1.VSCLLIB is in        *   FILE 183
//*            the linklist.  If you compile your COBOL             *   FILE 183
//*            modules with 'resident' and have large JOBLIBs       *   FILE 183
//*            or STEPLIBs, you want to try this.                   *   FILE 183
//*                                                                 *   FILE 183
//*            The job contains 2 different versions of the         *   FILE 183
//*            patch in AMASPZAP format.  Each version              *   FILE 183
//*            corresponds to a different PTF level, use the        *   FILE 183
//*            one that works for you.  The patch is packaged       *   FILE 183
//*            with its own validation program.                     *   FILE 183
//*                                                                 *   FILE 183
//*  ZAPXMIT   Patch job - Remove BLKSIZE(3120) from XMIT OUTDA()   *   FILE 183
//*            cmd                                                  *   FILE 183
//*                                                                 *   FILE 183
//*            This patch to the TRANSMIT command sets the BLKSIZE  *   FILE 183
//*            of the output data set to zero when TRANSMIT/XMIT    *   FILE 183
//*            is invoked with the OUTDA or OUTDS parameter.        *   FILE 183
//*            This version of the ZAP works on TSO/E 2.6.          *   FILE 183
//*                                                                 *   FILE 183
```
