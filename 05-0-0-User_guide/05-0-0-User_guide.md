## User guide

### Administration

#### Manage analyzer template
TheHive will display the analysis summary the same way for all analyzers: display a tag using taxonomies and level color.

##### List analyzer templates
The management page is accessible from the header menu through the Admin > Analyzer templates menu and required a use with the manageAnalyzerTemplate permission (refer to Profiles and permissions).
![](/media/05-3-0-analyzer-template.png)

Analyzer templates are still customisable via the UI and can also be imported.

##### Import analyzer templates
TheHive Project provides a set of analyzer templates (we use the same report-templates.zip archive for backward compatibility reasons).

The template archive is available at https://download.thehive-project.org/report-templates.zip.

To import the zip file, click on the Import templates, this opens the import dialog. Drop the zip files or click to select it from your storage and finally click Yes, import template archive.

![](/media/05-3-1-import-analyzer-template.png)

Note that analyzer templates are global and common to all the organisations.

#### User Profiles management

##### Permissions
A Profile is a set of permissions attached to a User and an Organisation. It defines what the user can do on an object hold by the organisation. TheHive has a finite list of permissions:

- manageOrganisation (1) : the user can create, update an organisation
- manageConfig (1): the user can update configuration
- manageProfile (1): the user can create, update and delete profiles
- manageTag (1): the user can create, update and delete tags
- manageCustomField (1): the user can create, update and delete custom fields
- manageCase: the user can create, update and delete cases
- manageObservable: the user can create, update and delete observables
- manageAlert: the user can create, update and import alerts
- manageUser: the user can create, update and delete users
- manageCaseTemplate: the user can create, update and delete case template
- manageTask: the user can create, update and delete tasks
- manageShare: the user can share case, task and observable with other organisation
- manageAnalyse (2): the user can execute analyse
- manageAction (2): the user can execute actions
- manageAnalyzerTemplate (2): the user can create, update and delete analyzer template (previously named report template)

(1) Organisations, configuration, profiles and tags are global objects. The related permissions are effective only on “admin” organisation. (2) Actions, analysis and template is available only if Cortex connector is enabled

**NOTE**

**Read** information doesn’t require specific permission. By default, users in an organisation can see all data shared with that organisation (cf. shares, discussed in Organisations,Users and sharing).

##### Profiles
We distinguish two types of profiles:

- Administration Profiles
- Organisation Profiles

The management page is accessible from the header menu through the Admin > Profiles menu and required a use with the manageProfile permission (refer to the section above).

TheHive comes with default profiles but they can be updated and removed (if not used). New profiles can be created.

![](/media/05-2-0-profiles-list.png)

Once the New Profile button is clicked, a dialog is opened asking for the profile type, a name for the profile and a selection of permissions. Multiple selection can be made using CTRL+click.

![](/media/05-2-1-add-profile.png)

If it is used, a profile can’t be remove but can be updated.

Default profiles are:

- admin: can manage all global objects and users. Can’t create case.
- analyst: can manage cases and other related objects (observables, tasks, …), including shring them
- org-admin: all permissions except those related to global objects
- read-only: no permission

##### Observable types
You can edit observable types in the administrator panel.

Admin > Observable
![](/media/05-0-0-7-observable-edit.png)

### Alerts

### Responders

#### Responders list
-	Symantec Endpoint Protection Unquarantine Host_0_1
-	AMPforEndpoints_SCDAdd_1_0
-	Crowdstrike_Falcon_Custom_IOC_API_1_0
-	Symantec Messaging Gateway Unblock Email_0_1
-	Symantec Messaging Gateway Block Domain_0_1
-	Check Point Block IP_0_1
-	SendGrid_1_0
-	Check Point Unblock IP_0_1
-	Redmine_Issue_1_0
-	DNS-RPZ_1_0
-	Info Blox Block IP_0_1
-	Info Blox Block Domain_0_1
-	AMPforEndpoints_MoveGUID_1_0
-	RT4-CreateTicket_1_0
-	Symantec Messaging Gateway Block Email_0_1
-	Mailer_1_0
-	KnowBe4_1_0
-	Velociraptor_Flow_0_1
-	DomainToolsIris_AddRiskyDNSTag_1_0
-	Virustotal_Downloader_0_1
-	Wazuh_1_0
-	Symantec Endpoint Protection Unblock Hash_0_1
-	ZEROFOX_Close_alert_1_0
-	Minemeld_1_0
-	Umbrella_Blacklister_1_1
-	ZEROFOX_Takedown_request_1_0
-	Symantec Endpoint Protection Quarantine Host_0_1
-	DomainToolsIris_CheckMaliciousTags_1_0
-	Symantec Messaging Gateway Unblock IP_0_1
-	Symantec Messaging Gateway Block IP_0_1
-	AMPforEndpoints_IsolationStart_1_0
-	AMPforEndpoints_IsolationStop_1_0
-	QRadar_Auto_Closing_Offense_1_0
-	Symantec Endpoint Protection Block Hash_0_1
-	Info Blox Delete Rule_0_1
-	Symantec Messaging Gateway Unblock Domain_0_1
-	AMPforEndpoints_SCDRemove_1_0

