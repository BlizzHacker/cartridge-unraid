1|# Unraid Community Applications Dispute Report
2|
3|## Filing
4|**Date:** October 2, 2026
5|**Filed by:** Wade (BlizzHacker) — me@moveweight.com
6|**Repository:** github.com/BlizzHacker/cartridge-unraid
7|**Disputed submission:** "ROMarrNG" — submitted by user "snapetech"
8|**Unraid CA listing (contested):** https://ca.unraid.net/apps/romarrng-0u7zgr30thxjr7
9|
10|---
11|
12|## 1. What happened
13|
14|In August 2026, a user named "snapetech" submitted a fork of our ROMarr project
15|to the Unraid Community Applications repository under the name "ROMarrNG".
16|That submission:
17|
18|- Copied the entire ROMarr codebase from github.com/BlizzHacker/romarr without
19|  authorization or attribution
20|- Retained the original ROMarr branding, architecture, and Unraid CA template
21|  structure
22|- Rebranded it with a slightly different name ("ROMarrNG") to appear as an
23|  independent product
24|- Was submitted to Unraid CA after our original submission was taken down,
25|  making it appear that "ROMarrNG" is a legitimate alternative
26|
27|This is not a fork in the open-source sense. Our repository is MIT-licensed,
28|but the fork removes our branding, removes our name from the CA template
29|description, and presents itself as a separate project. That is not how MIT
30|license works — the license requires attribution and preservation of the
31|copyright notice in all substantial portions of the software.
32|
33|## 2. Evidence
34|
35|### 2a. Code similarity
36|
37|Our v0.9.0 release (2026-09-19) and the "ROMarrNG" submission both contain
38|identical:
39|
40|- Store architecture (queue item tracking, seerr request tracking)
41|- API route structure (/api/v1/*)
42|- Unraid CA template structure (romarr.xml with identical field names)
43|- Docker entrypoint flow
44|- Platform detection logic
45|- Import pipeline (decompress → catalogue → import)
46|
47|We can provide a line-by-line diff on request.
48|
49|### 2b. Branding theft
50|
51|The "ROMarrNG" Unraid CA page (when it was live) used our:
52|
53|- Project name in the description
54|- Feature list (verbatim)
55|- Platform list (verbatim)
56|- Configuration guide structure
57|- "© MoveWeight Studios" reference removed, replaced with nothing
58|
59|### 2c. Submission timeline
60|
61|| Date | Event |
62||------|-------|
63|| 2025-12 | We submit ROMarr v0.7.x to Unraid CA |
64|| 2026-08-08 | Our repo (cartridge-unraid) becomes inaccessible from GitHub — Unraid CA page for our repo was removed |
65|| 2026-08-09 | "ROMarrNG" appears in Unraid CA under snapetech |
66|| 2026-09-19 | We cut v0.9.0, restored our repo visibility |
67|| 2026-09-21 | PR on main repo fails CI (expected — code was in flux) |
68|| 2026-10-02 | We cut v1.0.0 with integration API (our genuine differentiator) |
69|
70|The timing is significant: our submission went down the day before their
71|submission went up.
72|
73|## 3. Our request
74|
75|We request that Unraid Community Applications:
76|
77|1. **Remove the "ROMarrNG" submission** from the CA repository, as it is an
78|   unlicensed (in the attribution sense) and unauthorized fork
79|2. **Restore our original ROMarr submission** (or accept our v1.0.0 resubmission),
80|   which we are prepared to submit immediately
81|3. **Flag the "snapetech" account** for review — this appears to be a
82|   deliberate brand-hijacking submission, not a good-faith fork
83|
84|## 4. Our resubmission
85|
86|We are resubmitting ROMarr at v1.0.0, which includes:
87|
88|- All features that were in the prior submission
89|- New: External Platform API (Cartridge + custom frontend integration)
90|- New: Request tracking with stable request IDs across restarts
91|- New: Startup recovery of in-flight external requests
92|- 2083 passing tests (v0.9.0 had ~2081)
93|- Full OpenAPI documentation for all API routes
94|- NOTICE in the repository root establishing authorship
95|
96|Our repository is public: https://github.com/BlizzHacker/romarr
97|Our CA template repository is public: https://github.com/BlizzHacker/cartridge-unraid
98|
99|## 5. Contact
100|
101|Wade (BlizzHacker)
102|me@moveweight.com
103|GitHub: github.com/BlizzHacker
104|
105|---
106|
107|*This report is filed in good faith. We are happy to provide further evidence,
108|a full code diff, or to meet with Unraid staff to resolve this.*