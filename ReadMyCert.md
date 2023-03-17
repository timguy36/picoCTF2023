# ReadMyCert

## Challenge Description

How about we take you on an adventure on exploring certificate signing requests
Take a look at this CSR file here.

## Tags
Cryptography

## Challenge Information

Points: 100

## Hints

1) Download the certificate signing request and try to read it.

## Solution

The challenge gives you readmycert.csr, a Certificate Signing Request file.

````
terminal % cat readmycert.csr 
-----BEGIN CERTIFICATE REQUEST-----
MIICpzCCAY8CAQAwPDEmMCQGA1UEAwwdcGljb0NURntyZWFkX215Y2VydF8zYWE4
MDA5MH0xEjAQBgNVBCkMCWN0ZlBsYXllcjCCASIwDQYJKoZIhvcNAQEBBQADggEP
ADCCAQoCggEBAN1PdpW4sKum7AhFubDl86sflki20dWKkZ/iZBYYX/RYqZIWm9ve
pdfwkeiDdz7KriPzM9tTDuJm1kWv8/3AxHrYwliFHK0lsmUYdOcPfrvlh6SIuZwH
vxhrR0DJ0+W5vU+4j9G/hk2+JLMURh8WZadwBhRcfIxk97OXujjvHS9KplMAs5ul
cSSQcv77QkIcxVg1OSDVZoEjTr131g+/Jox3T+uFPEvzF9iq03JMU39oqfGaFL02
EQTaTl8efLIDkGxrKCc+Jhn4e1mD+9UlUmIn9nsOBCYNrnfq4usAL10ZPMDty2Sx
yVTl0171trvCA9DF5PRG6eMYirJOmF18oSUCAwEAAaAmMCQGCSqGSIb3DQEJDjEX
MBUwEwYDVR0lBAwwCgYIKwYBBQUHAwIwDQYJKoZIhvcNAQELBQADggEBAMa7s/l3
mAwJi7LsosPS6/VlZwfTdiJAv+WOKN9T1q2JRHsAGRrW9Gz5p7nSBKJxevRaOMwn
XWK0HqmN3y2/lor50jWzqLhM4TnbKsakXnEIo90XgHoy+n0DL0296Lg/xoXrRgrh
2o3rtZTc+irqUzTRM7Q1F76LNmgtEXqvbOm6Gx2dASPhVAAfylRBCTyz2dYwg2vM
kwt4e5bTvpze/xyTyI8Pydq09YYJe0+a2cHSgcoyGoWXjIK4CUxjBNXAFxSPCcS3
5JRkBnyGo+KL+XtuK9yCX7xBFkwLybK7Mj4TeGiwDsR/0SwqyWGb7Q2m58ay8RVm
pmAIEs21M3236Z4=
-----END CERTIFICATE REQUEST-----
````

Certs are encoded in base64, so decoding the cert data would give you 

````
00�0<1&0$UpicoCTF{read_mycert_3aa80090}10U)	ctfPlayer0"0
	*H
��0
�OvEHՊd_Xޥw>ʮ#3SfEzX%et~凤kG@幽OѿM$Fep\|d8/JS�q$rBBX59 f#Nw&wO<KتrLSh6N_|lk('>&{Y%Rb'{&
w�/]<dT^FN]|%�&0$	*H
	100U%0
+0
	*H
��ƻw	egv"@(S֭D{�lqzZ8']b-5L9*Ƥ^qz2}/M?ƅF
ڍ뵔*S4356h-zl#T�TA	<0k̓x{Ӿȏڴ	{Oҁ2	Lc	ķd|{n+܂_ALɲ2>xh,*a
Ʋf`͵3}
````

## Flag

picoCTF{read_mycert_3aa80090}
