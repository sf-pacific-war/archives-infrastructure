# Flying Tigers and CBI Archive Beta

Product requirements and project delivery plan

Version 4  |  First beta  |  11 October 2026

## Part 1 Product requirements and design

Build a public website where Flying Tigers 85th anniversary attendees can explore archival evidence about Flying Tigers and China–Burma–India history, view the museum’s collection, and share artifact photos. Invited, signed-in contributors can publish and edit their own community posts. The beta supports a morning launch and an afternoon panel, with continued access after the event.

Most decisions and background were collected from the meeting Jessie &lt;&gt; Deb on Oct 11.

### Product goals

- Make historical evidence easy to find, view, inspect, and cite.

- Let invited artifact owners contribute photos and context, then update their own published records.

- Show the source and stewardship of every record through three distinct collection tiers.

### Users and core use cases

| User | Use case and expected result |
| --- | --- |
| Public visitor | Search a person, place, unit, or topic; open a record and inspect its source, image, citation, and access conditions. |
| Signed-in user | Give or remove a thumbs-up and comment on published Tier 2 and 3 records; manage own comments. |
| Invited contributor | Redeem an invite, upload photos, publish a Tier 3 post, and edit or unpublish it later. |
| Museum staff | Create, edit, and publish Tier 2 museum records with provenance and public display permissions. |
| Panelist or event volunteer | Open prepared examples and help visitors browse or contribute from a phone. |

### Beta scope

Include bilingual discovery, record viewing, invited Tier 3 publishing and editing, museum publishing, thumbs-up likes and comments on Tiers 2 and 3, and moderation. Tier 2 content is optional for launch, subject to collection availability and team capacity. Design for mobile use and a peak of 500 simultaneous browsers.

Defer file downloads, video, generated historical answers, broad archive crawling, full OCR, artifact authentication, and a full museum collection management system.

### Success measures

Measure visits, source openings by tier, unsuccessful searches, invite activations, published posts, edits, likes, and comments. Review results within one week after the event.

### Collection model and discovery requirements

A collection tier identifies provenance and stewardship. Historical confidence, editorial review status, and reuse rights are separate attributes. Every result, detail page, and shared link must retain its tier and source attribution.

| Collection tier | Content and attribution | Source and publication control |
| --- | --- | --- |
| Tier 1<br>Institutional archives | External records held by archives such as NARA. Display source-supplied metadata, catalog ID, source link, and rights. Tier 1 is read-only, with no likes or comments. | The external institution owns and publishes the record. No local role, including administrators, can edit or publish Tier 1 records. |
| Tier 2<br>Museum collection | The museum’s own documented holdings and authorized materials. Show item ID, credit, provenance, and custody or ownership status. | Authorized museum staff create, edit, and publish records after museum review. |
| Tier 3<br>Community contributions | Free artifact-photo uploads and accounts from invited users. Retain contributor credit, attribution, and public display permission. | Invited owners publish and edit their own posts directly, without staff preapproval. |

#### Search and browsing

Offer a search box, prepared topics, and a separate entry for each tier. All collections searches group results by tier and show counts; rank by relevance within each group. Support English and Chinese interface labels and reviewed search aliases. Add filters for institution, material type, date, language, and access where metadata supports them.

Display Tier 1 titles and descriptions as supplied by the external institution. Interface translations and search aliases must not alter archival metadata. Show useful empty-result guidance and unavailable-source status. Link related records while preserving their separate provenance.

#### Evidence and access

Read-only institutional references must identify the holding institution, collection and item IDs, title, creator when known, date and its meaning, stable source URL, retrieval date, language, and rights. Keep collection-level descriptions distinct from item-level facts. Museum records use an existing item ID or a clearly labeled temporary digital ID.

Use the access labels View here, View at institution, Catalog only, and Access unconfirmed. Provide a permitted preview or a direct source link and a copyable citation. Preserve source attribution, unknown dates, and conflicting accounts without rewriting external records.

#### Tier integrity

The system assigns a community upload to Tier 3. Publication or later review does not promote it into another tier. If the museum formally incorporates an object, staff may create a linked Tier 2 record with supporting documentation and preserved contribution history. Community claims remain contributor-supplied unless separately reviewed.

### Page design and contributor experience

Use a mobile-first layout with a language switch, search, and Contribute entry. Browsing is public. Sign-in enables likes and comments on Tiers 2 and 3; an invite additionally enables Tier 3 photo contributions.

