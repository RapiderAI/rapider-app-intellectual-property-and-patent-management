<!-- Rapider Official App SOW & Specification | App #136: Intellectual Property & Patent Management (intellectual-property-and-patent-management) | Domain: LGL -->
# #136 Intellectual Property & Patent Management (`intellectual-property-and-patent-management`) — Scope of Work (SOW)

- **App Number:** `#136`
- **App Key:** `intellectual-property-and-patent-management`
- **Suite / Domain:** Legal, Compliance & Corporate Governance (`LGL` — `Lgl*`)
- **Representative Benchmark (`P1`):** Anaqua (AQX Platform & Anaqua AI)
- **Combined Feature Set Reference:** [../combined-features/136-intellectual-property-and-patent-management-features.md](../combined-features/136-intellectual-property-and-patent-management-features.md)
- **Status:** Official Architecture & Implementation Specification

---

## 1. Executive Outcome & Target Audience

**Rapider Intellectual Property & Patent Management (`intellectual-property-and-patent-management`)** safeguards an organization's crown-jewel intangible assets—patents, trademarks, industrial designs, trade secrets, copyrights, and defensive domains—from R&D invention conception through multi-jurisdiction prosecution, IDS duty-of-candor compliance, virtual patent marking, and disciplined annuity pruning. By integrating directly with `plm` (`MfgProductRevision`), `productcatalog` (`ComProduct`), `employees` / `payroll` (`HrEmployee`, `HrPayrollRun`), `acc` (`FinLegalEntity`), and `accpayable` (`FinSupplierBill`), it eliminates outside-counsel double-docketing blind spots, accidental patent abandonments, and novelty-destroying pre-filing disclosures.

### SME / Startup Fast-Path vs. Enterprise Progressive Disclosure
- **Startup & Mid-Market Fast-Path:** Capture engineer Invention Disclosures (`LglInventionDisclosure`) before conference talks destroy foreign novelty, track Provisional-to-Utility/PCT conversion deadlines (`LglIpAsset`, `LglIpProsecutionAction`), maintain trademark Nice classes & §8/§9 specimens of use, and publish an accurate Virtual Patent Marking schedule (`35 U.S.C. § 287(a)`).
- **Global R&D Enterprise Progressive Disclosure:** Progressively unlock Patent Committee weighted scoring rubrics, DTSA-compliant Trade Secret vaults, automated US `37 CFR 1.56` cross-family IDS citation propagation (`LglPriorArtReference`), PCT 30/31-month & Unitary Patent validation calculators, dual-control global annuity pruning campaigns (`LglIpRenewalAnnuity`), statutory *ArbnErfG* / milestone inventor awards (`LglInventorAward`), and privileged FTO vaults.

### Measurable Business Outcomes
1. **Zero Missed Statutory PTO Deadlines or Accidental Crown-Jewel Abandonments** via tiered statutory deadline escalations and mandatory dual-control (`IP Counsel` + `Business Unit Owner`) approval on `ABANDON_PRUNE` instructions.
2. **100% Cross-Family IDS Duty-of-Candor Compliance (`37 CFR 1.56`)** by automatically flagging copending US family applications whenever prior art is cited in EPO, JPO, CNIPA, or sibling continuations.
3. **15%–30% Reduction in Wasted Annuity Maintenance Spend** through product-mapped (`ComProduct` / `MfgProductRevision`) ROI pruning campaigns on obsolete or non-practiced filings.
4. **Zero False-Marking Exposure & Maximum Infringement Damages Recovery** via automated Virtual Patent Marking updated dynamically as patents issue or expire.

### Top 6 Global Benchmark Summary (`P1`–`P6`)
Synthesizes **Anaqua AQX (`P1`)** invention workflows, AI IDS cross-citation, Annuities Decision Workspace, and AI Patent Auto-Classifier; **Clarivate IPfolio on Salesforce (`P2`)** Patent-to-Product virtual marking and outside counsel spend alignment; **Questel Equinox & Orbit (`P3`)** family trees, PCT cost modeling, and trade secret vaults; **Dennemeyer DIAMS iQ (`P4`)** 300+ jurisdiction statutory rules and Nice trademark classes; **Alt Legal (`P5`)** zero-friction trademark specimen/status workflows; and **SAP IP & PLM (`P6`)** tight linkage to `plm`, `payroll`, `acc`, and `billing`.

---

## 2. In-Scope, Out-of-Scope & Suite Ownership Boundaries

### In-Scope (`intellectual-property-and-patent-management`)
- R&D Invention Disclosure intake, novelty-bar alerts, and Patent Committee scoring (`LglInventionDisclosure`).
- Patent, trademark, design, trade secret, copyright, and domain family trees & national assets (`LglIpFamily`, `LglIpAsset`) with chain-of-title recordation.
- Statutory prosecution docketing (`LglIpProsecutionAction`) and cross-family IDS prior-art citation propagation (`LglPriorArtReference`).
- Patent maintenance annuities, trademark §8/§9/§71 renewals, and dual-control pruning campaigns (`LglIpRenewalAnnuity`).
- Patent-to-Product virtual patent marking, inventor milestone awards (`LglInventorAward`), privileged FTO vaults, and trademark/brand watch disputes (`LglIpWatchDispute`).