### Analyzers

#### Analyzers list
-	IPVoid_1_0
-	OpenCTI_SearchObservable_1_0
-	SEKOIAIntelligenceCenter_Indicators_1_0
-	SEKOIAIntelligenceCenter_Context_1_0
-	HIBP_Query_2_0
-	DNSSinkhole_1_0
-	DomainToolsIris_Investigate_1_0
-	Cyberprotect_ThreatScore_1_0
-	Autofocus_SearchJSON_1_0
-	DomainTools_Reputation_2_0
-	VirusTotal_GetReport_3_0
-	MaxMind_GeoIP_4_0
-	FireEyeiSight_1_0
-	Malwares_GetReport_1_0
-	Mnemonic_pDNS_Public_3_0
-	DomainTools_Risk_2_0
-	PassiveTotal_Osint_2_0
-	CIRCLPassiveDNS_2_0
-	CyberChef_FromHex_1_0
-	PassiveTotal_Passive_Dns_2_1
-	Shodan_Host_1_0
-	DomainTools_WhoisLookupUnparsed_2_0
-	PassiveTotal_Host_Pairs_2_0
-	Hunterio_DomainSearch_1_0
-	CyberChef_FromCharCode_1_0
-	MISPWarningLists_2_0
-	DomainTools_ReverseIPWhois_2_0
-	AbuseIPDB_1_0
-	TorProject_1_0
-	CIRCLPassiveSSL_2_0
-	Fortiguard_URLCategory_2_1
-	Splunk_Search_User_Agent_3_0
-	Yara_2_0
-	EmergingThreats_DomainInfo_1_0
-	DNSDB_DomainName_2_0
-	PhishTank_CheckURL_2_1
-	IPinfo_Hosted_Domains_1_0
-	SpamhausDBL_1_0
-	PassiveTotal_Trackers_2_0
-	ThreatResponse_1_0
-	FileInfo_7_0
-	Maltiverse_Report_1_0
-	BackscatterIO_GetObservations_1_0
-	OTXQuery_2_0
-	Investigate_Sample_1_0
-	MetaDefenderCloud_Reputation_1_0
-	Autofocus_SearchIOC_1_0
-	Splunk_Search_Mail_Email_3_0
-	LastInfoSec_1_0
-	Patrowl_GetReport_1_0
-	NSRL_1_0
-	PhishingInitiative_Scan_1_0
-	C1fApp_1_0
-	RecordedFuture_risk_1_0
-	Nessus_2_0
-	SecurityTrails_Passive_DNS_1_0
-	JoeSandbox_File_Analysis_Inet_2_0
-	Virusshare_2_0
-	GreyNoise_2_3
-	DomainTools_ReverseIP_2_0
-	Yeti_1_0
-	StaxxSearch_1_0
-	SinkDB_1_1
-	MalwareBazaar_1_0
-	Robtex_Forward_PDNS_Query_1_0
-	WOT_Lookup_2_0
-	Splunk_Search_Hash_3_0
-	Autofocus_GetSampleAnalysis_1_0
-	VirusTotal_Scan_3_0
-	EmergingThreats_IPInfo_1_0
-	Shodan_ReverseDNS_1_0
-	Shodan_Host_History_1_0
-	PassiveTotal_Whois_Details_2_0
-	Urlscan_io_Search_0_1_1
-	DomainTools_WhoisLookup_2_0
-	PassiveTotal_Malware_2_0
-	DomainTools_ReverseNameServer_2_0
-	IntezerCommunity_1_0
-	DNSDB_IPHistory_2_0
-	GoogleSafebrowsing_2_0
-	PassiveTotal_Enrichment_2_0
-	PayloadSecurity_File_Analysis_1_0
-	Msg_Parser_3_0
-	DomainMailSPFDMARC_Analyzer_1_1
-	PassiveTotal_Unique_Resolutions_2_0
-	Splunk_Search_User_3_0
-	CuckooSandbox_Url_Analysis_1_2
-	BackscatterIO_Enrichment_1_0
-	Hashdd_Detail_1_0
-	DomainTools_ReverseWhois_2_0
-	Threatcrowd_1_0
-	CyberCrime-Tracker_1_0
-	EmailRep_1_0
-	URLhaus_2_0
-	MISP_2_1
-	TeamCymruMHR_1_0
-	Hashdd_Status_1_0
-	DShield_lookup_1_0
-	EmergingThreats_MalwareInfo_1_0
-	StopForumSpam_1_0
-	DomainTools_HostingHistory_2_0
-	CyberChef_FromBase64_1_0
-	Abuse_Finder_3_0
-	Investigate_Categorization_1_0
-	SecurityTrails_Whois_1_0
-	DomainTools_WhoisHistory_2_0
-	MetaDefenderCloud_Scan_1_0
-	PassiveTotal_Ssl_Certificate_History_2_0
-	Splunk_Search_Other_3_0
-	Malpedia_1_0
-	MetaDefenderCore_Scan_1_0
-	Splunk_Search_Registry_3_0
-	Crt_sh_Transparency_Logs_1_0
-	IPinfo_Details_1_0
-	CERTatPassiveDNS_2_0
-	Urlscan_io_Scan_0_1_0
-	ProofPoint_Lookup_1_0
-	PayloadSecurity_Url_Analysis_1_0
-	Shodan_DNSResolve_1_0
-	Splunk_Search_Mail_Subject_3_0
-	GoogleDNS_resolve_1_0_0
-	DomainToolsIris_Pivot_1_0
-	MetaDefenderCloud_GetReport_1_0
-	Hipposcore_2_0
-	Shodan_InfoDomain_1_0
-	CuckooSandbox_File_Analysis_Inet_1_2
-	JoeSandbox_File_Analysis_Noinet_2_0
-	GoogleVisionAPI_WebDetection_1_0_0
-	TalosReputation_1_0
-	Splunk_Search_IP_3_0
-	TorBlutmagie_1_0
-	SpamAssassin_1_0
-	Splunk_Search_Domain_FQDN_3_0
-	FireHOLBlocklists_2_0
-	NERD_1_0
-	ThreatGrid_1_0
-	Robtex_Reverse_PDNS_Query_1_0
-	PassiveTotal_Ssl_Certificate_Details_2_0
-	VMRay_3_0
-	DNSDB_NameHistory_2_0
-	PhishingInitiative_Lookup_2_0
-	SoltraEdge_1_0
-	Pulsedive_GetIndicator_1_0
-	IBMXForce_Lookup_1_0
-	Splunk_Search_URL_URI_Path_3_0
-	JoeSandbox_Url_Analysis_2_0
-	Censys_1_0
-	Malwares_Scan_1_0
-	Robtex_IP_Query_1_0
-	HippoMore_2_0
-	HybridAnalysis_GetReport_1_0
-	EmlParser_1_2
-	ClamAV_FileInfo_1_1
-	ForcepointWebsensePing_1_0
-	Shodan_Search_2_0
-	Umbrella_Report_1_0
-	PassiveTotal_Components_2_0
-	MetaDefenderCore_GetReport_1_0
-	MalwareClustering_Search_1_0
-	Mnemonic_pDNS_Closed_3_0
-	Splunk_Search_File_Filename_3_0
-	UnshortenLink_1_2
-	Onyphe_Summary_1_0
-	AnyRun_Sandbox_Analysis_1_0