| Screen | Required elements |
| --- | --- |
| Home and search | Prepared topics, three tier entries, query and filters, grouped results, source and tier labels. |
| Record detail | Title, photos or source link, description, attribution, dates, citation, rights, and related records. Tier 2 and 3 add thumbs-up likes, comments, and reporting; Tier 1 has no social controls. |
| My contributions | Own drafts and published posts, status, Updated date, and Edit, Publish, or Unpublish controls. |
| Post editor | Photo upload and preview, context fields, public credit, display consent, draft save, and publication controls. |
| Staff workspace | Museum editing, invites, and reports on community posts and Tier 2/3 comments, with moderation controls. Tier 1 has no editing, publishing, likes, or comments. |

#### Publish and edit a community post

1. Sign in with a verified account and redeem an organizer-issued invite code. Explain that published posts are visible to anyone on the internet.

2. Add 1–5 photos, a title, a short description, the owner’s connection to the artifact, and the basis for its attribution. Dates, places, names, and units may remain unknown.

3. Choose a public credit name or Anonymous. Confirm permission to upload and display the photos publicly. Keep the account email private.

4. Save a private draft or choose Publish. After automatic file validation and processing succeed, the post appears publicly in Tier 3 without staff approval. On failure, preserve the draft and explain how to retry.

5. From My contributions, edit text, photos, or public credit. Save a private revision or choose Save and publish. The prior public version remains until the new one is ready; update the page, gallery, and search together.

#### Publication states

Drafts are private. Published posts show the current public version. Unpublished by owner posts are private and may be published again. Hidden by staff posts remain private until a moderator lifts the restriction; owner edits cannot bypass it.

#### Photo handling and owner control

Proposed limits: five images per post and 10 MB per image. Support JPEG and PNG plus tested HEIC conversion. Keep originals private, create smaller viewing copies, and remove location metadata from public images. Retain private revision history for the owner and staff; review badges apply only to the reviewed version.

Unpublishing or removal must clear public pages, search results, and cached delivery. Present contribution terms covering credit, public display, retention, and withdrawal.

### Likes comments and participation

Use thumbs-up likes and comments to let visitors respond to museum and community records. An active signed-in account is sufficient; invite codes apply only to Tier 3 artifact contributions. Published comments and total like counts are visible to all visitors.

| Collection tier | Interaction experience |
| --- | --- |
| Tier 1 | Viewing and source access only. Show no like button, like count, comment form, or comment list. Reject like and comment requests for Tier 1. |
| Tier 2 | Published museum records support thumbs-up likes and comments when this optional tier is included. |
| Tier 3 | Published community posts support thumbs-up likes and comments. Posting a comment does not require an upload invitation. |

#### Thumbs-up likes

Allow one thumbs-up per account per record. The same control removes that user’s like, and repeated requests do not increase the count. Show the total and the signed-in user’s selected state. A signed-out visitor choosing Like is prompted to sign in.

#### Comments

Provide a plain-text comment form and a chronological comment list. Show the author’s public display name and posting time; keep account emails private. Signed-in authors can publish, edit, and delete their own comments. Comments appear after validation without routine staff approval. Record owners cannot edit other people’s comments.

#### Moderation and visibility

Visitors can report a comment. Jessie moderates comments on Tiers 2 and 3 and can hide or restore them with a recorded reason. Authors cannot restore moderator-hidden comments by editing them. Apply basic length and posting-rate limits to control spam.

Only published, visible records accept interactions. When a record is unpublished or hidden, its comments and like counts also become private and new interactions stop. Suspended accounts cannot change likes or comments. Keep comments separate from the record’s historical description, attribution, and review status; a like is not verification of a historical claim.

### Invitations and publishing permissions

Tier 3 uploads and record publishing require an invitation. Redeeming a code grants the contributor role to the signed-in account. Likes and comments on published Tier 2 and 3 records require only an active signed-in account. Check roles and ownership on the server.

| Role | Allowed actions | Scope |
| --- | --- | --- |
| Public visitor | Browse records, images, visible comments, and like counts | Published records in all tiers |
| Signed-in user | Like/unlike; comment; edit or delete own comments | Published Tier 2 and 3 records; no invite needed |
| Invited contributor | Upload, publish, edit, and unpublish own posts | Own Tier 3 records only |
| Museum editor | Create, edit, and publish museum records | Authorized Tier 2 records |
| Organizer or administrator | Issue or revoke invites; suspend contributors | Access administration |
| Community moderator | Review reports; hide or restore posts and comments | Tier 3 posts and Tier 2/3 comments; reasons logged |