### Out-of-Scope (Delegated to Peer Rapider Apps)
- Engineering CAD/BOM authoring and engineering change orders (owned by `plm` / `bom`).
- Commercial product SKU catalog and pricing (owned by `productcatalog`).
- Employee payroll tax calculation and net salary disbursement (owned by `payroll`).
- General Ledger intangible asset amortization journals and AP wire execution (owned by `acc` / `accpayable` / `payments`).
- Full courtroom patent infringement litigation eDiscovery review (owned by `#138 litigation-and-ediscovery`).

### Cross-Suite Ownership Contract

| Domain / App | Owns Canonical Models | Integration Contract with `intellectual-property-and-patent-management` |
| :--- | :--- | :--- |
| **`intellectual-property-and-patent-management` (`#136` — This App)** | `LglInventionDisclosure`, `LglIpFamily`, `LglIpAsset`, `LglIpProsecutionAction`, `LglPriorArtReference`, `LglIpRenewalAnnuity`, `LglInventorAward`, `LglIpWatchDispute` | Publishes approved annuity/outside-counsel AP bills, inventor bonus payouts, virtual patent marking feeds, and statutory deadline Home `WorkItem`s. |
| **`plm` & `productcatalog`** | `MfgProductRevision`, `ComProduct` | `LglInventionDisclosure` and `LglIpFamily` link `productIds -> ComProduct[]` and `productRevisionIds -> MfgProductRevision[]` to power Virtual Patent Marking and pruning ROI scores. |
| **`employees` & `payroll`** | `HrEmployee`, `HrPayrollRun` | Inventors and Patent Committee reviewers reference `HrEmployee`; approved `LglInventorAward` milestones emit bonus compensation lines to `payroll`. |
| **`acc`, `accpayable` & `budgeting`** | `FinLegalEntity`, `FinSupplierBill`, `FinBudget` | IP assignees reference `FinLegalEntity`; approved `PAY_RENEW` annuity batches and foreign associate invoices emit `FinSupplierBill`s; 5-year annuity forecasts feed `FinBudget`. |
| **`vendors` & `billing`** | `OpsSupplierProfile`, `FinInvoice` | Outside prosecution counsel and annuity agents reference `OpsSupplierProfile`; outbound IP licensing agreements link royalty schedules to `FinInvoice`. |
| **Rapider Platform** | Identity/RBAC, Files/Drive, Home `WorkItem`, `projectChannelMessage`, `requiredWorkflows` | Drive stores drawings, office actions, assignments, and privileged FTO opinions; Home `WorkItem`s route committee votes, IDS alerts, and pruning sign-offs; IP Copilot runs in `projectChannelMessage`. |

---

## 3. Primary Web Pages & Sidebar Navigation Architecture (12 Pages)

All visible sidebar sections strictly enforce the **Minimum 3 Items per Section Rule** (`Overview`: 3 items, `Prosecution & Brand`: 3 items, `Renewals & Value`: 3 items = 9 visible items; 3 detail/drawer routes hidden with `displayOnMenu: false`).

