---
title: "A Solarsoft IDL example"
objectives:
- "Run an IDL program using the Solarsoft library"
---

A simple set of example code to confirm that IDL and Solarsoft are functioning as expected is available from [https://gitlab.com/FaradaysGnomes/scw-idl-tutorial.git](Richard Grimes' gitlab page). 

# Setting up the code

Download this project into your home directory:

~~~
git clone https://gitlab.com/FaradaysGnomes/scw-idl-tutorial.git
~~~
{: .bash}

Change into the directory:

~~~
cd scw-idl-tutorial
~~~
{: .bash}

Edit the set_sunbird.pro directories to point at our work directories. For this tutorial we will just point it at the scw-idl-tutorial folder.

~~~
nano set_sunbird.pro
~~~
{: .bash}


Change the home and idlhome lines to the following and then use CTRL+X to exit, pressing y when asked to save and then hitting enter to confirm the file name.

~~~
home='/home/'+username+'/scw-idl-tutorial
idlhome=home
~~~~



# Running the Example on the Login Node

Load the IDL module:

~~~
module load IDL
~~~
{: .bash}


Launch idl on the command line and then type `set_sunbird, ['sdo']` to run the Solarsoft configuration script.

~~~
$ idl
IDL 8.7.2 (linux x86_64 m64).
(c) 2019, Harris Geospatial Solutions, Inc.

Licensed for use by: University of Swansea
License: MNT-5515312
IDL> set_sunbird, ['sdo']
% Compiled module: SET_SUNBIRD.
% Compiled module: DEVICELIB.
% DEVICELIB: Added system variable !BCOLOR
% DEVICELIB: Added system variable !ASPECT
% Compiled module: IMAGELIB.
% IMAGELIB: Added system variable !IMAGE
IDL> 


SSWIDL should now be configured. We can test this by using the example procedure:

~~~
IDL> tutorialshowvsoimage, '/home/a.abc1/'     
% Compiled module: TUTORIALSHOWVSOIMAGE.
% Compiled module: DOWNLOADVSO.
% Compiled module: VSO_SEARCH.
% Compiled module: VSO__DEFINE.
% Compiled module: SOAP__DEFINE.
% Compiled module: GEN__DEFINE.
% Compiled module: VSO_SERVER.
% Compiled module: IS_STRING.
% Compiled module: HAVE_NETWORK.
% Compiled module: URL_FIX.
% Compiled module: IS_BLANK.
% Compiled module: HAS_URL_SCHEME.
% Compiled module: URL_PARSE.
% Compiled module: STR_REPLACE.
% Compiled module: IS_NUMBER.
% Compiled module: IS_STRUCT.
% Compiled module: SINCE_VERSION.
% Compiled module: SOCK_HEAD.
% Compiled module: IS_URL.
% Compiled module: IS_FTP.
% Compiled module: IDLNETURL2__DEFINE.
% Loaded DLM: URL.
% Compiled module: HTTP_PROXY.
% Compiled module: IS_NUMBER2.
% Compiled module: SOCK_IDL_AGENT.
% Compiled module: USE_PROXY.
% Compiled module: HAVE_PROXY.
% Compiled module: SOCK_CONTENT.
% Compiled module: SOCK_CONTENT_HTTP.
% Compiled module: BYTE2STR.
% Compiled module: MERGE_STRUCT.
% Compiled module: HTTP__DEFINE.
% Compiled module: ALLOW_SOCKETS.
% Compiled module: OS_FAMILY.
% Compiled module: HAVE_TAG.
% Compiled module: TRIM.
% Compiled module: GREP.
% Compiled module: APPEND_ARR.
% Compiled module: EXIST.
% Compiled module: OBJ_STRUCT.
% Compiled module: XMLPARSER__DEFINE.
% Compiled module: VSO_FORMAT.
% Compiled module: ANYTIM2UTC.
% Compiled module: DATATYPE.
% Compiled module: STR2UTC.
% Compiled module: VALID_NUM.
% Compiled module: DELVARX.
% Compiled module: DELVARX2.
% Compiled module: DESTROY.
% Compiled module: BOOST_ARRAY.
% Compiled module: UTC2INT.
% Compiled module: TAG_EXIST.
% Compiled module: DATE2MJD.
% Compiled module: CHECK_INT_TIME.
% Compiled module: GET_LEAP_SEC.
% Compiled module: INT2UTC.
% Compiled module: MJD2DATE.
% Compiled module: STR_FORMAT.
% Compiled module: ARR2STR.
% Compiled module: TRIM2.
% Compiled module: TRY_NETWORK.
% Compiled module: STRARRCOMPRESS.
% Compiled module: SOCK_READU.
% Compiled module: IS_SOCKET.
% Compiled module: CLOSE_LUN.
% Compiled module: XKILL.
% Compiled module: STACK__DEFINE.
Records Returned : JSOC : 1/1
Found   1 files. Downloading first file...
% Compiled module: VSO_GET.
% Compiled module: UNIQ.
% Compiled module: DEFAULT.
% Loaded DLM: XML.
% VSO_GET: This will download 1 file(s)
1 : http://netdrms01.nispdc.nso.edu/cgi-bin/netdrms/drms_export.cgi?series=hmi__Ic_45s;compress=rice;record=15210242-15210242
% Compiled module: SOCK_COPY.
% Compiled module: REM_DUP_KEYWORDS.
% Compiled module: SOCK_GET.
% Compiled module: CURDIR.
% Compiled module: IS_MEMBER.
% Compiled module: DATA_CHK.
% Compiled module: TEST_DIR.
% Compiled module: WRITE_DIR.
% Compiled module: CHKLOG.
% Compiled module: GET_DELIM.
% Compiled module: FIX_SLASH.
% Compiled module: STR2ARR.
% Compiled module: DERIV_ARR.
% Compiled module: LOCAL_NAME.
% Compiled module: CONCAT_DIR.
% Compiled module: GET_LOGENV.
% Compiled module: VALID_TIME.
% Compiled module: GET_TEMP_DIR.
% Compiled module: HOME_DIR.
% Compiled module: SESSION_ID.
% Compiled module: GET_RID.
% Compiled module: NINT.
% Compiled module: MPRINT.
% Compiled module: GET_CALLER.
% Compiled module: STRPAD.
% SOCK_GET_MAIN: 15808320 bytes of hmi.ic_45s.2014.09.10_00_01_30_TAI.continuum.fits copied in 23.56 seconds.
% Compiled module: CHMOD.
% VSO_GET: Downloading completed
Done!
% Compiled module: READ_SDO.
% Compiled module: FILE_EXIST.
% Compiled module: FILE_STAT.
% Compiled module: GET_FITS_NEXTEND.
% Compiled module: FITS_OPEN.
% Compiled module: SXPAR.
% Compiled module: GETTOK.
% Compiled module: SXDELPAR.
% Compiled module: FITS_INFO.
% Compiled module: STRN.
% Compiled module: REQUIRED_TAGS.
% Compiled module: MREADFITS_TILECOMP.
% Compiled module: MREADFITS_HEADER.
% Compiled module: HEADFITS.
% Compiled module: FXPOSIT.
% Compiled module: FXMOVE.
% Compiled module: MRD_HREAD.
% Compiled module: FXPAR.
% Compiled module: MRD_SKIP.
% Compiled module: FITSHEAD2STRUCT.
% Compiled module: FXADDPAR.
% Compiled module: FXPARPOS.
% Compiled module: FMT_TAG.
% Compiled module: DETABIFY.
% Compiled module: STRSPECIAL.
% Compiled module: STRLASTCHAR.
% Compiled module: SSW_STRSPLIT.
% Compiled module: ID_ESC.
% Compiled module: ISVALID.
% Compiled module: ID_ESC_INIT.
% Compiled module: SSW_UNIQ.
% Compiled module: ID_UNESC.
% Compiled module: MRD_STRUCT.
% Compiled module: TAG_INDEX.
% Compiled module: STRMIDS.
% Compiled module: GT_TAGVAL.
% Compiled module: STR_TAGVAL.
% Compiled module: SSW_BIN_PATH.
% Compiled module: STR_SUBSET.
% Compiled module: WHERE_ARR.
% Compiled module: REP_TAG_NAME.
% Compiled module: STRUP.
% Compiled module: GET_TAG_INDEX.
% Compiled module: REM_TAG.
% Compiled module: ADD_TAG.
% Compiled module: IDL_RELEASE.
% Compiled module: LAST_ITEM.
% Compiled module: JOIN_STRUCT.
% Compiled module: BOX_MESSAGE.
% Compiled module: STRJUSTIFY.
% Compiled module: PRSTR.
 -----------------------------
| Uncompressing to> /usr/tmp/ |
 -----------------------------
% Compiled module: SSW_JSOC_INDEX2FILENAMES.
% Compiled module: TIME2FILE.
% Compiled module: ANYTIM.
% Compiled module: CHECKVAR.
% Compiled module: STR_LASTPOS.
% Compiled module: UTIME2STR.
% Compiled module: GETUTBASE.
% Compiled module: GETUT.
% Compiled module: INT2EX.
% Compiled module: DAYCNV.
% Compiled module: EX2INT.
% Compiled module: JDCNV.
% Compiled module: UTC2STR.
% Compiled module: MK_DIR.
% Compiled module: IS_DIR.
 --------------------------------------------------------------------------------------------------------
| /home/a.cos/hmi.ic_45s.2014.09.10_00_01_30_TAI.continuum.fits -> /usr/tmp/HMI20140910_000036_6173.fits |
 --------------------------------------------------------------------------------------------------------
% Compiled module: SSW_FILE_DELETE.
% FREE_LUN: Unable to delete file. Unit: 100, File: /usr/tmp/HMI20140910_000036_6173.fits
  Operation not permitted
% SSW_FILE_DELETE: Can't delete: /usr/tmp/HMI20140910_000036_6173.fits

FITSIO status = 105: couldn't create the named file
failed to create new file (already exists?):
/usr/tmp/HMI20140910_000036_6173.fits
% Compiled module: ALL_VALS.
% Compiled module: MREADFITS_SHM.
% Compiled module: FILE_SIZE.
% Compiled module: WHERE_PATTERN.
% Compiled module: LAST_NELEM.
% Compiled module: ALPHAGEN.
% Compiled module: IS_LENDIAN.
% Compiled module: GET_NBYTES.
% Compiled module: SWAP_ENDIAN_INPLACE.
% Compiled module: RELTIME.
% Compiled module: UT_TIME.
% Compiled module: UT_DIFF.
% Compiled module: SYSTIM.
% Compiled module: INT2SEC.
% Compiled module: ANYTIM2INTS.
% Compiled module: TIMSTR2EX.
% Compiled module: FMT_TIM.
% Compiled module: GT_DAY.
% Compiled module: GT_TIME.
% Compiled module: ATIME.
% Compiled module: FCHECK.
% Compiled module: F_ATIME.
% Compiled module: WC_WHERE.
% Compiled module: TIMEGRID.
% Compiled module: CONCAT_STRUCT.
% Compiled module: INT2SECARR.
% Compiled module: UPDATE_HISTORY.
% Compiled module: STR2NUMBER.
% Compiled module: BOOST_TAG.
% Compiled module: REP_TAG_VALUE.
% Compiled module: COPY_VAR.
% Compiled module: COMP_FITS_CEN.
% Loaded DLM: PNG.
Saved image to /home/a.abc1/
IDL> 
~~~
{: .bash}

This should have created two files in the home directory, one called `hmi.ic_45s.2014.09.10_00_01_30_TAI.continuum.fits` and the other `output.png`. 

# Copy the output back to your own computer

Open an SFTP or SCP client such as filezilla and connect to `sunbird.swansea.ac.uk`. Copy the `output.png` file back to your own computer and view it.

Alternatively this can be done from the command line (change a.abc1 to your user id) with the SCP command. The first part of the command specifies the username and hostname, the second part after the : is the name of the file we want to copy and the 3rd part is the destination for the file, in this case `.` means the current directory.

~~~
scp a.abc1@sunbird.swansea.ac.uk:output.png .
~~~
{: .bash}

# Automating the whole process

Launch nano and create a new file called `run.pro` 

~~~
nano run.pro
~~~
{: .bash}

Enter the two commands we typed above followed by `exit`

~~~
set_sunbird, ['sdo']
tutorialshowvsoimage, '/home/a.cos/'
exit
~~~

Now create a Slurm script to run this on a compute node:

~~~
nano testjob.slurm
~~~
{: .bash}

and enter the code below, this will tell Slurm the job name is "testjob", allocate 1 CPU core and give a time limit of 5 minutes. It then loads the IDL module and runs the `run.pro` script.

~~~
#!/bin/bash --login
#SBATCH --job-name=testjob
#SBATCH -n 1
#SBATCH --time=0-0:5:0

module load IDL/8.7
idl run.pro
~~~

Now submit the slurm script using the `sbatch` command.

~~~
sbatch testjob.slurm
~~~
{: .bash}