#### Invite lifecycle

Allowed beta invite codes are flyingtigers85, sfpacificwarmuseum, and sf2026. Organizers distribute these codes to selected participants; redemption limits and expiry are configured before launch. Validate redemption against this list on the server, enforce limits atomically, record each redeeming account, limit failed attempts, and keep codes out of public pages and logs.

Codes activate Tier 3 contributor access and do not replace sign-in. Expiry or revocation stops future redemptions. Suspending an account blocks uploads, publication, edits, and like/comment changes. Existing public content remains visible unless staff hide it.

#### Ownership rules

Set the owner from the signed-in account and assign Tier 3 on the server. Contributors cannot edit another user’s content, change owner IDs or tiers, create institutional or museum records, or grant themselves staff roles. Invitation codes never grant staff access. Tier 1 records are external and read-only for every local role, including staff and administrators.

#### Staff publishing and moderation

Museum editors can create or import simple records, attach images, record provenance and rights, and publish or unpublish them. Private donor details, valuations, and storage locations stay outside public records. Tier 1 descriptions and archival content remain under the external institution’s control; this site provides discovery, source links, and permitted read-only viewing.

Reports on Tier 3 posts and comments on Tiers 2 and 3 go to the staff queue. Moderators may hide content with a recorded reason and notify its author; restoration requires a moderator. Posts and comments publish without routine staff preapproval.

### System design and acceptance criteria

#### Logical design

Display external Tier 1 references alongside published Tier 2 and 3 records. Keep likes and comments separate from record metadata and revisions. Enforce sign-in, tier, ownership, and publication state for interactions; require invitations for Tier 3 uploads and publishing. Uploaded originals stay private; publish viewing copies.

Index Tier 1 references only where source terms permit storage; use transient results or source links elsewhere. Refresh permitted copies from authoritative sources and keep them read-only. Update Tier 2/3 search after changes. Keep drafts, revisions, invite codes, account details, and originals private. Likes and comments cannot alter record metadata.

#### Quality requirements

Provide readable type, large touch targets, keyboard navigation, descriptive image text, and English/Chinese labels. Validate real file contents before publication. Use HTTPS, server-side permissions, multifactor authentication for administrators, upload limits, and an audit trail for access and publication changes.

| Requirement | Beta acceptance condition |
| --- | --- |
| Discovery and evidence | All public records show the correct tier, source, rights, and review status. Tier grouping and filters work; featured records have a tested viewing route. No download controls appear in any tier. |
| External Tier 1 | All roles have read-only access. Tier 1 has no record editing, publishing, likes, or comments through the interface or API. Metadata refresh preserves the external source. |
| Direct contribution | On iPhone and Android, an invited owner can upload, publish, edit a published post, and unpublish without human preapproval. Public pages and search reflect changes. |
| Access isolation | Accounts cannot modify others’ posts, photos, or comments. Uninvited accounts cannot upload or publish Tier 3 records but may like/comment when signed in. Suspended accounts cannot write. Users cannot change owner, tier, or role. |
| Invite and removal controls | Only listed, active invite codes work. Unlisted, expired, revoked, or exhausted codes fail. Concurrent redemption cannot exceed the limit. Owners cannot republish staff-hidden posts. |
| Likes and comments | Signed-in users without invites can like and comment on Tier 2/3; signed-out users cannot. One like per account and record; unlike works. Hidden records and comments are not publicly accessible. |
| Staff workflows | When Tier 2 is included, authorized museum editors can edit, publish, and unpublish its records. Community invitations do not grant these permissions. Tier 2 availability does not block launch. |
| Performance | Test 500 browsing sessions for 30 minutes, each taking one page, search, or record action every 15 seconds. Include 25 uploads of one 5 MB image within five minutes. Target under 1% unexpected errors and p95 search display under 2 seconds. |

The traffic profile is a proposed launch test, not measured capacity. Test phone loading on venue-like connectivity and report external archive latency separately. Record evidence for every acceptance check before launch.

## Part 2 Project overview

The beta will support attendees of the Flying Tigers 85th anniversary events, with continued access afterward. This section explains the event experience, responsibilities, and delivery risks.

### Responsibilities