| # | Route | Page Title | Sidebar Section | Menu Visible | Key Components & UX |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 1 | `ip-dashboard` | IP Portfolio & Docket Command | `Overview` | `true` (Order 1) | KPI cards (Active Patent Families, Registered Marks, 30-Day Statutory Bars, Uncited Cross-Family IDS Items, Annual Annuity Spend `Decimal128`), jurisdiction heatmap, novelty-bar alerts. |
| 2 | `invention-disclosures` | Invention Disclosures (IDF) | `Overview` | `true` (Order 2) | `<rapider-kanban>` triage board (`DRAFT` -> `SUBMITTED` -> `COMMITTEE_REVIEW` -> `APPROVED_PATENT` / `TRADE_SECRET` / `DEFENSIVE_PUB`) + searchable `LglInventionDisclosure` table, `#activeFilterTagsBar`, novelty countdown pill. |
| 3 | `patent-families` | Patents & Trade Secrets | `Overview` | `true` (Order 3) | Hierarchical `LglIpFamily` & `LglIpAsset` table, technology taxonomy tree filter, PCT/National-phase family badges, Trade Secret clean-room badge, chain-of-title status. |
| 4 | `prosecution-docket` | Prosecution Docket & IDS | `Prosecution & Brand` | `true` (Order 4) | `LglIpProsecutionAction` statutory deadline workbench (shortened 3m vs. 6m absolute bar), AI Office Action parser uploader, and Cross-Family IDS (`37 CFR 1.56`) `UNCITED_NEEDS_IDS` alert tab. |
| 5 | `trademarks-domains` | Trademarks, Designs & Domains | `Prosecution & Brand` | `true` (Order 5) | Brand portfolio table (`WORD_MARK`, `LOGO_MARK`, `DESIGN`, `DOMAIN_NAME`), Nice Class (`1–45`) filter chips, §8/§15 specimen-of-use tracker, `<rapider-phone-input>` for foreign associate trademark contacts. |
| 6 | `brand-watch-disputes` | Brand Watch & Oppositions | `Prosecution & Brand` | `true` (Order 6) | `<rapider-kanban>` + table of `LglIpWatchDispute` alerts (Gazette Watches, UDRP Domains, Marketplace Counterfeits, PTAB/EPO Oppositions), similarity score badges. |
| 7 | `annuities-pruning` | Annuities & Pruning Workspace | `Renewals & Value` | `true` (Order 7) | `LglIpRenewalAnnuity` decision grid, AI Pruning ROI score, `PAY_RENEW` vs. dual-control `ABANDON_PRUNE` action flow, 5-year multi-currency maintenance cost forecast chart. |
| 8 | `product-marking-licensing` | Virtual Patent Marking & Value | `Renewals & Value` | `true` (Order 8) | Patent-to-Product matrix linking `LglIpAsset` <-> `ComProduct` / `MfgProductRevision`, live `35 U.S.C. § 287(a)` public marking preview, and privileged FTO opinion vault tab. |
| 9 | `inventor-awards` | Inventor Awards & Recognition | `Renewals & Value` | `true` (Order 9) | `LglInventorAward` milestone ledger (`IDF_APPROVED`, `FIRST_FILING`, `PATENT_GRANTED`), contribution split verification, *ArbnErfG* election deadlines, `payroll` handoff status. |
| 10 | `ip-asset-detail` | IP Family & Asset 360 | *(None)* | `false` | Interactive Patent Family Tree diagram, Claims & Priority chain, Prosecution history, Cross-Family IDS matrix (`LglPriorArtReference`), Assignments, Product coverage, and `projectChannelMessage` IP Copilot + `#btnGoBack`. |
| 11 | `idf-detail` | Invention Disclosure & Committee Scoring | *(None)* | `false` | Technical narrative, Drive sketches, co-inventor `Decimal128` contribution table, Patent Committee 4-axis scorecard, prior-art notes, and 1-click "Convert to Provisional / Trade Secret" action. |
| 12 | `ip-drawer` | Submit IDF / Docket Asset / Watch Alert | *(None)* | `false` | Context-aware sliding drawer for engineer IDF submission, national-phase `LglIpAsset` creation, or `LglIpProsecutionAction` logging with `<rapider-phone-input>` for outside counsel; auto-closes on Save/Cancel with `finally` button reset. |

### Rapider UI & QA Standards Enforced Across All 12 Pages
- **SWR Read Standard:** Initial page reads use `window.rapiderApi.findSWR(entityName, filter)` and `countSWR(entityName, where)` with clean filter payloads (zero manual `isDeleted` where clauses) and defensive client-side filtering (`items = raw.filter(i => i && i.isDeleted !== true)`).
- **Table Actions & Navigation:** Primary identifiers (`idfNumber`, `familyCode`, `assetNumber`, `actionRef`, `annuityRef`) render as `font-semibold text-primary hover:underline cursor-pointer` navigating to detail views/drawers. Zero standalone "View" buttons in `Actions`; Edit uses icon + text (`<i class="fas fa-edit mr-1"></i><span>Edit</span>`); Delete uses icon-only (`<i class="fas fa-trash-alt"></i>` with `title="Delete" aria-label="Delete"`).
- **Search & `#activeFilterTagsBar`:** Instant client-side search across docket numbers, patent/application numbers, mark text, CPC/Nice classes, and inventors paired with HTML-escaped dismissible chips and `[Clear all]`.
- **Contrast & Native Dialog Ban:** All primary and danger buttons enforce `!text-white text-white` and `style="color: #ffffff !important;"`. Zero `window.alert`, `window.confirm`, or `window.prompt` calls.

---

## 4. Canonical Data Models (`Lgl*` — 8 Models)

All models omit `projectId`, use platform UUID `id` (`00000000-xxxx-xxxx-xxxx-xxxxxxxxxxxx` for sample seeds), enforce `Decimal128` for contribution splits, PTO fees, extension surcharges, and awards, and maintain `version: Integer`.

