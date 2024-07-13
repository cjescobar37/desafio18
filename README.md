# Análisis de Seguridad de http://vulnweb.com

## Objetivo
Realizar pruebas sobre sistemas informáticos de la misma forma que podría hacerla una persona malintencionada. Conocer las debilidades de la infraestructura, a fin de poder solucionarlas, antes de que una persona malintencionada pudiera aprovecharse de ellas.

## Herramientas Utilizadas
- `dig`
- `whois`
- `geoiplookup`
- `nmap`

## Resultados
### 1. Identificación de sitios web hospedados
- `test.vulnweb.com`
- `testasp.vulnweb.com`
- `rest.vulnweb.com`
- `mail.vulnweb.com`
- `testhtml5.vulnweb.com`

### 2. Información del dominio principal
- **Salida de `dig vulnweb.com`:**
  ```plaintext
; <<>> DiG 9.18.24-0ubuntu0.22.04.1-Ubuntu <<>> vulnweb.com
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 24854
;; flags: qr rd ra; QUERY: 1, ANSWER: 1, AUTHORITY: 4, ADDITIONAL: 9

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 1232
;; QUESTION SECTION:
;vulnweb.com.                   IN      A

;; ANSWER SECTION:
vulnweb.com.            3600    IN      A       44.228.249.3

;; AUTHORITY SECTION:
vulnweb.com.            172799  IN      NS      ns1.eurodns.com.
vulnweb.com.            172799  IN      NS      ns4.eurodns.com.
vulnweb.com.            172799  IN      NS      ns3.eurodns.com.
vulnweb.com.            172799  IN      NS      ns2.eurodns.com.

;; ADDITIONAL SECTION:
ns1.eurodns.com.        164799  IN      AAAA    2610:1c8:b002::107
ns2.eurodns.com.        164799  IN      AAAA    2610:1c8:b001::107
ns3.eurodns.com.        164799  IN      AAAA    2610:1c8:b002::108
ns4.eurodns.com.        164799  IN      AAAA    2610:1c8:b001::108
ns1.eurodns.com.        164799  IN      A       199.167.66.107
ns2.eurodns.com.        164799  IN      A       104.37.178.107
ns3.eurodns.com.        164799  IN      A       199.167.66.108
ns4.eurodns.com.        164799  IN      A       104.37.178.108

;; Query time: 470 msec
;; SERVER: 10.255.255.254#53(10.255.255.254) (UDP)
;; WHEN: Sat Jul 13 10:54:36 -03 2024
;; MSG SIZE  rcvd: 312
  
- **Salida de `whois vulnweb.com`:**
  ```plaintext
 Domain Name: VULNWEB.COM
   Registry Domain ID: 1602006391_DOMAIN_COM-VRSN
   Registrar WHOIS Server: whois.eurodns.com
   Registrar URL: http://www.EuroDNS.com
   Updated Date: 2023-05-26T07:56:15Z
   Creation Date: 2010-06-14T07:50:29Z
   Registry Expiry Date: 2025-06-14T07:50:29Z
   Registrar: EuroDNS S.A.
   Registrar IANA ID: 1052
   Registrar Abuse Contact Email: legalservices@eurodns.com
   Registrar Abuse Contact Phone: +352.27220150
   Domain Status: clientTransferProhibited https://icann.org/epp#clientTransferProhibited
   Name Server: NS1.EURODNS.COM
   Name Server: NS2.EURODNS.COM
   Name Server: NS3.EURODNS.COM
   Name Server: NS4.EURODNS.COM
   DNSSEC: unsigned
   URL of the ICANN Whois Inaccuracy Complaint Form: https://www.icann.org/wicf/
>>> Last update of whois database: 2024-07-13T14:00:31Z <<<

For more information on Whois status codes, please visit https://icann.org/epp

NOTICE: The expiration date displayed in this record is the date the
registrar's sponsorship of the domain name registration in the registry is
currently set to expire. This date does not necessarily reflect the expiration
date of the domain name registrant's agreement with the sponsoring
registrar.  Users may consult the sponsoring registrar's Whois database to
view the registrar's reported date of expiration for this registration.