| Owner | Responsibility |
| --- | --- |
| Jessie | Proposes the budget for Deb’s review. Owns project delivery, website design and implementation, hosting, launch, invitations, content publishing, moderation, and ongoing support. |
| Deb | Provides requirements, reviews the proposed budget, and provides legal and brand permissions. Gives design critique, reviews, and input. Supplies the optional Tier 2 museum collection, attribution, provenance, and display permission information as availability and capacity allow. |

### Event experience

- Explore Flying Tigers and China–Burma–India history through Tier 1 archival references, Tier 3 community contributions, and Tier 2 museum records when available.

- Search people, places, units, and topics; view available images and follow links to original archival sources.

- Understand where each item comes from through clear collection tiers, citations, provenance, and review status.

- Sign in to give thumbs-up likes and comment on published Tier 2 and Tier 3 records.

- Use an invite code to upload, publish, and later edit their own artifact photos and historical context.

- Return after the event to continue exploring the collections and contributing to the community.

### Delivery risks and responses

Tiers 1 and 3 depend less on museum material preparation and review capacity. Tier 2 is optional for the beta and can be added later, depending on collection availability and Jessie’s and Deb’s time and capacity. Launch can proceed with Tiers 1 and 3. Tier 1 still depends on external archive availability, and Tier 3 requires working upload, publishing, and access controls.

### Tier 1 proposed archival sources

This section covers all nine proposed institutions and aggregators in the discovery plans. NARA has two distinct access routes. The tables describe potential beta access, not completed integrations. Policies were checked on 11 October 2026; official references and application steps follow.

A record preview means a title, description, source, and link. An image preview additionally needs a usable image and permission to display it. No blanket permission to embed archive websites is assumed. All Tier 1 material remains read-only, without likes, comments, or download controls.

| Source | Preview within our website | Connection needed |
| --- | --- | --- |
| [1] Library of Congress<br>LoC | Metadata: yes. Images or documents: conditional on online availability and item rights. | Public JSON API; no key. Permitted metadata can support our index. |
| [2] NARA<br>Public dataset | Metadata: yes, after import. Digital-object links may support permitted image previews. | Public data files; no API key or AWS account. Build our own search index. |
| [2] NARA<br>Catalog API v2 | Live metadata: conditional on access approval. Images remain subject to item rights. | Dedicated key. Live results only; current API terms prohibit storage or caching. |
| [3] Digital Public Library of America<br>DPLA | Metadata: yes. Preview images and full objects depend on the holding institution’s rights. | Dedicated API key. Metadata indexing is supported; preserve provider links. |
| [4] Europeana | Metadata: yes. Thumbnails and images depend on each item’s rights statement. | API key required. Use a project key for the public beta; personal keys are for testing. |
| [5] UK National Archives<br>Discovery | Live descriptions: conditional on approval. Full document previews need separate clearance. | Approved server IP for API access. No caching or storage; source-link fallback. |
| [6] Imperial War Museums<br>IWM | Source links initially. Selected low-resolution previews only if the use and item qualify. | No usable public API or signup confirmed. Seek an approved feed or partner route. |
| [7] National Diet Library<br>NDL Search | Bibliographic metadata: yes for permitted providers. Images need separate access and rights checks. | Public search/harvest APIs; tested subset needs no key. Permissions vary by provider and use. |
| [8] Japan Center for Asian Historical Records<br>JACAR | Source links initially. Selected scan previews may be possible under holding-institution rules. | No usable public API confirmed for this project. Obtain formal machine-access details first. |
| [9] Taiwan National Archives Administration | Case-title CSV: metadata only. A+, NEAR, and ACROSS remain source portals; image preview is unconfirmed. | CSV needs no key. A cooperation API would require agency agreement; no self-service signup confirmed. |

The preview assessment includes both technical access and reuse conditions. A public source page or successful API test does not establish permission to republish every image. Where a preview is unavailable, show the source link and access conditions.

### Tier 1 free access and paid use

These are archive access and reuse categories, separate from our three collection tiers. No standard paid API subscription was identified in the reviewed documentation. Approval, higher quotas, and image licensing are different requirements; an unspecified fee is not assumed to be zero. References [1]–[9] appear in the following access instructions.