| Model Name | Key Fields & Types | Relationships & External Refs | Invariants & Lifecycle |
| :--- | :--- | :--- | :--- |
| **`LglInventionDisclosure`** | `idfNumber: String`, `title: String`, `technicalProblem: String`, `proposedSolution: String`, `plannedPublicDisclosureDate: Date?`, `isNoveltyUrgent: Boolean`, `inventorsJson: Array<{employeeId, contributionPct: Decimal128, isLeadInventor}>`, `committeeScoresJson: Array<{reviewerId, meritScore, detectabilityScore, valueScore, recommendation}>`, `compositeScore: Decimal128`, `status: Enum(DRAFT, SUBMITTED, COMMITTEE_REVIEW, APPROVED_PROVISIONAL, APPROVED_UTILITY, RETAIN_TRADE_SECRET, DEFENSIVE_PUBLICATION, DECLINED)`, `version: Int` | `inventorsJson[].employeeId -> HrEmployee`, `productRevisionIds -> MfgProductRevision[]`, `attachmentFileIds -> DriveFile[]`, `spawnedFamilyId -> LglIpFamily?`, `reviewWorkItemId -> WorkItem?` | Sum of `inventorsJson[].contributionPct == 100.00` (`Decimal128`); `plannedPublicDisclosureDate` within 30 days sets `isNoveltyUrgent = true` and emits immediate IP Counsel Home `WorkItem`. |
| **`LglIpFamily`** | `familyCode: String`, `familyTitle: String`, `assetCategory: Enum(PATENT, TRADEMARK, INDUSTRIAL_DESIGN, TRADE_SECRET, COPYRIGHT, DOMAIN_GROUP)`, `earliestPriorityDate: Date?`, `technologyTaxonomyCode: String`, `cpcClassCodes: String[]`, `strategicTier: Enum(CORE_CROWN_JEWEL, ACTIVE_COMMERCIAL, DEFENSIVE, LICENSABLE, PRUNE_CANDIDATE)`, `virtualMarkingPublished: Boolean`, `status: Enum(ACTIVE, PARTIALLY_GRANTED, FULLY_EXPIRED, PRUNED_ABANDONED)`, `version: Int` | `sourceIdfId -> LglInventionDisclosure?`, `coveredProductIds -> ComProduct[]`, `coveredRevisionIds -> MfgProductRevision[]`, `licenseContractIds -> CrmContract[]` | `virtualMarkingPublished == true` publishes only child `LglIpAsset`s currently in `GRANTED_REGISTERED` status (automatically excluding pending or expired patents). |
| **`LglIpAsset`** | `assetNumber: String`, `assetSubtype: Enum(PROVISIONAL, UTILITY_NP, CONTINUATION, DIVISIONAL, PCT_INTERNATIONAL, EP_REGIONAL, NATIONAL_PHASE, DESIGN_PATENT, WORD_MARK, LOGO_MARK, TRADE_SECRET_VAULT, DOMAIN_NAME)`, `jurisdictionCode: String(2)`, `applicationNumber: String?`, `filingDate: Date?`, `publicationNumber: String?`, `grantOrRegNumber: String?`, `grantDate: Date?`, `ptaDays: Int`, `calculatedExpirationDate: Date?`, `niceClasses: Int[]`, `chainOfTitleVerified: Boolean`, `reelFrameRef: String?`, `outsideCounselPhoneE164: String?`, `isPrivilegedFtoAttached: Boolean`, `status: Enum(PREPARATION, FILED_PENDING, PUBLISHED, OFFICE_ACTION_OPEN, ALLOWED, GRANTED_REGISTERED, OPPOSED, ABANDONED, EXPIRED)`, `version: Int` | `familyId -> LglIpFamily`, `parentAssetId -> LglIpAsset?`, `assigneeLegalEntityId -> FinLegalEntity`, `outsideCounselSupplierId -> OpsSupplierProfile?`, `assignmentDeedFileId -> DriveFile?`, `ftoOpinionFileId -> DriveFile?` | `PROVISIONAL` assets auto-generate a non-extendable 12-month conversion `LglIpProsecutionAction`; `TRADE_SECRET_VAULT` and `ftoOpinionFileId` enforce clean-room/privilege RBAC isolation. |
| **`LglIpProsecutionAction`** | `actionRef: String`, `actionType: Enum(PROVISIONAL_12M_CONVERSION, PCT_30M_NATIONAL_PHASE, NON_FINAL_OFFICE_ACTION, FINAL_OFFICE_ACTION, NOTICE_OF_ALLOWANCE_ISSUE_FEE, EP_RULE_71_3, IDS_CROSS_CITATION_FILING, TRADEMARK_SEC8_SPECIMEN, OPPOSITION_RESPONSE)`, `mailingOrTriggerDate: Date`, `shortenedStatutoryDueDate: Date`, `finalNonExtendableBarDate: Date`, `currentExtensionMonthUsed: Int`, `extensionFeeAccrued: Decimal128`, `currency: String(3)`, `responseFiledDate: Date?`, `status: Enum(OPEN_UPCOMING, IN_EXTENSION_WINDOW, INSTRUCTIONS_SENT, FILED_COMPLETED, LAPSED)`, `version: Int` | `ipAssetId -> LglIpAsset`, `familyId -> LglIpFamily`, `assignedAttorneyId -> HrEmployee`, `officeActionPdfFileId -> DriveFile?`, `escalationWorkItemId -> WorkItem?` | `shortenedStatutoryDueDate <= finalNonExtendableBarDate`; cannot extend beyond `finalNonExtendableBarDate`. |
| **`LglPriorArtReference`** | `refCode: String`, `citationType: Enum(US_PATENT, US_PGPUB, FOREIGN_PATENT, NON_PATENT_LITERATURE)`, `documentIdentifier: String`, `publicationDate: Date?`, `titleOrCitationText: String`, `originatingJurisdiction: String(2)`, `usMemberCitationMapJson: Array<{usAssetId, status: Enum(UNCITED_NEEDS_IDS, CITED_ON_IDS_FILED, CITED_BY_EXAMINER, NOT_APPLICABLE_CLOSED), idsFiledDate}>`, `version: Int` | `familyId -> LglIpFamily`, `discoveredOnAssetId -> LglIpAsset`, `pdfCopyFileId -> DriveFile?` | Adding a reference to `LglIpFamily` automatically populates `UNCITED_NEEDS_IDS` for every open/pending US `LglIpAsset` in that family and spawns an `IDS_CROSS_CITATION_FILING` action within the 3-month `37 CFR 1.97(b)` fee-free window. |
| **`LglIpRenewalAnnuity`** | `annuityRef: String`, `renewalCycleLabel: String`, `dueDate: Date`, `surchargeGraceEndDate: Date`, `officialPtoFee: Decimal128`, `agentServiceFee: Decimal128`, `surchargeAmount: Decimal128`, `totalAmount: Decimal128`, `currency: String(3)`, `aiPruningRoiScore: Decimal128`, `decision: Enum(PENDING_DECISION, PAY_RENEW, ABANDON_PRUNE)`, `ipCounselApproverId: UUID?`, `businessOwnerApproverId: UUID?`, `paidDate: Date?`, `status: Enum(UPCOMING, UNDER_PRUNING_REVIEW, INSTRUCTED_TO_PAY, PAID_VERIFIED, ABANDONED_CONFIRMED)`, `version: Int` | `ipAssetId -> LglIpAsset`, `annuitySupplierId -> OpsSupplierProfile?`, `supplierBillId -> FinSupplierBill?`, `pruningWorkItemId -> WorkItem?` | **Dual-Control Abandonment Invariant:** Transition to `ABANDON_PRUNE` / `ABANDONED_CONFIRMED` requires BOTH `ipCounselApproverId` AND `businessOwnerApproverId` (`ipCounselApproverId != businessOwnerApproverId`). |
| **`LglInventorAward`** | `awardRef: String`, `milestoneType: Enum(IDF_APPROVED, FIRST_UTILITY_FILING, PATENT_GRANTED, STATUTORY_ARBNERFG_COMPENSATION)`, `grossAwardAmount: Decimal128`, `contributionSharePct: Decimal128`, `currency: String(3)`, `statutoryElectionDeadline: Date?`, `status: Enum(ELIGIBLE_PENDING, APPROVED_FOR_PAYROLL, PAID, WAIVED)`, `version: Int` | `inventorEmployeeId -> HrEmployee`, `idfId -> LglInventionDisclosure`, `ipAssetId -> LglIpAsset?`, `payrollRunId -> HrPayrollRun?`, `approvalWorkItemId -> WorkItem?` | Unique `(inventorEmployeeId, idfId, milestoneType)` preventing duplicate filing/grant payouts for the same inventor milestone. |
| **`LglIpWatchDispute`** | `watchRef: String`, `watchType: Enum(TRADEMARK_GAZETTE_WATCH, DOMAIN_CYBERSQUAT_UDRP, MARKETPLACE_COUNTERFEIT, PATENT_PTAB_OPPOSITION)`, `adverseMarkOrAsset: String`, `adverseApplicantName: String`, `jurisdictionOrPlatform: String`, `oppositionDeadline: Date?`, `similarityScore: Decimal128`, `resolutionOutcome: Enum(OPEN_TRIAGE, MONITORING_NO_ACTION, CEASE_AND_DESIST_SENT, OPPOSITION_FILED, TAKEDOWN_REMOVED, COEXISTENCE_SIGNED, CLOSED)`, `version: Int` | `protectedAssetId -> LglIpAsset`, `assignedCounselId -> HrEmployee`, `evidenceFileId -> DriveFile?`, `workItemId -> WorkItem?` | High-risk hits (`similarityScore >= 0.85` with `oppositionDeadline` <= 30 days) auto-escalate via Home `WorkItem`. |

