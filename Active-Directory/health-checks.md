Health checks run prior to Domain Functional Level Upgrade
----------------------------------------------------------
####Find current Domain Functional Level
In an elevated command prompt: 
```(Get.ADForest).DomainMode```
```(Get.ADForest).ForestMode```

####dcdiag
```dcdiag /c /e /v```

####DSQuery
``` dsquery * cn=schema,cn=configuration,dc=[insertdomainhere],dc=ad -scope base -attr objectVersion```

####netdom
```netdom /query fsmo```

####repadmin
```repadmin /replsummary```
```repadmin /showrepl```
```repadmin /bridgeheads * /verbose```
```repadmin /bind *```
```repadmin /showbackup *```
```repadmin /showtrust *```
```repadmin /showoutcalls *```
```repadmin /kcc *```
```repadmin /syncall /e```
```repadmin /syncall /aped```
```repadmin /failcache *```
```repadmin /istg * /verbose```