| Source | Available without an access fee | Paid use or additional approval |
| --- | --- | --- |
| [1] LoC | Public API without a key; reusable materials subject to item rights. Current JSON limit: 20 requests/minute. | No paid API upgrade published. Reproduction services or third-party image permissions may cost extra. |
| [2] NARA dataset and API | Public dataset access. API default: 10,000 queries/month per key. Public-domain materials may be reused. | 150,000 queries/month may be requested with justification; this is an approval category, not an advertised paid plan. Copies and non-public-domain rights are separate. |
| [3] DPLA | CC0 metadata can be reused, including commercially. API access requires a key; item media rights differ. | No paid API plan published. Provider image/copy fees may apply; selling or renting the DPLA service itself requires written consent. |
| [4] Europeana | Free API keys; CC0 metadata. Media use follows each rights statement. | Project approval is required for production, not a paid upgrade. Separate rights-holder licensing may cost money. |
| [5] UK Discovery | Public discovery and approved API access; no API subscription charge published. Guidelines: 3,000 calls/day and 1/second. | Digital copies or reproduction can incur charges. No paid capacity upgrade published; storage would need separate written permission. |
| [6] IWM | Public browsing; eligible low-resolution material for accepted noncommercial uses with credit. | High-resolution, commercial, or uncovered uses need licensing or a quote. Confirm that our event/museum website qualifies; no verified API price tiers. |
| [7] NDL Search | Permitted metadata access; the tested NDL Catalog subset is CC BY with attribution. No paid API plan published. | Other providers or for-profit uses may require an application. Image rights and copying services are separate; approval is not a paid API tier. |
| [8] JACAR | Public search/viewing. Some holding institutions permit secondary image use with attribution. | Other holdings or photographs may require permission; high-quality copies and any fees depend on the holder. No verified API price tiers. |
| [9] Taiwan archives | Case-title CSV is explicitly free under the Government Open Data License v1.0. Public catalog access is separate from copies. | Copies and permitted image reuse may involve fees or approval. Cooperation API pricing, quotas, and eligibility remain unconfirmed. |

Hosting, integration, and licensed images remain project costs. Jessie proposes the budget and obtains technical access approvals and quotes; Deb reviews the budget and provides legal and brand permissions.

### Tier 1 access applications and references

Jessie owns technical access applications and integration; Deb provides requirements and legal and brand permissions. Request read-only access for public historical discovery, describe the event audience and expected traffic, and distinguish metadata display from image reuse.

#### 1 Library of Congress

No registration is needed for the public JSON API. Use documented search and record endpoints, respect rate limits, and check the rights statement for each proposed image. Batch permitted metadata updates rather than making an archive request for every visitor action.