TERMS OF USE: You are not authorized to access or query our Whois
database through the use of electronic processes that are high-volume and
automated except as reasonably necessary to register domain names or
modify existing registrations; the Data in VeriSign Global Registry
Services' ("VeriSign") Whois database is provided by VeriSign for
information purposes only, and to assist persons in obtaining information
about or related to a domain name registration record. VeriSign does not
guarantee its accuracy. By submitting a Whois query, you agree to abide
by the following terms of use: You agree that you may use this Data only
for lawful purposes and that under no circumstances will you use this Data
to: (1) allow, enable, or otherwise support the transmission of mass
unsolicited, commercial advertising or solicitations via e-mail, telephone,
or facsimile; or (2) enable high volume, automated, electronic processes
that apply to VeriSign (or its computer systems). The compilation,
repackaging, dissemination or other use of this Data is expressly
prohibited without the prior written consent of VeriSign. You agree not to
use electronic processes that are automated and high-volume to access or
query the Whois database except as reasonably necessary to register
domain names or modify existing registrations. VeriSign reserves the right
to restrict your access to the Whois database in its sole discretion to ensure
operational stability.  VeriSign may restrict or terminate your access to the
Whois database for failure to abide by these terms of use. VeriSign
reserves the right to modify these terms at any time.

The Registry database contains ONLY .COM, .NET, .EDU domains and
Registrars.
Domain Name: vulnweb.com
Registry Domain ID: D16000066-COM
Registrar WHOIS Server: whois.eurodns.com
Registrar URL: http://www.eurodns.com
Updated Date: 2023-05-26T10:04:20Z
Creation Date: 2010-06-14T00:00:00Z
Registrar Registration Expiration Date: 2025-06-13T00:00:00Z
Registrar: Eurodns S.A.
Registrar IANA ID: 1052
Registrar Abuse Contact Email: legalservices@eurodns.com
Registrar Abuse Contact Phone: +352.27220150
Domain Status: clientTransferProhibited http://www.icann.org/epp#clientTransferProhibited
Registry Registrant ID:
Registrant Name: Acunetix Acunetix
Registrant Organization: Acunetix Ltd
Registrant Street: 3rd Floor,, J&C Building,, Road Town
Registrant City: Tortola
Registrant State/Province:
Registrant Postal Code: VG1110
Registrant Country: VG
Registrant Phone: +1.23456789
Registrant Fax:
Registrant Email: administrator@acunetix.com
Registry Admin ID:
Admin Name: Acunetix Acunetix
Admin Organization: Acunetix Ltd
Admin Street: 3rd Floor,, J&C Building,, Road Town
Admin City: Tortola
Admin State/Province:
Admin Postal Code: VG1110
Admin Country: VG
Admin Phone: +1.23456789
Admin Fax:
Admin Email: administrator@acunetix.com
Registry Tech ID:
Tech Name: Acunetix Acunetix
Tech Organization: Acunetix Ltd
Tech Street: 3rd Floor,, J&C Building,, Road Town
Tech City: Tortola
Tech State/Province:
Tech Postal Code: VG1110
Tech Country: VG
Tech Phone: +1.23456789
Tech Fax:
Tech Email: administrator@acunetix.com
Name Server: ns1.eurodns.com
Name Server: ns2.eurodns.com
Name Server: ns3.eurodns.com
Name Server: ns4.eurodns.com
DNSSEC: unsigned
URL of the ICANN Whois Inaccuracy Complaint Form: https://www.icann.org/wicf/
>>> Last update of WHOIS database: 2024-07-13T14:00:45Z <<<

For more information on Whois status codes, please visit https://icann.org/epp

Please email the listed admin email address if you wish to raise a legal issue.

The Data in EuroDNS WHOIS database is provided for information purposes only.
The fact that EuroDNS display such information does not provide any guarantee
expressed or implied on the purpose for which the database may be used, its
accuracy or usefulness. By submitting a WHOIS query, you agree that you will
use this Data only for lawful purposes and that, under no circumstances will
you use this Data to:

(1) allow, enable, or otherwise support the transmission of mass unsolicited,
commercial advertising or solicitations via e-mail (spam); or
(2) enable high volume, automated, electronic processes that apply to EuroDNS
(or its systems). EuroDNS reserves the right to modify these terms at any time.

By submitting this query, you agree to abide by the above policy.
root@DESKTOP-HD1ARV7:/home/cristian# dig test.vulnweb.com

; <<>> DiG 9.18.24-0ubuntu0.22.04.1-Ubuntu <<>> test.vulnweb.com
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 49583
;; flags: qr rd ra; QUERY: 1, ANSWER: 1, AUTHORITY: 4, ADDITIONAL: 9

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 1232
;; QUESTION SECTION:
;test.vulnweb.com.              IN      A

;; ANSWER SECTION:
test.vulnweb.com.       3600    IN      A       44.228.249.3