---

## 5. Core End-to-End User Journeys

### Journey 1: Urgent Pre-Conference Invention Disclosure to Provisional Filing & Inventor Award
1. Principal Battery Engineer opens `#/ip-drawer` and submits `LglInventionDisclosure` (`IDF-2026-0088`) with 2 co-inventors (`60.00%` / `40.00%`), noting an IEEE conference keynote in 12 days (`isNoveltyUrgent == true`).
2. `intellectual-property-and-patent-management` immediately issues an urgent Novelty Bar Home `WorkItem` to Chief IP Counsel; Patent Committee scores the IDF (`91/100` on `#/idf-detail`) and approves `APPROVED_PROVISIONAL`.
3. IP Paralegal spawns `LglIpFamily` (`FAM-BAT-042`) + US Provisional `LglIpAsset` (`63/991,204`) prior to the keynote (preserving worldwide PCT/EP/CN priority!), auto-schedules the non-extendable 12-month Utility/PCT conversion `LglIpProsecutionAction`, and queues `LglInventorAward` bonuses to `payroll`.

### Journey 2: EPO Search Report Triggering Automated US Cross-Family IDS (`37 CFR 1.56`) Compliance
1. Paralegal uploads a European Extended Search Report PDF on `EP-4102998` (`FAM-BAT-019`) in `#/prosecution-docket`; AI PTO Office Action Parser (`IPPM-020`) extracts 4 newly cited foreign patent references.
2. Confirming `lgl.ip.priorArt.register` creates `LglPriorArtReference` records, detects 2 copending US Continuations in `FAM-BAT-019`, flags both `UNCITED_NEEDS_IDS`, and schedules a 90-day fee-free `IDS_CROSS_CITATION_FILING` deadline (`37 CFR 1.97(b)`) via Home `WorkItem`.