[LoC API and access](https://www.loc.gov/apis/json-and-yaml/) · [Rate limits](https://www.loc.gov/apis/json-and-yaml/working-within-limits/) · [Image rights](https://www.loc.gov/legal/security-copyright-and-privacy/understanding-copyright/) · [Copying services](https://www.loc.gov/research-centers/services/general-scanning-and-copying/)

#### 2 United States National Archives

Dataset: use anonymous public access and select relevant record groups for a permitted local index. Catalog API: email Catalog_API@nara.gov with the requester’s name and email; obtain a read-only key and request a larger quota with a use-case justification if needed. Keep API responses transient and retain required attribution; the dataset is a separate route.

[NARA public dataset](https://www.archives.gov/developer/national-archives-catalog-dataset) · [API terms and quotas](https://www.archives.gov/research/catalog/help/api) · [Key request instructions](https://github.com/usnationalarchives/Catalog-API/blob/master/README.md) · [Image permissions](https://www.archives.gov/research/still-pictures/permissions)

#### 3 Digital Public Library of America

Use the API policy page’s documented POST request with our email address to request a key. DPLA sends the key by email. Keep it on our server, validate a small query, and retain original-provider links. Metadata reuse does not clear the associated images.

[DPLA key request and policy](https://pro.dp.la/developers/policies) · [Metadata policy](https://pro.dp.la/hubs/metadata-application-profile) · [Terms of use](https://dp.la/about/terms-conditions)

#### 4 Europeana

Create and confirm a Europeana account, then manage API keys from the profile. A personal key supports development. Submit the Project API key form for the public beta, describing purpose and expected traffic, and wait for review. Confirm the project’s limits and each media rights statement. Stop using affected metadata or thumbnails when Europeana requests removal.

[Europeana key application](https://www.europeana.eu/en/how-to-register-for-and-manage-an-api-key) · [Free API access](https://api.europeana.eu/en) · [Data and media terms](https://www.europeana.eu/en/rights/terms-of-use)

#### 5 UK National Archives Discovery

Email webmaster@nationalarchives.gov.uk with the production server’s outgoing IP address and intended use; wait for approval. Keep API results only for the current request. Seek explicit written permission for any stored index or cache; otherwise retain live display or source links.

[Discovery access and terms](https://www.nationalarchives.gov.uk/terms-and-conditions/discovery-for-developers-about-the-application-programming-interface-api/) · [Copies and ordering](https://www.nationalarchives.gov.uk/about/visit-us/researching-here/how-to-order-view-and-copy-documents/) · [Digital-copy use](https://discovery.nationalarchives.gov.uk/basket)

#### 6 Imperial War Museums

Ask IWM whether it can authorize a collection API or data feed; no self-service procedure is confirmed. For selected images, send catalogue numbers and the website’s intended use to imagesales@iwm.org.uk. Confirm eligibility for free noncommercial use or obtain a quote; keep source links until cleared.

[IWM copyright and reuse](https://www.iwm.org.uk/corporate/policies/copyright) · [Accepted noncommercial uses](https://www.iwm.org.uk/sites/default/files/files/2020-03/Accepted%20Non-Commercial%20Usages-2020.pdf) · [Licensing enquiries](https://www.iwm.org.uk/commercial/collections-sales-licensing)

### Tier 1 access in Japan and Taiwan

#### 7 National Diet Library Search

Begin with the tested NDL Catalog metadata subset, identified as iss-ndl-opac, under its CC BY terms. Review the provider list before adding databases. Submit the linked NDL Search API application when the provider or commercial use requires it; report ongoing use through the same form. Commercial thumbnail use also requires an application. Credit NDL Search and the supplying institution; treat image permission separately.

[NDL API rules and application form](https://ndlsearch.ndl.go.jp/en/help/api/) · [Provider permissions](https://ndlsearch.ndl.go.jp/en/help/api/provider)

#### 8 Japan Center for Asian Historical Records

Keep JACAR source links while Jessie asks jacar_enquire@archives.go.jp for a documented machine-access route, permitted fields, and reuse terms. There is no confirmed public key application for this project. For image previews, identify the holding institution and reference code: National Archives of Japan and Diplomatic Archives images generally permit secondary use with credit; National Institute for Defense Studies and other holdings may need permission. Photographs can have additional copyright holders.

[JACAR website terms](https://www.jacar.go.jp/english/termsofuse.html) · [Document image rules](https://www.jacar.archives.go.jp/aj/www/doc/en) · [Image-use FAQ](https://www.jacar.archives.go.jp/aj/www/faq/en/) · [Official contact](https://www.jacar.go.jp/english//about/documentstable/JACARLeaflet_en.pdf)

#### 9 Taiwan National Archives Administration

Use the free National Archives Case-title List CSV through dataset 95315; no key or registration is needed. Preserve source and license attribution. The file provides case-level titles and reference numbers, not scans or full text. Its data-production date is not the historical date of the records.

A+ serves national archive discovery and access applications; NEAR lists records held by individual agencies; ACROSS is a cross-institution discovery portal. These are separate from a third-party API. Cooperation APIs have existed, but project eligibility, authentication, quotas, fees, and public image rights are unconfirmed. Contact the agency through its official service channel with our proposed use and request formal documentation and permission before integration.

[Case-title dataset and free access](https://data.gov.tw/dataset/95315) · [Open-data license](https://data.gov.tw/licenses) · [Cooperation examples](https://www.archives.gov.tw/tw/arctw/59.html)

[A+ and service contact](https://aa.archives.gov.tw/) · [NEAR](https://near.archives.gov.tw/) · [ACROSS](https://across.archives.gov.tw/) · [Agency application and fees](https://www.archives.gov.tw/tw/arctw/109.html)

#### What is ready today

The discovery plans record small successful requests for LoC, the NDL Catalog subset, one NARA dataset shard, and Europeana with a development key. DPLA, NARA Catalog API, and UK Discovery still need credentials or access approval and live verification. JACAR and IWM remain portal-only. Taiwan’s CSV has only a limited-read check; synchronization and website integration are still pending.

These checks do not prove a production preview is ready. Jessie verifies record relevance, viewing routes, and hosted behavior and applies the legal and brand permissions Deb provides. Source-specific rights still govern each preview. Tier 1 source outages or unavailable images should leave a clear source-link fallback.
