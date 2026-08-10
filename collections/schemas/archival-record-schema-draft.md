# Archival Record Schema Draft

## Purpose

This schema defines the minimum record structure for the digital reading room
MVP. It is intentionally implementation-neutral so it can back a JSON dataset,
spreadsheet workflow, or later database model.

## Record identity

| Field | Required | Description |
| --- | --- | --- |
| `id` | yes | Stable internal identifier for the reading room record. |
| `sourceInstitution` | yes | Owning or providing institution, such as memorial hall, NARA, or university archive. |
| `sourceRecordId` | no | Original call number, archival identifier, or source-system identifier. |
| `title` | yes | Primary display title for the record. |
| `originalTitle` | no | Original-language or source-supplied title. |

## Description and interpretation

| Field | Required | Description |
| --- | --- | --- |
| `summaryZh` | no | Chinese summary or normalized description for public display. |
| `descriptionZh` | no | Longer Chinese contextual description. |
| `originalText` | no | Original source description, title block, or text excerpt kept for reference. |
| `derivedContentNote` | no | Note explaining whether summary/description was AI-assisted, human-edited, or translated. |

## Date and format

| Field | Required | Description |
| --- | --- | --- |
| `dateDisplay` | no | Human-readable display date or date range. |
| `dateStart` | no | Normalized start date when known. |
| `dateEnd` | no | Normalized end date when known. |
| `recordType` | yes | High-level type such as photo, video, document, oral-history transcript, or scan. |
| `extent` | no | Duration, page count, or other extent statement. |
| `language` | no | Language or languages represented in the source material. |

## Access, rights, and workflow

| Field | Required | Description |
| --- | --- | --- |
| `accessStatus` | yes | Public, internal only, restricted, or similar approved vocabulary. |
| `reviewStatus` | yes | Editorial/rights workflow status such as approved, pending_rights_review, or pending_editorial_review. |
| `rightsNote` | no | Rights or usage note that explains restrictions or approval basis. |
| `isPublic` | yes | Boolean publication flag derived from approved access/review status. |

## Discovery and navigation

| Field | Required | Description |
| --- | --- | --- |
| `themes` | no | Topic labels such as Flying Tigers, Hump Route, immigration, or exhibition history. |
| `tags` | no | Free or controlled tags for search and browse support. |
| `people` | no | Named people associated with the record. |
| `places` | no | Named places associated with the record. |

## Asset and display support

| Field | Required | Description |
| --- | --- | --- |
| `thumbnailUrl` | no | Thumbnail or poster image for list/detail views. |
| `assetUrl` | no | Primary asset or landing-page URL. |
| `assetFormat` | no | File or media format such as PDF, JPG, MP4, or external catalog link. |
| `attributes` | no | Displayable properties such as silent, black-and-white, borrowable, transcript available. |

## Provenance and notes

| Field | Required | Description |
| --- | --- | --- |
| `provenanceNote` | no | Context for how this record entered the reading room dataset. |
| `editorialNote` | no | Internal note for record quality or follow-up work. |
| `lastReviewedAt` | no | Most recent review date. |
| `lastReviewedBy` | no | Person responsible for latest metadata/review pass. |

## Minimum publishable record

A record is minimally publishable when it has:

- `id`
- `sourceInstitution`
- `title`
- `recordType`
- `accessStatus`
- `reviewStatus`
- `isPublic`

And when:

- `isPublic` is true
- rights status is known
- AI-derived text, if present, is clearly labeled

## Notes

- This draft intentionally separates `accessStatus`, `reviewStatus`, and
  `isPublic` so editorial workflow does not get confused with public display.
- The original intern document's field template is preserved here in expanded
  form rather than copied literally, because the original version was not enough
  for governance and operational use.