### Journey 3: Product-Mapped Annuity Pruning & Dual-Control Abandonment Safeguard
1. On `#/annuities-pruning`, IP Operations Manager reviews Q4 renewals (`\$184,500.00` across 46 patents): 38 patents map to active `ComProduct` SKUs (`CORE_CROWN_JEWEL` -> approved `PAY_RENEW`, emitting a consolidated `FinSupplierBill` to `accpayable`).
2. Eight older patents cover a discontinued v1 legacy module (`aiPruningRoiScore: 14.5`); IP Counsel marks `ABANDON_PRUNE`, which routes a mandatory second-approver Home `WorkItem` to the VP of Engineering (`businessOwnerApproverId != ipCounselApproverId`) before abandonment instructions can be transmitted.

### Journey 4: Live Virtual Patent Marking (`35 U.S.C. § 287(a)`) Lifecycle
1. When US Utility Patent `12,104,882` transitions from `ALLOWED` to `GRANTED_REGISTERED` on `#/ip-asset-detail`, its `LglIpFamily` link to `ComProduct` (`SKU-ANODE-PRO`) automatically adds `US 12,104,882` to the Virtual Patent Marking schedule on `#/product-marking-licensing`, and automatically removes expired sibling patents on their exact `calculatedExpirationDate`.

### Journey 5: List-to-Detail Click-Through & Filter State Restoration
1. Trademark Counsel filters `#/trademarks-domains` by `Nice Class: "9"` and searches `"RAPIDER"`, displaying `#activeFilterTagsBar` chips `Nice Class: "9" ✕` and `Search: "RAPIDER" ✕`.
2. Counsel clicks `TM-US-0019` -> navigates to `#/ip-asset-detail?id=...` verifying the §8 specimen screenshot, then clicks `#btnGoBack`, restoring `#/trademarks-domains` with both filter chips intact.

---

## 6. Consolidated Feature Priorities & Work Packages

### `P0` Foundation (MVP Release — Mandatory)
- **WP-P0-1: Invention Disclosure Portal & Novelty Triage (`IPPM-001`, `IPPM-002`, `IPPM-026`):** `LglInventionDisclosure` intake, `100.00%` `Decimal128` contribution validation, novelty-bar urgency alerts, Patent Committee Home `WorkItem`s, and Startup vs. Enterprise UX toggle.
- **WP-P0-2: Patent/Trademark Portfolio & Statutory Prosecution Engine (`IPPM-005`, `IPPM-006`, `IPPM-009`, `IPPM-010`):** `LglIpFamily` & `LglIpAsset` hierarchy, `FinLegalEntity` assignee link, Nice classes, §8/§15 specimen tracking, and `LglIpProsecutionAction` shortened/final statutory bar deadlines.
- **WP-P0-3: Cross-Family IDS Duty-of-Candor Engine (`IPPM-007`):** `LglPriorArtReference` cross-family US `UNCITED_NEEDS_IDS` propagation and 90-day `37 CFR 1.97(b)` deadline generator.
- **WP-P0-4: Annuities, Dual-Control Pruning & Virtual Patent Marking (`IPPM-012`, `IPPM-013`, `IPPM-015`):** `LglIpRenewalAnnuity` schedule, mandatory dual-control `ABANDON_PRUNE` sign-off, `FinSupplierBill` renewal handoff, and `ComProduct`/`MfgProductRevision` Virtual Patent Marking.

### `P1` Scale & Global R&D Governance
- **WP-P1-1: Trade Secret Vault, FTO Privilege Wall & Chain of Title (`IPPM-003`, `IPPM-016`, `IPPM-022`):** Clean-room `TRADE_SECRET_VAULT` access logs, privileged `ftoOpinionFileId` ACL isolation from engineering search, and PTO assignment reel/frame verification.
- **WP-P1-2: PTO Sync, PCT Matrix, Multi-Year Forecasting & Inventor Awards (`IPPM-004`, `IPPM-008`, `IPPM-014`, `IPPM-017`, `IPPM-024`):** USPTO/EPO/WIPO status connector workflow, PCT/Unitary Patent cost matrix, 5-year `FinBudget` feed, `CrmContract` licensing links, and `LglInventorAward` -> `payroll` handoff.
- **WP-P1-3: Brand Gazette Watch & Opposition Management (`IPPM-011`):** `LglIpWatchDispute` triage board (`<rapider-kanban>`) for trademark watches, UDRP domains, and PTAB/EPO oppositions.

### `P2` Adjacent Analytics & Grounded IP AI
- **WP-P2-1: Grounded IP Intelligence AI Suite (`IPPM-018`, `IPPM-019`, `IPPM-020`, `IPPM-021`, `IPPM-023`, `IPPM-025`):** AI Patent Auto-Classifier, `projectChannelMessage` IP Portfolio Copilot (shielding unpublished IDFs, Trade Secrets, and FTO opinions), AI Office Action PDF & prior-art parser, AI Pruning ROI scorer, claim-to-product summarizer, and trademark watch similarity scorer.

