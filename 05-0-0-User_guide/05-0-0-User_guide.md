## User guide

### Administration

### Alerts

### Cases

#### Observables
Observables are pieces of information added to a case. 

<table style="border-color: #00000;" border="1">
<tbody>
<tr style="height: 33px;">
<td style="height: 33px; text-align: center;" width="154">
autonomous-system
</td>
<td style="height: 33px; text-align: center;" width="154">
fqdn
</td>
<td style="height: 33px; text-align: center;" width="154">
mail
</td>
<td style="height: 33px; text-align: center;" width="154">
registry
</td>
</tr>
<tr style="height: 33px;">
<td style="height: 33px; text-align: center;" width="154">
domain
</td>
<td style="height: 33px; text-align: center;" width="154">
hash
</td>
<td style="height: 33px; text-align: center;" width="154">
mail-subject
</td>
<td style="height: 33px; text-align: center;" width="154">
uri_path
</td>
</tr>
<tr style="height: 33px;">
<td style="height: 33px; text-align: center;" width="154">
file
</td>
<td style="height: 33px; text-align: center;" width="154">
hostname
</td>
<td style="height: 33px; text-align: center;" width="154">
other
</td>
<td style="height: 33px; text-align: center;" width="154">
url
</td>
</tr>
<tr style="height: 33.5px;">
<td style="height: 33.5px; text-align: center;" width="154">
filename
</td>
<td style="height: 33.5px; text-align: center;" width="154">
ip
</td>
<td style="height: 33.5px; text-align: center;" width="154">
regexp
</td>
<td style="height: 33.5px; text-align: center;" width="154">
user-agent
</td>
</tr>
</tbody>
</table>

Perform the following steps to add an observable:

1.	Click Add observable(s) button:
![](/media/05-0-0-add-ovservable.png)

2.	Create new observable(s) window appears:
![](/media/05-0-5-create-new-observable.png)

3.	Select type e.g. ip, domain, url, mail.
If you choose file type, you can upload a file. Zipped archives are supported.
![](/media/05-0-1-drop-observable-file.png)

4.	You can add one single observables or many observables at once - one observable per line.
5.	Select appropriate TLP flag.
6.	(Optional) IOC flag indicates observables classified as True Positive. Only IOC-flagged observables are exported to MISP instances.
7.	(Optional) You can also set  “Has been sighted” toggle to mark observables which have been seen.
8.	(Optional) If you click “Ignore for similarity”, you will disable “Observable seen in other cases” list.
9.	Add tags and/or description.
10.	Click Create observable(s).
On Observable List you can check if observables have been seen in other cases:
-	Black eye: Observable seen in other cases,
-	Red eye: Observable seen in other cases and flagged as IOC there.
![](/media/05-0-2-observable-list.png)

You can display details and check cases where the observable has been seen:
![](/media/05-0-4-observable-details.png)

After uploading file-type observables hashes are automatically calculated:
![](/media/05-0-6-obervable-file-details.png)

If you want to download file observable, it will be zipped and password protected:
![](/media/05-0-3-observable-protected-file.png)

You can run various analyzers (e.g. VirusTotal, MaxMind_GeoIP) and responders (e.g. block IP, domain, e-mail) against observables.

### Organisation

### Reports