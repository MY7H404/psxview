# PsXview plugin for volatility3
> This plugin helps you detect hidden processes by comparing what PsActiveProcessHead contains with what is reported by various other sources of process listings.
### How to use psxview.py
```
git clone https://github.com/MY7H404/psxview
python3 vol.py -f {filename} -p psxview psxview
```
> [!TIP]
> You can copy the psxview.py file into "volatility3/volatility3/plugins/windows/psxview.py", so that you can easily run this plugin like other normal plugins "windows.psxview"

---
Here is an example of psxview. A "False" in any column indicates that the respective process is missing. You can download this memory dump sample from [here](https://github.com/pinesol93/MemoryForensicSamples), named "Windows 10 build 17134 x64".
```
$ python3 ~/volatility3/vol.py -f memdump.mem -p psxview psxview
Volatility 3 Framework 2.7.2
Progress:  100.00		PDB scanning finished                     
Offset(P)	Name                	  PID	pslist	psscan	session	thrdproc	ExitTime

0xa7800007d080	svchost.exe         	 4400	True	True	True	True	N/A
0xa780000b9580	ctfmon.exe          	 4488	True	True	False	True	N/A
0xa78000101580	NisSrv.exe          	 4668	True	True	True	True	N/A
0xa78000185580	conhost.exe         	 4976	True	True	False	True	N/A
0xa780001d6080	svchost.exe         	 5048	True	True	True	True	N/A
0xc20c69c74280	System              	    4	True	True	-	True	N/A
0xc20c69cf6580	sihost.exe          	 2060	True	True	False	True	N/A
0xc20c69cfe580	explorer.exe        	 4824	True	True	False	True	N/A
0xc20c69d00580	userinit.exe        	 4756	True	True	False	False	2018-08-01 19:21:13.000000 
0xc20c69d52040	Registry            	   68	True	True	-	True	N/A
0xc20c69e87580	WmiPrvSE.exe        	 3460	True	True	True	True	N/A
0xc20c6a212040	smss.exe            	  500	True	True	-	True	N/A
0xc20c6a5514c0	svchost.exe         	 8808	True	True	True	True	N/A
0xc20c6a959580	FTK Imager.exe      	 3328	False	True	-	False	N/A
0xc20c6a963580	audiodg.exe         	 2356	True	True	True	True	N/A
0xc20c6a97b580	taskhostw.exe       	 9408	True	True	False	True	N/A
0xc20c6a9d4080	SystemSettings      	 2660	True	True	False	True	N/A
0xc20c6aa0d580	svchost.exe         	 8052	False	True	-	False	N/A
0xc20c6aa11340	WUDFHost.exe        	 8756	False	True	-	False	N/A
0xc20c6aaaf080	RuntimeBroker.      	 9144	False	True	-	False	2018-08-06 18:14:23.000000 
0xc20c6aaf9080	svchost.exe         	 1992	True	True	True	True	N/A
0xc20c6ab2b580	svchost.exe.ex      	 6176	True	True	False	True	2018-08-01 19:52:19.000000 
0xc20c6ab70080	svchost.exe         	 8852	True	True	False	True	2018-08-01 20:00:08.000000 
0xc20c6ab92580	ByteCodeGenera      	 6532	True	True	False	True	2018-08-01 19:50:42.000000 
0xc20c6abeb580	notepad.exe         	 1412	True	True	False	True	2018-08-06 18:12:17.000000 
0xc20c6adac580	csrss.exe           	  612	True	True	True	True	N/A
0xc20c6afc3580	svchost.exe         	 5580	False	True	-	False	2018-08-06 18:15:11.000000 
0xc20c6b023080	SgrmBroker.exe      	 4244	True	True	True	True	N/A
0xc20c6b427580	NisSrv.exe          	 4668	True	True	True	True	N/A
0xc20c6b475580	conhost.exe         	 4976	True	True	False	True	N/A
0xc20c6b4c6080	svchost.exe         	 5048	True	True	True	True	N/A
0xc20c6b513580	svchost.exe         	 5264	True	True	True	True	N/A
0xc20c6b585580	svchost.exe         	 3224	True	True	True	True	N/A
0xc20c6b588580	ie4uinit.exe        	 5716	True	True	False	True	2018-08-01 19:21:31.000000 
0xc20c6b5b6580	svchost.exe         	 4040	True	True	True	True	N/A
0xc20c6b67e580	TPAutoConnect.      	 4960	True	True	False	True	N/A
0xc20c6b6a5580	svchost.exe         	 2020	True	True	False	True	N/A
0xc20c6b6b5580	svchost.exe         	 4304	True	True	True	True	N/A
0xc20c6b6c3580	svchost.exe         	 4132	True	True	False	True	N/A
0xc20c6b6ef080	taskhostw.exe       	 4260	True	True	False	True	N/A
0xc20c6b8d9580	fontdrvhost.ex      	  948	True	True	False	True	N/A
0xc20c6b8db580	fontdrvhost.ex      	  940	True	True	True	True	N/A
0xc20c6b8dd580	svchost.exe         	  924	True	True	True	True	N/A
0xc20c6b8df580	svchost.exe         	  904	True	True	True	True	N/A
0xc20c6b8ed580	csrss.exe           	  680	True	True	False	True	N/A
0xc20c6b910080	winlogon.exe        	  732	True	True	False	True	N/A
0xc20c6b913080	wininit.exe         	  696	True	True	True	True	N/A
0xc20c6b93e080	services.exe        	  804	True	True	True	True	N/A
0xc20c6b98e080	lsass.exe           	  816	True	True	True	True	N/A
0xc20c6ba17580	svchost.exe         	  628	True	True	True	True	N/A
0xc20c6ba39580	svchost.exe         	 1020	True	True	True	True	N/A
0xc20c6ba9f080	svchost.exe         	  476	True	True	True	True	N/A
0xc20c6bad9580	svchost.exe         	 1196	True	True	True	True	N/A
0xc20c6bae1580	svchost.exe         	 1072	True	True	True	True	N/A
0xc20c6bae3580	svchost.exe         	 1056	True	True	True	True	N/A
0xc20c6bae5580	svchost.exe         	 1040	True	True	True	True	N/A
0xc20c6bae9580	svchost.exe         	  800	True	True	True	False	2018-08-06 18:11:48.000000 
0xc20c6bb0b080	dwm.exe             	 1144	True	True	False	True	N/A
0xc20c6bb8e580	svchost.exe         	 1296	True	True	True	True	N/A
0xc20c6bb9a580	svchost.exe         	 1392	True	True	True	True	N/A
0xc20c6bb9c580	svchost.exe         	 1384	True	True	True	True	N/A
0xc20c6bbd5380	vmacthlp.exe        	 1336	True	True	True	True	N/A
0xc20c6bbf2580	svchost.exe         	 1480	True	True	True	True	N/A
0xc20c6bbf4580	svchost.exe         	 1472	True	True	True	True	N/A
0xc20c6bc35580	svchost.exe         	 1632	True	True	True	True	N/A
0xc20c6bc3b580	svchost.exe         	 1600	True	True	True	True	N/A
0xc20c6bc3d580	svchost.exe         	 1592	True	True	True	True	N/A
0xc20c6bc3f580	svchost.exe         	 1576	True	True	True	True	N/A
0xc20c6bc41580	svchost.exe         	 1568	True	True	True	True	N/A
0xc20c6bca52c0	svchost.exe         	 1608	True	True	True	True	N/A
0xc20c6bcc9580	svchost.exe         	 1692	True	True	True	True	N/A
0xc20c6bcd1400	svchost.exe         	 2888	True	True	True	True	2018-08-01 19:24:38.000000 
0xc20c6bcee580	svchost.exe         	 1944	True	True	True	True	N/A
0xc20c6bcf6580	svchost.exe         	 1884	True	True	True	True	N/A
0xc20c6bcfa580	svchost.exe         	 1856	True	True	True	True	N/A
0xc20c6bd28580	svchost.exe         	 1768	True	True	True	True	N/A
0xc20c6bddc340	svchost.exe         	 1936	True	True	True	True	N/A
0xc20c6be01580	svchost.exe         	 1964	True	True	True	True	N/A
0xc20c6be13580	svchost.exe         	 2128	True	True	True	True	N/A
0xc20c6be63040	MemCompression      	 1096	True	True	-	True	N/A
0xc20c6bfa6580	svchost.exe         	 2276	True	True	True	True	N/A
0xc20c6bfae580	svchost.exe         	 2232	True	True	True	True	N/A
0xc20c6bfb2580	svchost.exe         	 2164	True	True	True	True	N/A
0xc20c6bfdb080	svchost.exe         	 2224	True	True	True	True	N/A
0xc20c6c026580	svchost.exe         	 2400	True	True	True	True	N/A
0xc20c6c032580	svchost.exe         	 2420	True	True	True	True	N/A
0xc20c6c082580	svchost.exe         	 2476	True	True	True	True	N/A
0xc20c6c095580	MSASCuiL.exe        	 6268	True	True	False	True	N/A
0xc20c6c11f580	vmtoolsd.exe        	 2712	True	True	True	True	N/A
0xc20c6c121580	VGAuthService.      	 2704	True	True	True	True	N/A
0xc20c6c123580	svchost.exe         	 2692	True	True	True	True	N/A
0xc20c6c125580	SecurityHealth      	 2680	True	True	True	True	N/A
0xc20c6c12b580	svchost.exe         	 2644	True	True	True	True	N/A
0xc20c6c12f580	svchost.exe         	 2636	True	True	True	True	N/A
0xc20c6c131580	svchost.exe         	 2628	True	True	True	True	N/A
0xc20c6c133580	svchost.exe         	 2620	True	True	True	True	N/A
0xc20c6c14b580	spoolsv.exe         	 2332	True	True	True	True	N/A
0xc20c6c19f580	svchost.exe         	 2724	True	True	True	True	N/A
0xc20c6c1a5580	svchost.exe         	 2908	True	True	True	True	N/A
0xc20c6c1a7580	svchost.exe         	 2892	True	True	True	True	N/A
0xc20c6c1db580	MsMpEng.exe         	 2756	True	True	True	True	N/A
0xc20c6c1e1580	svchost.exe         	 2736	True	True	True	True	N/A
0xc20c6c501580	TPAutoConnSvc.      	 3452	True	True	True	True	N/A
0xc20c6c50f080	dllhost.exe         	 3472	True	True	True	True	N/A
0xc20c6c6be580	msdtc.exe           	 3796	True	True	True	True	N/A
0xc20c6c6cb080	svchost.exe         	 5304	True	True	True	True	N/A
0xc20c6c766080	svchost.exe         	 4400	True	True	True	True	N/A
0xc20c6c7a2580	ctfmon.exe          	 4488	True	True	False	True	N/A
0xc20c6c82a580	SearchFilterHo      	 3316	True	True	True	True	N/A
0xc20c6c894580	svchost.exe         	 5028	True	True	True	True	N/A
0xc20c6c8b4580	svchost.exe         	 3648	True	True	True	True	N/A
0xc20c6cb23580	dllhost.exe         	 5872	True	True	False	True	N/A
0xc20c6cb8b580	SearchIndexer.      	 6028	True	True	True	True	N/A
0xc20c6cbb6080	ShellExperienc      	 6108	True	True	False	True	N/A
0xc20c6cca2580	RuntimeBroker.      	 4768	True	True	False	True	N/A
0xc20c6ccd5580	SearchUI.exe        	 5420	True	True	False	True	N/A
0xc20c6cd4b580	RuntimeBroker.      	 1116	True	True	False	True	N/A
0xc20c6cdf4580	scvhost.exe         	  360	True	True	False	True	2018-08-06 18:12:03.000000 
0xc20c6ce694c0	svchost.exe         	 7260	True	True	True	True	N/A
0xc20c6cec3080	conhost.exe         	 9912	True	True	False	True	N/A
0xc20c6cec7080	svchost.exe         	 6848	True	True	True	True	N/A
0xc20c6cf5e580	ApplicationFra      	 6236	True	True	False	True	N/A
0xc20c6cfb1580	OneDrive.exe        	 2200	True	True	False	True	N/A
0xc20c6cfc2580	vmtoolsd.exe        	 3372	True	True	False	True	N/A
0xc20c6d020580	AM_Delta.exe        	 2000	False	True	-	False	N/A
0xc20c6d03d580	RuntimeBroker.      	 6488	True	True	False	True	N/A
0xc20c6d04c080	MicrosoftEdge.      	 6524	True	True	False	False	2018-08-01 19:36:02.000000 
0xc20c6d0d2080	Bubbles.scr         	10204	True	True	False	True	2018-08-01 19:50:38.000000 
0xc20c6d0e3580	RuntimeBroker.      	 6640	True	True	False	False	2018-08-01 19:40:40.000000 
0xc20c6d242580	svchost.exe         	 7328	True	True	True	True	N/A
0xc20c6d270080	svchost.exe         	 5024	True	True	True	True	N/A
0xc20c6d303580	svchost.exe         	 6744	True	True	False	True	N/A
0xc20c6d314580	svchost.exe         	 5940	True	True	True	True	N/A
0xc20c6d34a580	WMIADAP.exe         	 8444	False	True	-	False	N/A
0xc20c6d36c080	scvhost.exe.ex      	  336	True	True	False	True	2018-08-01 19:52:31.000000 
0xc20c6d482080	OfficeHubTaskH      	  400	True	True	False	True	N/A
0xc20c6d4cc080	svchost.exe         	 8708	True	True	True	True	N/A
0xc20c6d4d2080	dxdiag.exe          	 6324	True	True	False	True	2018-08-01 19:51:28.000000 
0xc20c6d4f3080	svchost.exe         	 8108	True	True	True	True	N/A
0xc20c6d510080	notepad - Copy      	 6372	True	True	False	True	2018-08-01 20:10:32.000000 
0xc20c6d561080	dllhost.exe         	 6884	True	True	False	True	N/A
0xc20c6d5ac340	svchost.exe.ex      	 5528	True	True	False	True	2018-08-01 19:52:20.000000 
0xc20c6d617580	SkypeHost.exe       	 2296	True	True	False	True	N/A
0xc20c6d63e080	svchost.exe         	 9388	True	True	True	True	N/A
0xc20c6d687580	SearchProtocol      	 6376	True	True	False	True	N/A
0xc20c6d694080	notepad - Copy      	 3504	True	True	False	True	2018-08-01 20:10:37.000000 
0xc20c6d6b8580	dllhost.exe         	 7384	True	True	False	True	N/A
0xc20c6d6c3080	smartscreen.ex      	 7624	True	True	False	True	N/A
0xc20c6d6fc580	svchost.exe         	10012	True	True	False	True	2018-08-01 19:49:19.000000 
0xc20c6d732080	notepad.exe         	 9128	True	True	False	True	2018-08-01 20:05:12.000000 
0xc20c6d789580	Bubbles.scr         	 6948	True	True	False	True	2018-08-01 19:50:31.000000 
0xc20c6d82e080	svchost.exe         	 1404	True	True	False	True	2018-08-01 19:56:35.000000 
0xc20c6d86b080	cmd.exe             	 3884	True	True	False	True	N/A
0xc20c6d8e02c0	SearchFilterHo      	 5344	False	True	-	False	N/A
0xc20c6d99b580	svchost.exe.ex      	 8140	True	True	False	True	2018-08-01 19:52:16.000000 
0xc20c6daa5080	WmiPrvSE.exe        	 5632	True	True	True	True	N/A
0xc20c6daf9580	notepad.exe         	 7968	True	True	False	True	2018-08-01 19:57:10.000000 
0xc20c6db28080	RuntimeBroker.      	 3948	True	True	False	True	N/A
0xc20c6db7c200	RuntimeBroker.      	 2744	True	True	False	True	N/A
0xc20c6dbc5340	svchost.exe         	 7852	True	True	False	True	2018-08-01 19:49:22.000000 
0xc20c6dc01080	svchost.exe         	 5712	True	True	True	True	N/A
0xc20c6ddad580	svchost.exe         	 8560	True	True	False	True	N/A
0xc20c6ddb1580	svchost.exe         	10024	True	True	True	True	N/A
0xc20c6debd400	MicrosoftEdge.      	 6552	True	True	False	False	2018-08-01 19:40:09.000000 
0xc20c6df09580	MpSigStub.exe       	 4276	False	True	-	False	N/A
0xc20c6e0bf580	scvhost.exe.ex      	 3016	True	True	False	True	2018-08-01 19:52:29.000000 
0xc20c6e0ea580	svchost.exe         	 7136	True	True	True	True	N/A
0xc20c6e24f580	xwizard.exe         	  252	True	True	False	True	2018-08-01 19:51:55.000000 
0xc20c6e495080	cmd.exe             	 8868	True	True	False	True	2018-08-01 19:49:18.000000 
0xc20c6e58b580	wuauclt.exe         	 4076	False	True	-	False	N/A
0xc20c6e5ca200	notepad.exe         	 8800	True	True	False	True	2018-08-01 20:10:21.000000 
0xf800cad56580	msdtc.exe           	 3796	True	True	True	True	N/A
0xf800cad63080	svchost.exe         	 5304	True	True	True	True	N/A
0xf800caeac4c0	svchost.exe         	 8808	True	True	True	True	N/A
0xf800caf3c580	notepad.exe         	 1412	True	True	False	True	2018-08-06 18:12:17.000000
```
## Contribution

Contributions to psxview are welcome. If you encounter issues or have suggestions for improvements, feel free to open an issue or submit a pull request.

## TODO
- [ ] pspcid table
- [ ] csrss
- [ ] deskthrd
