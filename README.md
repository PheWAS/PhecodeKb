PhecodeKbHtnHotn V2 includes chapters for two conditions (cn): hypertension (htn) and hypotension (hotn).  Each chapter includes positive associations between phecodes and the condition. Negative associations, where one condition down modulates the other, are not represented except as they occur as positive associations in the chapter for the paired condition. 

In aggregate, phecodes are assigned KB-status =1 if they have associations in the hypotension chapter and no association in the hypertension chapter, 3 for the reverse, and 4 if they have associations in both chapters.

Each chapter has sections for three sources: phecodeX taxonomy, literature review of epidemiology and the VanderbiltDDx knowledgebase.  The design principles, provenance of the sources and population of the hypertension chapter were reported in Stead WW, Lewis A, Giuse, NB, Koonce, TY, Bastarache, L. Knowledgebase strategies to aid interpretation of clinical correlation research. J Am Med Inform Assoc. 2023;30:1257-1265. DOI: 10.1093/jamia/ocad078. PMID: 37164621 PMCID: PMC10280353.  Extension of the structure to support paired chapters for conditions at opposite ends of a clinical spectrum is reported in a manuscript that is currently under review.

I – htn_hotn tab (aggregate knowledgebase pf positive associations with hypertension and/or hypotension)

Column label	KB chapters	Meaning of column label	Values
phecode		phecodeX v1	
phecode_string		phecode label	
htn_hotn_kb	Aggregate	KB-status	0=none, 1=hypotension, 3=hypertension, 4=both
htn_hotn_p	Aggregate	Phecode tree association	0=none, 1=hypotension, 3=hypertension, 4=both
htn_hotn_l	Aggregate	Literature association	0=none, 1=hypotension, 3=hypertension, 4=both
htn_hotn_v	Aggregate	VDDxKB association	0=none, 1=hypotension, 3=hypertension, 4=both
htn_kb	Hypertension	Chapter status	0=none, 3=positive association
htn_p	Hypertension	Phecode tree association	0=none, 3=positive association
htn_l	Hypertension	Literature association	0=none, 3=positive association
htn_v	Hypertension	VDDxKB association	0=none, 3=positive association
hotn_kb	Hypotension	Chapter status	0=none, 3=positive association
hotn_p	Hypotension	Phecode tree association	0=none, 3=positive association
hotn_l	Hypotension	Literature association	0=none, 3=positive association
hotn_v	Hypotension	VDDxKB association	0=none, 3=positive association

 
II – htn & hotn tabs (chapters hypertension and hypotension)

Column label	KB sections	Meaning of column label	Values
phecode		phecodeX v1	
phecode_string		phecode label	
cn_kb	Aggregate	Chapter status	3=positive association
cn_p	Phecode tree	Section status	blank=none, 3=positive association
pt	Phecode tree	Type of association	Blank=none, 1=pt_1, 4=multimap (1 trumps 4) 
pt_1	Phecode tree	phecode map includes ICD for condition	Blank=none, 1=true
l_pt	Phecode tree	Literature association maps to ICD that multimaps to a phecode without a direct association	Blank=none,  4=true
ltid_pt	Phecode tree	Litid for term associated with the multimap	Blank=none, ltids delimited by “|”
v_pt	Phecode tree	VDDxKB association maps to ICD that multimaps to a phecode without a direct association	Blank=none,  4=true
dxid_pt	Phecode tree	dxid for term associated with the multimap	Blank=none, dxid delimited by “|”
cn_l	Literature	Section status	blank=none, 3=positive association
l_cn_pc	Literature	Positive association from condition to phecode	See cn_pc association type codes
l_pc_cn	Literature	Positive association from phecode to condition	See pc_cn association type codes
l_mt	Literature	Literature term to phecode mapping type 	See mapping type table
ltid	Literature	Literature term ID	5 digit number (10001-99999)
cn_v	VDDxKB	Section status	blank=none, 3=positive association
v_cn_pc	VDDxKB	Positive association from condition to phecode	See cn_pc association type codes
v_pc_cn	VDDxKB	Positive association from phecode to condition	See pc_cn association type codes
v_mt	VDDxKB	Diagnosis name to phecode mapping type 	See mapping type table
dxid	VDDxKB	Literature term ID	5 digit number (10000-19999)
 
cn - condition (e.g. htn or hotn)                                     Source term to phecode mapping types
pc  - phecode

cn_pc & pc_cn association type codes:
0 none
2 co-occurrence /s clear cause & effect
3 system (part of constellation /s clear cause & effect)
4 risk factor
5 cause

![image](https://github.com/PheWAS/PhecodeKb/assets/34251274/38e744bf-1e00-41cf-8298-c4d9fe9c3ce3)