### Cases

#### Observables
Observables are pieces of information added to a case. 

<table style="width: 100%; border: 1px solid #e1e4e5;">
<tbody>
<tr style="height: 33px;">
<td style="height: 33px; text-align: center; border: 1px solid #e1e4e5;" width="154">
autonomous-system
</td>
<td style="height: 33px; text-align: center; border: 1px solid #e1e4e5;" width="154">
fqdn
</td>
<td style="height: 33px; text-align: center; border: 1px solid #e1e4e5;" width="154">
mail
</td>
<td style="height: 33px; text-align: center; border: 1px solid #e1e4e5;" width="154">
registry
</td>
</tr>
<tr style="height: 33px;">
<td style="height: 33px; text-align: center; border: 1px solid #e1e4e5;" width="154">
domain
</td>
<td style="height: 33px; text-align: center; border: 1px solid #e1e4e5;" width="154">
hash
</td>
<td style="height: 33px; text-align: center; border: 1px solid #e1e4e5;" width="154">
mail-subject
</td>
<td style="height: 33px; text-align: center; border: 1px solid #e1e4e5;" width="154">
uri_path
</td>
</tr>
<tr style="height: 33px;">
<td style="height: 33px; text-align: center; border: 1px solid #e1e4e5;" width="154">
file
</td>
<td style="height: 33px; text-align: center; border: 1px solid #e1e4e5;" width="154">
hostname
</td>
<td style="height: 33px; text-align: center; border: 1px solid #e1e4e5;" width="154">
other
</td>
<td style="height: 33px; text-align: center; border: 1px solid #e1e4e5;" width="154">
url
</td>
</tr>
<tr style="height: 33.5px;">
<td style="height: 33.5px; text-align: center; border: 1px solid #e1e4e5;" width="154">
filename
</td>
<td style="height: 33.5px; text-align: center; border: 1px solid #e1e4e5;" width="154">
ip
</td>
<td style="height: 33.5px; text-align: center; border: 1px solid #e1e4e5;" width="154">
regexp
</td>
<td style="height: 33.5px; text-align: center; border: 1px solid #e1e4e5;" width="154">
user-agent
</td>
</tr>
</tbody>
</table>

##### How to add observables into Case


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