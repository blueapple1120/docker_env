# ogg

```
GGSCI (ogg1) 4> view params mgr

PORT 7809
DYNAMICPORTLIST 7810-7860
AUTORESTART EXTRACT *, RETRIES 5, WAITMINUTES 3, RESETMINUTES 60
PURGEOLDEXTRACTS ./dirdat/*, usecheckpoints, minkeepdays 1
LAGREPORTHOURS 1
LAGINFOMINUTES 30
LAGCRITICALMINUTES 45


GGSCI (ogg1) 2> view params EXT_TEST

EXTRACT ext_test
SETENV(ORACLE_SID="crpdb")
Setenv (NLS_LANG="SIMPLIFIED CHINESE_CHINA.AL32UTF8")
USERID ogg, PASSWORD pwd
DISCARDFILE ./dirrpt/ext_test.dsc, APPEND, MEGABYTES 1024
EXTTRAIL ./dirdat/te
DYNAMICRESOLUTION
GETUPDATES
GETUPDATEBEFORES
NOCOMPRESSDELETES
NOCOMPRESSUPDATES
table EPDM.CD_LOCATION;


GGSCI (ogg1) 3> view params DPE_TEST

EXTRACT dpe_test
PASSTHRU
RMTHOST 10.88.104.236, MGRPORT 7809
RMTTRAIL ./dirdat/te
GETUPDATES
GETUPDATEBEFORES
TABLE EPDM.CD_LOCATION;



GGSCI (test) 1> view param mgr

PORT 7809
DYNAMICPORTLIST 7810-7860
AUTORESTART REPLICAT *, RETRIES 5, WAITMINUTES 3, RESETMINUTES 60
PURGEOLDEXTRACTS ./dirdat/*, usecheckpoints, minkeepdays 1
LAGREPORTHOURS 1
LAGINFOMINUTES 30
LAGCRITICALMINUTES 45



```

