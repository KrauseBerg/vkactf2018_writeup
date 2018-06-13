You Spin Me Righ... [Crypto 10]
-----------------------------------
>Расшифруй:  
synt{pnrfne_abg_frpher_nalzber}

Используем шифр Цезаря (он же rot13)  
>```flag{caesar_not_secure_anymore```

MD(ascii(f)-ascii(a)) [Crypto 20]
-----------------------------------
>Что здесь захешировали?  
9a0c3013dbacdda1873e4a153346dc5c  
Флаг в формате FLAG{исходная строка}  

По заголовку таска видно, что ```ascii(f)-ascii(a)``` равно 5.  А занчит используем md5 decoder.

>```FLAG{1234567qwerty}```

...игла в яйце... [Crypto 30]
-----------------------------------
Раскодируйте  
```4a 54 51 32 4a 54 52 6a 4a 54 51 78 4a 54 51 33 4a 54 64 69 4a 54 51 78 4a 54 55 7a 4a 54 51 7a 4a 54 51 35 4a 54 51 35 4a 54 56 6d 4a 54 59 35 4a 54 63 7a 4a 54 56 6d 4a 54 63 32 4a 54 59 31 4a 54 63 79 4a 54 63 35 4a 54 56 6d 4a 54 63 32 4a 54 59 31 4a 54 63 79 4a 54 63 35 4a 54 56 6d 4a 54 59 31 4a 54 59 78 4a 54 63 7a 4a 54 63 35 4a 54 64 6b```

Дан код в формате hex. Раскодируем.  
```JTQ2JTRjJTQxJTQ3JTdiJTQxJTUzJTQzJTQ5JTQ5JTVmJTY5JTczJTVmJTc2JTY1JTcyJTc5JTVmJTc2JTY1JTcyJTc5JTVmJTY1```  
Получили код в base64. Раскодируем.  
```%46%4c%41%47%7b%41%53%43%49%49%5f%69%73%5f%76%65%72%79%5f%76%65%72%79%5f%65```  
Получили URL. Раскодируем.  

>```FLAG{ASCII_is_very_very_e}```