---

## 7. Roles, Permissions & Field-Level Governance

| Role | Permitted Actions | Restricted / Field-Level Boundaries |
| :--- | :--- | :--- |
| **Chief IP Counsel / Patent Attorney (`lgl.ip.counsel`)** | Full management of `LglInventionDisclosure`, `LglIpFamily`, `LglIpAsset`, `LglIpProsecutionAction`, `LglPriorArtReference`, privileged FTO opinions, and legal sign-off on `LglIpRenewalAnnuity` pruning. | **Cannot** unilaterally execute `ABANDON_PRUNE` without Business Unit Owner co-approval (`businessOwnerApproverId != ipCounselApproverId`). |
| **IP Docketing Paralegal (`lgl.ip.paralegal`)** | Docket PTO office actions, stage IDS cross-citations, upload assignment deeds and §8 trademark specimens, prepare outside-counsel and annuity fee batches. | Cannot approve `ABANDON_PRUNE` patent abandonments or finalize Patent Committee filing rejections. |
| **R&D Inventor (`lgl.ip.inventor`)** | Submit new `LglInventionDisclosure`s, view status and comments on own submitted IDFs, view own `LglInventorAward` milestones, browse public/granted company patent portfolio. | **Strictly blocked** from viewing other teams' unpublished IDFs, `TRADE_SECRET_VAULT` files (unless named custodian), and **strictly blocked** from reading `ftoOpinionFileId` legal opinions (preserving privilege & preventing willful-infringement exposure). |
| **Patent Committee / R&D Business Owner (`lgl.ip.committee_reviewer`)** | Score assigned `LglInventionDisclosure`s; co-approve `PAY_RENEW` / `ABANDON_PRUNE` decisions for assigned `ComProduct` lines. | Scoped to assigned business unit / technology taxonomy; no write access to statutory PTO docket dates. |
| **Outside Prosecution Counsel (`lgl.ip.outside_counsel`)** | Scoped portal access to specifically assigned `LglIpAsset` dockets to upload filing receipts, office actions, and prior art. | Zero access to unassigned IP families, internal Trade Secret vaults, pruning ROI scores, or competitor watch strategies. |

---

## 8. Technical APIs, Guarded Commands, Events & `requiredWorkflows`

### Guarded Idempotent Commands
Every mutating command enforces `idempotencyKey`, `correlationId`, and `expectedVersion`:
- `lgl.ip.idf.triage` — Validates `sum(contributionPct) == 100.00`, records committee decision, spawns `LglIpFamily` / `LglIpAsset` (or `TRADE_SECRET_VAULT`), and triggers `IDF_APPROVED` `LglInventorAward`.
- `lgl.ip.priorArt.register` — Registers `LglPriorArtReference` and atomically flags all open US sibling `LglIpAsset`s as `UNCITED_NEEDS_IDS` with 90-day `IDS_CROSS_CITATION_FILING` actions.
- `lgl.ip.annuity.decide` — Enforces dual-control (`ipCounselApproverId` + `businessOwnerApproverId`) on `ABANDON_PRUNE` and emits consolidated `FinSupplierBill` requests on `PAY_RENEW`.
- `lgl.ip.asset.recordGrant` — Computes `calculatedExpirationDate` (20-year filing term + `ptaDays`), updates Virtual Patent Marking feed, and queues `PATENT_GRANTED` `LglInventorAward`s.

### Domain Events (Kafka)
- **Published:** `lgl.ip.idf.submitted`, `lgl.ip.noveltyBar.urgent`, `lgl.ip.asset.filed`, `lgl.ip.asset.granted`, `lgl.ip.ids.crossCitationFlagged`, `lgl.ip.annuity.paymentApproved` (to `accpayable`), `lgl.ip.asset.abandoned`, `lgl.ip.inventorAward.approved` (to `payroll`), `lgl.ip.virtualMarking.updated`.
- **Consumed:** `mfg.plm.revision.released`, `com.catalog.product.retired` (flags orphaned patents as `PRUNE_CANDIDATE`), `fin.ap.bill.paid`.

### `requiredWorkflows` in `app.manifest.json`
1. `lgl-ip-statutory-docket-escalator` (Daily evaluator emitting `90d/30d/14d/7d/48h` Home `WorkItem`s for non-extendable Provisional 12m, PCT 30m, Office Action 6m bars, IDS 90d windows, and *ArbnErfG* deadlines).
2. `lgl-ip-pto-bibliographic-sync` (Scheduled USPTO Open Data / EPO OPS / WIPO bibliographic status & PTA verifier via vault-injected API keys).
3. `lgl-ip-quarterly-annuity-pruning-campaign` (Groups upcoming 6-month `LglIpRenewalAnnuity` items, computes AI Pruning ROI scores, and routes dual-control review Home `WorkItem`s).

