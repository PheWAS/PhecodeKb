PhecodeKbHtnHotn V2 includes chapters for two conditions (cn): hypertension (htn) and hypotension (hotn).  Each chapter includes positive associations between phecodes and the condition. Negative associations, where one condition down modulates the other, are not represented except as they occur as positive associations in the chapter for the paired condition. 

In aggregate, phecodes are assigned KB-status =1 if they have associations in the hypotension chapter and no association in the hypertension chapter, 3 for the reverse, and 4 if they have associations in both chapters.

Each chapter has sections for three sources: phecodeX taxonomy, literature review of epidemiology and the VanderbiltDDx knowledgebase.  The design principles, provenance of the sources and population of the hypertension chapter were reported in Stead WW, Lewis A, Giuse, NB, Koonce, TY, Bastarache, L. Knowledgebase strategies to aid interpretation of clinical correlation research. J Am Med Inform Assoc. 2023;30:1257-1265. DOI: 10.1093/jamia/ocad078. PMID: 37164621 PMCID: PMC10280353.  Extension of the structure to support paired chapters for conditions at opposite ends of a clinical spectrum is reported in a manuscript that is currently under review.

I – htn_hotn tab (aggregate knowledgebase pf positive associations with hypertension and/or hypotension)

|Column label	| KB chapters	| Meaning of column label	 | Values |
|-------------|-------------|--------------------------|-------|
|phecode|		| phecodeX v1	|       |
|phecode_string|   		|phecode label|        |	
|htn_hotn_kb|	Aggregate|	KB-status	| 0=none, 1=hypotension, 3=hypertension, 4=both|
|htn_hotn_p	|Aggregate|	Phecode tree association	|0=none, 1=hypotension, 3=hypertension, 4=both|
|htn_hotn_l	|Aggregate	|Literature association	|0=none, 1=hypotension, 3=hypertension, 4=both|
|htn_hotn_v	|Aggregate	|VDDxKB association	|0=none, 1=hypotension, 3=hypertension, 4=both|
|htn_kb	|Hypertension	|Chapter status|	0=none, 3=positive association|
|htn_p	|Hypertension	|Phecode tree association	|0=none, 3=positive association|
|htn_l	|Hypertension	|Literature association	|0=none, 3=positive association|
|htn_v	|Hypertension	|VDDxKB association	|0=none, 3=positive association|
|hotn_kb	|Hypotension|	Chapter status	|0=none, 3=positive association|
|hotn_p	|Hypotension	|Phecode tree association	|0=none, 3=positive association|
|hotn_l	|Hypotension	|Literature association	|0=none, 3=positive association|
|hotn_v	|Hypotension	|VDDxKB association|	0=none, 3=positive association|

 
II – htn & hotn tabs (chapters hypertension and hypotension)

|Column label|	KB chapters	|Meaning of column label	|Values|
|------------|------------|------------------------|-------|
|phecode|		|phecodeX v1	|       |
|phecode_string|		       |phecode label|      |	
|cn_kb|	Aggregate|	Chapter status	|3=positive association|
|cn_p|	Phecode tree|	Section status	|blank=none, 3=positive association|
|pt	|Phecode tree	|Type of association	|Blank=none, 1=pt_1, 4=multimap (1 trumps 4) |
|pt_1	|Phecode tree	|phecode map includes ICD for condition	|Blank=none, 1=true|
|l_pt	|Phecode tree|	Literature association maps to ICD that multimaps to a phecode without a direct association	|Blank=none,  4=true|
|ltid_pt|	Phecode tree|	Litid for term associated with the multimap	|Blank=none, ltids delimited by “|”|
|v_pt|	Phecode tree	|VDDxKB association maps to ICD that multimaps to a phecode without a direct association	|Blank=none,  4=true|
|dxid_pt	|Phecode tree	|dxid for term associated with the multimap	|Blank=none, dxid delimited by “|”|
|cn_l	|Literature|	Section status	|blank=none, 3=positive association|
|l_cn_pc|	Literature|	Positive association from condition to phecode|	See cn_pc association type codes|
|l_pc_cn|	Literature	|Positive association from phecode to condition	|See pc_cn association type codes|
|l_mt|	Literature	|Literature term to phecode mapping type |	See mapping type table|
|ltid|	Literature|	Literature term ID|	5 digit number (10001-99999)|
|cn_v	|VDDxKB|	Section status	|blank=none, 3=positive association|
|v_cn_pc	|VDDxKB	|Positive association from condition to phecode|	See cn_pc association type codes|
|v_pc_cn|	VDDxKB|	Positive association from phecode to condition	|See pc_cn association type codes
|v_mt	|VDDxKB|	Diagnosis name to phecode mapping type |	See mapping type table|
|dxid	|VDDxKB	|Literature term ID	|5 digit number (10000-19999)|
 
cn - condition (e.g. htn or hotn)                                    
pc  - phecode

cn_pc & pc_cn association type codes:
0 none
2 co-occurrence /s clear cause & effect
3 system (part of constellation /s clear cause & effect)
4 risk factor
5 cause

Source term to phecode mapping types
|mapping type|Source|ICD|phecode|coverage|
|------------|-----|---|--------|--------|
|1a|1|1|1|full|
|1b|1|>1|1|full|
|2a|1|1|1|phecode is subset of source|
|2b|1|>1|1|pheecode is subset of source|
|2c|1|>1|>1|phecode is subset of source|
|3a|1|1|1|source is a subset of phecode|
|3d|1|1|>1|source is a subset of phecode|
|3b|1|>1|1|source is a subset of phecode|
|3c|1|>1|>1|source is a subset of pheecode|


III – htn_lit and hotn_lit tabs (literature association detail)