;; AUTHORITY SECTION:
vulnweb.com.            172318  IN      NS      ns3.eurodns.com.
vulnweb.com.            172318  IN      NS      ns4.eurodns.com.
vulnweb.com.            172318  IN      NS      ns1.eurodns.com.
vulnweb.com.            172318  IN      NS      ns2.eurodns.com.

;; ADDITIONAL SECTION:
ns1.eurodns.com.        165538  IN      AAAA    2610:1c8:b002::107
ns2.eurodns.com.        165538  IN      AAAA    2610:1c8:b001::107
ns3.eurodns.com.        165538  IN      AAAA    2610:1c8:b002::108
ns4.eurodns.com.        165538  IN      AAAA    2610:1c8:b001::108
ns1.eurodns.com.        165538  IN      A       199.167.66.107
ns2.eurodns.com.        165538  IN      A       104.37.178.107
ns3.eurodns.com.        165538  IN      A       199.167.66.108
ns4.eurodns.com.        165538  IN      A       104.37.178.108

;; Query time: 150 msec
;; SERVER: 10.255.255.254#53(10.255.255.254) (UDP)
;; WHEN: Sat Jul 13 11:02:37 -03 2024
;; MSG SIZE  rcvd: 317

## Indentificacion de IP's de subdominios:

root@DESKTOP-HD1ARV7:/home/cristian# dig dev.vulnweb.com

; <<>> DiG 9.18.24-0ubuntu0.22.04.1-Ubuntu <<>> dev.vulnweb.com
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 25944
;; flags: qr rd ra; QUERY: 1, ANSWER: 1, AUTHORITY: 4, ADDITIONAL: 9

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 1232
;; QUESTION SECTION:
;dev.vulnweb.com.               IN      A

;; ANSWER SECTION:
dev.vulnweb.com.        3600    IN      A       44.228.249.3

;; AUTHORITY SECTION:
vulnweb.com.            172031  IN      NS      ns1.eurodns.com.
vulnweb.com.            172031  IN      NS      ns3.eurodns.com.
vulnweb.com.            172031  IN      NS      ns4.eurodns.com.
vulnweb.com.            172031  IN      NS      ns2.eurodns.com.

;; ADDITIONAL SECTION:
ns1.eurodns.com.        164031  IN      AAAA    2610:1c8:b002::107
ns2.eurodns.com.        164031  IN      AAAA    2610:1c8:b001::107
ns3.eurodns.com.        164031  IN      AAAA    2610:1c8:b002::108
ns4.eurodns.com.        164031  IN      AAAA    2610:1c8:b001::108
ns1.eurodns.com.        164031  IN      A       199.167.66.107
ns2.eurodns.com.        164031  IN      A       104.37.178.107
ns3.eurodns.com.        164031  IN      A       199.167.66.108
ns4.eurodns.com.        164031  IN      A       104.37.178.108

;; Query time: 190 msec
;; SERVER: 10.255.255.254#53(10.255.255.254) (UDP)
;; WHEN: Sat Jul 13 11:07:24 -03 2024
;; MSG SIZE  rcvd: 316

##Encontramos la Geolocalizacion de los sitios consultados:

geoiplookup 35.81.188.86
GeoIP Country Edition: US, United States
geoiplookup 44.238.29.244
GeoIP Country Edition: US, United States
geoiplookup 44.228.249.3 
GeoIP Country Edition: US, United States

##Utilizacion de nmap para obtener cualquier otra informacion adicional:

nmap 35.81.188.86 
Starting Nmap 7.80 ( https://nmap.org ) at 2024-07-13 11:47 -03
Nmap scan report for ec2-35-81-188-86.us-west-2.compute.amazonaws.com (35.81.188.86)
Host is up (0.26s latency).
Not shown: 998 filtered ports
PORT     STATE SERVICE
80/tcp   open  http
8080/tcp open  http-proxy

nmap 44.238.29.244
Starting Nmap 7.80 ( https://nmap.org ) at 2024-07-13 11:49 -03
Nmap scan report for ec2-44-238-29-244.us-west-2.compute.amazonaws.com (44.238.29.244)
Host is up (0.26s latency).
Not shown: 999 filtered ports
PORT   STATE SERVICE
80/tcp open  http

## Conclusión
Este documento proporciona una guía paso a paso para realizar pruebas de ethical hacking sobre el sitio http://vulnweb.com/. Siguiendo esta guía, se puede identificar sitios web hospedados, obtener información de dominio, direcciones IP, geolocalización, y realizar escaneos de puertos para descubrir posibles vulnerabilidades.