Классика [Crypto 40]
-----------------------------------
>Флаг в формате FLAG{нижний_регистр}  
ckQhOdIF Th eOoX kVaVVHTaR XVWSPW, dRblIoL KVaVVHTaRo EjS dINAmaVaPq QMPO CTlS sLWb fLGY fSTqVW. HTIa AkW EWWqUaMPG bf NWXmfQ EPD mSLg MfTdISUXfThc. NSdc CFYWCpMgbMXG, TaWY XIUcYI SUblE WXlOOLGD mg TdI hSaTNE mZEu Sob. nVKTbkH OLgffLCIkk AnI WOeMNY mjAeRWR MRF VXjY WHSdfEDLX. LHac kSQQ VO ZWT WPgbS aGLe oIpL SZX LWMTf MaQTSdW QF mZE dSmgQLQLW, jEcEjRXIUS hX AcI, Tif ETE nkUWPdm ZSV FhfD kJ TSURI CTjReIV. DQXU OY SLh OabPW JAoW BaIf YQTV WblH xVahUWJ sagRpLSWdW, KNVdUZMfU PSIS hX AhP kWlIU, RTTBeXk, OZH DIkVS. xVahUWJ sagRpLSWdW CRX fOp OfciR HOk TEeRY OOVQBTlS WRV QMR VEgV Tk FW QXYOSr ST pMeSe. rQ BkWEZ WhSOMHIV, ZEWPlV dINAmWD lVgPXIOS idAcYW hTI dRblIoL KVaVVHTaR. Bpsu{hMIEgWRa_Mk_jQVa_ETkY}  
PLWgQ ETE llUnHq, RQRUE-VgApIV, dgVTIgY, TaHVm NICR VSTo aahT PCRZW RkYfR QcGS. tfOpLWf fLKNZ lHWX VfMaU PXgPhI lc fLG bkaTeWZ GTSTTaSIn Mk hTIKR laZa. edhTSWGa lHac SfQ RQT amGa PaYQ XJE FSIjI ucaR, VHXq AnI S aQHKUf lO hEjUQ GCT. MZEu EjS M WNOp eApYjWZK DRXWD WRV Ra RQT kWAYL lVQMT FndL oMrS gRVIe lHnIW mQETS hX AcI. EOfYTE fSLaW SjQVIAX fIjI lc eIXEglEaR hcgRFS, TfD iElidI HEfSLaW SjQVCGX kErIf ha XYEenE lSmbPW. cLmZOqKZ aaWV PXgPhI lVURM OY lHaQ Sg NIKNZ TLqI UOfW, VHXq CkQW WZ E PUfTEn SX QaPQRl SNZ TShfITNl. FOp InSdc DLnW CWX ag M fTImaSd wZcdXJAbj. ip Mk gfMNL VgNoMVSdIF OgW Ob XZS YMPOkaTu FjSQHU Ig ufw.  
tjcNEDLr lHa SdRQWV egYLeWZ PdIGD hX CWX, lVQ fTImaSd wZcdXJAbj CWR lfMGG Imk AjGWgfVa BTUK pS lVQ HQMXkTeG UOfW QF KgMa. xZWe FTEXV WWW XWdWV PkaZaH Xcd MVS iZYoMUOX WVRXfGpL SbP LWNmaNc ETWXMVY. MgDWc, lVQ QQSm lHac mggENLr ZUjX ag RST TaWIn Sob RSQD UgWhW. tfUXKSa KHkVlVMMTS fSY dEnS eXCRmWD kYl Oe WVRXWT YElg UR VHX MNeXWR wMPGWgM, XYl kUXJ PeWNpc gT TETD pgRg JjcY FTEXVEnW SZX SXEk lHa agfXH, VHX tReXagT wJOklHWMj VMW DEVgMa E XcdGG Th TE nIUYaRGD paTd Sf hTI eft kHka TSZGJ, HTnIjK TSQR TEVgGjMrSP EU A UjEaH ab yEa 1980. taWY WVW baa DETmTeJmZ, YYEH-egVaH UOfW KNmWRjElWaRCLeq.  
ao QWbfMQNXV PnInWaYULr, tReXagT wJOklHWMjg TEXE gg SlIUWRME BkWEZ-VWZMXGD WaSaEkSe. AJEg UHkSkWZK C bkaTeWZ GTSTTaSIn Jgf kSWR YSMePq, ddMEIgY UoYSZXc FEiWNZW gb fcRE, ThPhMUONPG MTjKeRYg, MRF PTjEjXSUQ. eEHbWVaQWbfW YHbUH YEf PQ JQUgV Ij XZS bIFIZjEa MfQXYFE vxa pMlZQW UUVZ Ao ku (udEPD vZAiTacZ), kr (gkSNZ tjSYMGR), GO (nWXacZEN wbfNaV), tK (nVGEW OIjRWf), MRF rP (JEcMgbMP yIgfEn). xZSdI KS TdSk XZS OSXEmWD WaSfP SH dF (vIoXabSYKSaWD IIjWf), aJIVZ MaEfg fLCT T XEiEdS TEU PkgDqGWR RMXE vxa CVSbP gJAfhIkRk/DdIOIXjS, WRV O YENE aSS lVgRgGGS YaFpIWb ojc gkSNZ gZOYTKOgk/pnIeWQVU.  
ulmAhPq PdIGDXjS iEcS WMVTXfS WZSWXEDLX TEpaWSZ XYEenE WRV gUbVEXf WaIcg aJ CGX. LHa IpdQVVS lWEi Xg OSVGE mZAp OahfIPS YaRoX khMVV BhfDeRY kUXJ HneAjW SfaYPD mZE WKW cR XYEenE sIWYe. eHTXj TsIdjQ aGEdk, KeXlSZW JAoW HWH lVQMT BTkIY MfcOYNAmaOjW, ZOhI DEXf WaEfSP, EPD aSVa LSR fLG TbeE pS TSOSOE pWLh-EVXgWVEW. EOoX TfQIFEkk RaUmWdI VHTl TdIq fQQCIg kAbIdm URFOhjS WRV hTEV TaWY XI kdMcGD/gWUpIjSP. hWE mg TdI TfQIFEkk’ DePaUQREE bf PhEUWZK EAmk, RWVWZk HQEl S bnMlWeL uHhjTdEaf ZIGD mg Ba VWgOYGD YjOi E kVQPVEk. ufw EfR YSUT UjEaHWfe HKSThPnSnS aJ FEVdAsMfU MRF TXfDkRWQfSOY lmRcIjm. IMVH ijOlIj QMVG, TaWSa GShe aKLe dIrI S ZaRI, HXSLpLq, OZH LOrXUh PaTQ EPD UjIjK ZObTKNXkS pS lVQMT FTeIhc. xcd QQRX aNbSjaMXKOg, hLaEkS OSPTTUT pLW pdIGD vgUjGaZ EIERXlAnc Xcd XJIl TRaIV.  

Текст наталкивает на то, что это шифр Vigenere.  
Расшифруем.  
p.s. Я использовал утилиту CrypTool

>```Flag{vIGEnERe_Is_vERy_EAsY}```