For each condition, the literature section structures the associations by classification, then by direction of the association (from condition to phecode (cn_pc), or the reverse (pc_cn)), and then by association type code.

|Condition	|Classification # |	Short name	| Name|
|-----------|----------------|------------|-----|
|Hypertension	|1001|	hypertension	|Hypertension|
|Hypertension	|1002	|ish|	Isolated Systolic Hypertension|
|Hypotension	|1003	|oh	|Orthostatic hypotension|
|Hypotension|	1004	|d_sep_sh	|Distributive septic shock|
|Hypotension	|1005	|d_nsh_sh|	Distributive non-septic shock|
|Hypotension	|1006|	cardiac _sh	|Cardiac shock|
|Hypotension	|1007|	hypov_sh_nh	|Hypovolemic non-hemorrhagic shock|
|Hypotension|	1008|	hypov_sh_h	|Hypovolemic hemorrhagic shock|
|Hypotension|	1009	|obstructive_sh|	obstructive shock|

Each tab includes 3 header rows, the 1st 2 are a human readable format, the 3rd has unique column names for computer processing. The column names in the following data dictionary refer to the 3rd row.
|Column label|	Meaning of column label	|Values|
|------------|-------------------------|------|
|phecode|	phecodeX v1|	LL_### to LL_###.###|
|phecode_string|	phecode label	|text string|
|l_mt	|Mapping type for literature term to phecode| 	See mapping type table|
|ltid|	Literature term ID	|5 digit number (10001-99999)|
|l_term	|Literature term|	text string|
|cn_pc-classification#|	Positive association from condition/classification to phecode|	See cn_pc association type codes|
|pc_cn_classification#|	Positive association from phecode to classification/condition|	See pc_cn association type codes|
Note: last two columns are paired and repeat for each classification of the condition

 
IV – htn_vddx and hotn_vddx tabs (VDDxKB association detail)
For each condition, the VDDxKB section structures the associations by diagnoses representing the condition, then by direction of the association (from condition to phecode (cn_pc), or the reverse (pc_cn)), and then by link type (LT) and frequency/evoking strength (FE). Manifestations of the association are represented alongside.

Diagnoses representing the condition
|Condition	|cxid	|Diagnosis name|
|----------|-----|--------------|
|Hypertension|	10157|	Essential hypertension|
|Hypertension|10158|	Malignant hypertension|
|Hypotension|	10425|	Hypovolemic shock|
|Hypotension	|10474|	Cardiogenic shock|
|Hypotension	|10475|	Pyrogenic shock|
|Hypotension|	10505|	Heat exhaution|

Manifestations related to the conditions
|Condition|	mxid	|Short name|	Expansion|
|---------|-----|----------|-----------|
|Hypertension|	21264	|DBP 95-125|   |	
|Hypertension|	21265|	DBP >125|	    |
|Hypertension	|21302	| PP inc|	Increased Pulse pressure|
|Hypotension|	21303|	PP narrow	|Narrow pulse pressure|
|Hypotension|	21268|	Orthostatic|	Orthostatic drop on Physical Exam|
|Hypotension|	21270|	SBP 90-110	|
|Hypotension	|21271	|SBP <90	|     |
|Hypotension|	23387	|DBP <60	|   |
|Hypertension	|20431	|Exacerbation|	Hx of recent exacerbation of Htn|
|Hypertension	|21640	|Abrupt onset|	Hx of abrupt onset of Htn|
|Hypertension|	23454	|Resistant to rx|	Htn resistant to treatment|
|Hypertension|	21269|	Paroxysmal|	Paroxysmal hypertension|
|Hypertension|	23110|	SBP arms > legs|     |	
|Both|	20229|	Bradycardia	|
|Both|	21587	Tachycardia|	  |
|Both|	20102	|Age 16-25|	 |
|Both	|20103	|Age 26-55|	   |
|Both|	20104	|Age >55|	   |
|Both	|21417	|Birth female	|    |
|Both	|21418|	Birth male|      |	

Each tab includes 3 header rows, the 1st 4 are a human readable format, the 5th has unique column names for computer processing. The column names in the following data dictionary refer to the 3rd row.
|#	Column| label|	Meaning of column label	|Values|
|-------|-------|------------------------|-------|
|1|	phecode|	phecodeX v1|	LL_### to LL_###.###|
|2|	phecode_string|	phecode label	|text string|
|3|	v_mt|	Mapping type for diagnosis name to phecode	|See mapping type table|
|4|	dxid|	Diagnosis ID #	|5 digit number (10000-19999)|
|5|	dxname|	Diagnosis name	|text string|
|6|	p|	Prevalence |	1-5|
|7|	cn_pc_cxid_fe	|Frequency & evoking strength of cxid for dxid (and by map to phecode)|	2 digit number, 1st is frequency (0-5), 2nd is evoking strength(0-5)|
|8|	cn_pc_cxid_lt	|Link type of cxid for dxid (and by map to phecode)	|Letter (A=cause, D=risk fx, E=system)|
|9|	pc_cn_cxid_fe|	Frequency & evoking strength of dxid (and by map to phecode) for cxid|	2 digit number, 1st is frequency (0-5), 2nd is evoking strength(0-5)|
|10|	pc_cn_cxid_lt	|Link type of dxid (and by map to phecode) for cxid|	Letter (A=cause, D=risk fx, E=system)|
|11|	Xmxid_fe|	Frequency & evoking strength of mxid for dxid (and by map to phecode)|	2 digit number, 1st is frequency (0-5), 2nd is evoking strength(0-5)|
Note: lines 7-10 repeat for each cxid related to the condition
            Line 11 repeats for each mxid related to the condition