### Grounded Rapider AI Contract
The IP Portfolio Copilot (`projectChannelMessage`) enforces **Trade Secret Clean-Room & FTO Privilege Isolation**: engineering callers never retrieve `ftoOpinionFileId` content or unauthorized `TRADE_SECRET_VAULT` entries; every AI citation links exact `LglIpAsset.id` and `LglPriorArtReference.id` records; and AI never abandons an IP asset or closes a PTO statutory deadline without explicit human confirmation.

---

## 9. Security, Privacy, Compliance & Non-Functional Requirements

- **DTSA (`18 U.S.C. § 1836`) & EU Trade Secrets Directive Secrecy Evidence:** `TRADE_SECRET_VAULT` entries enforce strict named-custodian encryption, watermarked viewing, and immutable access logs proving statutory "reasonable measures to keep such information secret."
- **Attorney-Client Privilege & Willful Infringement Firewall:** `ftoOpinionFileId` and legal clearance memos are segmented behind `lgl.ip.counsel` ACLs so R&D engineers cannot inadvertently access adverse patent opinions.
- **Zero Hardcoded Secrets:** USPTO Patent Center/TSDR, EPO OPS, and WIPO API credentials reside strictly in `process.env` / platform secret vaults.
- **Life-of-Asset + Statutory Retention:** Prosecution wrappers, inventor assignment deeds, and IDS filing proofs are retained for the full 20-year patent term + 6-year post-expiration damages lookback (`35 U.S.C. § 286`).
- **Accessibility & Responsive UX:** WCAG 2.2 AA compliance, accessible tabular views alongside interactive Patent Family Trees, `#ffffff !important` contrast on primary/danger actions, and responsive `390px`/`768px`/`1440px` layouts across Light and Dark themes.

---

## 10. Deterministic Acceptance Criteria

1. **Sidebar Section Threshold:** `app.manifest.json` defines 3 visible sidebar sections (`Overview`: 3 items, `Prosecution & Brand`: 3 items, `Renewals & Value`: 3 items) with zero 1-item or 2-item headers; detail and drawer routes set `displayOnMenu: false`.
2. **SWR & Clean Query Compliance:** All 12 pages load initial records via `findSWR` / `countSWR` without manual `isDeleted` where clauses and defensively filter `item.isDeleted !== true` in memory.
3. **Inventor Contribution Split Invariant:** Submitting an `LglInventionDisclosure` where `sum(inventorsJson[].contributionPct) != 100.00` (`Decimal128`) fails deterministically with `422 INVALID_CONTRIBUTION_SPLIT`.
4. **Cross-Family IDS Propagation (`37 CFR 1.56`):** Registering a new `LglPriorArtReference` on an EPO family member automatically marks all open US sibling `LglIpAsset`s in that `LglIpFamily` as `UNCITED_NEEDS_IDS` and creates an `IDS_CROSS_CITATION_FILING` prosecution action.
5. **Dual-Control Abandonment Guardrail:** Attempting to finalize `ABANDON_PRUNE` on an `LglIpRenewalAnnuity` with only a single approver or where `ipCounselApproverId == businessOwnerApproverId` fails with `403 DUAL_APPROVAL_REQUIRED`.
6. **Virtual Patent Marking Accuracy:** The Virtual Patent Marking output for a `ComProduct` includes 100% of linked `GRANTED_REGISTERED` patents and deterministically excludes `FILED_PENDING`, `ABANDONED`, and `EXPIRED` assets.
7. **FTO Privilege & Trade Secret Isolation:** Querying `LglIpAsset` or `projectChannelMessage` as `lgl.ip.inventor` returns `403 PRIVILEGED_OPINION_RESTRICTED` on `ftoOpinionFileId` and hides unauthorized `TRADE_SECRET_VAULT` payloads.
8. **Unique Inventor Milestone Awards:** Approving `FIRST_UTILITY_FILING` twice for the same `(inventorEmployeeId, idfId)` is rejected idempotently without emitting duplicate `payroll` award events.
9. **Optimistic CRUD & Drawer Lifecycle:** Creating/updating/deleting disclosures, docket actions, or watch items updates tables and `<rapider-kanban>` immediately, clears SWR cache keys, resets submit buttons in `finally`, and auto-closes `#/ip-drawer`.
10. **Search, `#activeFilterTagsBar` & Clear All:** Filtering by asset category, jurisdiction, Nice class, or search query renders HTML-escaped chips in `#activeFilterTagsBar`; clicking `✕` or `[Clear all]` updates all views synchronously.
11. **Table Actions & Custom Elements:** Zero standalone "View" buttons in `Actions`, clickable primary identifiers, icon+text `Edit` and icon-only `Delete` buttons, `<rapider-kanban>` on IDFs/Brand Watch, `<rapider-phone-input>` on outside counsel contacts, `#ffffff !important` primary/danger button text, and zero `alert()`/`confirm()`/`prompt()` calls.
12. **Click-Through & Back State Restoration:** Clicking an IP asset number in `#/patent-families` or `#/trademarks-domains` navigates cleanly to `#/ip-asset-detail?id=...` without `<base href>` 404 hijacking, and `#btnGoBack` restores prior filter tags across Light and Dark themes.
