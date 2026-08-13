# 现有开源档案与数字馆藏系统学习栈

## 目的

这份研究笔记整理一组与档案管理、数字馆藏、数字阅读室、检索和长期保存相关的开源系统与开放标准。重点不是马上选择一个“大而全”的企业级平台，而是明确哪些工具最值得在本项目里 hands-on 跑起来，用一个小型 prototype 把概念和实现同时学清楚。

对 SF Pacific War Archives Infrastructure Project 来说，第一阶段最有价值的不是完整 institutional repository，而是一个 20-100 件档案对象规模的小型 Digital Reading Room。这个 prototype 应该让团队清楚看到：

- archival hierarchy 由谁管理
- public collection site 由谁发布
- canonical metadata 放在哪里
- search index 如何生成
- image / A/V object 如何交付
- preservation repository 以后应该插在哪一层

## 快速对照

| Tool / Standard | 开源状态 | 主要负责什么 | 是否适合 hands-on 学 |
| --- | --- | --- | --- |
| [ArchivesSpace](https://archivesspace.org/) | 开源 | Archival management: accessions, resources, archival objects, agents, subjects, digital object descriptions, finding aids | 非常适合，第一优先级 |
| [Omeka S](https://omeka.org/s/) | 开源 | Digital collections, public sites, exhibitions, linked open data, items/media/sites | 非常适合，最好上手 |
| [Fedora Repository](https://fedorarepository.org/) | 开源 | Repository backend: digital objects, metadata, relationships, persistence, preservation-oriented storage | 适合第二阶段 |
| [Islandora](https://islandora.github.io/documentation/) | 开源 | 完整 DAMS / repository ecosystem，围绕 Drupal、可选 Fedora、microservices、IIIF、linked data、search | 适合理解 institutional architecture |
| [DSpace](https://dspace.org/) | 开源 | Institutional repository，常用于论文、datasets、theses、大学/研究机构 repository | 可学，但不是本项目第一核心 |
| [Samvera / Hyrax / Hyku](https://samvera.org/) | 开源社区生态 | Highly customizable repository framework / application，适合有工程团队的机构 | 可学，engineering 较重 |
| [OpenSearch](https://opensearch.org/about/) | 开源 | Full-text search, faceted search, analytics, vector search, hybrid retrieval | 非常适合 |
| [Elasticsearch](https://www.elastic.co/pricing/faq/licensing/) | 有开源选项，但 licensing / release model 更复杂 | Search, vector search, hybrid retrieval, analytics | 学概念可以；纯开源 prototype 更建议 OpenSearch |
| [IIIF](https://iiif.io/) | 开放标准，有多个开源 implementation | Image / A/V delivery, manifests, interoperability across repositories and viewers | 必学 |
| [Mirador](https://projectmirador.org/) | 开源 | IIIF viewer，支持 image comparison、metadata display、workspace、annotation support | 很适合直接跑起来 |
| [OpenSeadragon](https://openseadragon.github.io/) | 开源 | High-resolution zoomable image viewer，理解 tiled image / deep zoom 很有用 | 很适合 |
| [OCFL](https://ocfl.io/) | 开放规范，有 implementations | Preservation file layout, object versioning, repository rebuildability, storage transparency | 适合学习 preservation architecture |
| [PostgreSQL](https://www.postgresql.org/about/) | 开源 | Canonical metadata / application database / workflow state / authority tables | 非常适合 |

## 推荐学习栈

第一阶段建议把系统控制在可以本地运行和理解的范围内：

```text
Researcher
    |
    v
Omeka S
public collection site
    |
    +--------------------+
    |                    |
    v                    v
Mirador              OpenSearch
IIIF viewer          BM25 / facets / hybrid retrieval
    |                    |
    +---------+----------+
              |
              v
        PostgreSQL
        canonical metadata
              |
    +---------+----------+
    |                    |
    v                    v
ArchivesSpace        File Store
archival hierarchy   TIFF / PDF / audio / video / transcripts
```

这个 learning stack 第一阶段故意不放 Fedora。Fedora 很重要，但它应该在团队已经理解 metadata、hierarchy、public presentation、search 各自职责之后再加入。否则一开始就搭完整 DAMS / repository stack，学习成本会变高，而且容易把系统边界看混。

## 每一层真正教你什么

### ArchivesSpace: 学 archival management

ArchivesSpace 最适合作为第一优先级，因为它把档案学里的概念直接变成了软件实体和 API entity。

需要重点学习：

- accession
- resource
- archival object
- agent
- subject
- location
- digital object
- finding aid

ArchivesSpace 管的是 archival intellectual structure。例如：

```text
Collection
  -> Series
      -> File
          -> Item
```

这个层级和 public website 里的 item display model 不是一回事。对本项目来说，ArchivesSpace 更像 staff-side system of record，用来管理 arrangement、description、authority control、archival context。

最值得 reverse-engineering 的问题：

- 为什么 `Resource` 是一个 entity？
- 为什么 `Agent` 不是简单的 `creator: string`？
- 为什么 `Subject` 是 reusable record？
- 为什么 `Archival Object` 有 parent-child hierarchy？
- 为什么 `Digital Object` 和 `Archival Object` 要分开？

这些问题会把学习从“会用一个软件”推进到 information architecture reverse engineering。

### Omeka S: 学 digital collections + metadata + publishing

Omeka S 是最适合快速上手 public digital collection 的系统。它能很直观地展示：

```text
metadata model -> collection objects -> public presentation
```

需要重点学习：

- vocabulary
- resource template
- item set
- item
- media
- site

Omeka S 的 public-facing collection model 更像：

```text
Item Set
  -> Item
      -> Media
```

这很适合展览页、专题 browse、public collection website 和轻量数字展示。它不替代 ArchivesSpace 的 archival hierarchy，而是把已经审核、适合公开的记录转成面向公众和研究者的 collection/publishing model。

对 Digital Reading Room 来说，Omeka S 特别适合用来理解：

- Dublin Core / linked data vocabularies 如何塑造 item description
- resource template 如何把 metadata rule 变成 editor-facing form
- item set 如何支持 public grouping
- media attachment 和 archival description 的边界
- 一个 installation 如何管理多个 public site

### OpenSearch: 学 archival retrieval

OpenSearch 是把 archival science 接到 data / ML / retrieval 技术上的关键层。可以先把 ArchivesSpace / Omeka S 的 records export 出来，再设计自己的 search document。

一个 prototype search document 可以是：

```json
{
  "id": "sfwar-0001",
  "title": "Oral history interview with ...",
  "collection": "SF Pacific War Archives",
  "source_institution": "Memorial Hall",
  "agents": ["..."],
  "subjects": ["..."],
  "places": ["..."],
  "date_start": "1942-01-01",
  "date_end": "1945-12-31",
  "record_type": "oral_history",
  "access_status": "public",
  "review_status": "approved",
  "ocr_text": "...",
  "summary_zh": "..."
}
```

建议按顺序实现：

- BM25 keyword search
- exact phrase search
- facets by collection / source institution / person / place / topic / format / access status
- date-range filtering
- authority expansion，例如 alternate names、related places
- vector search over OCR / transcript / description
- hybrid retrieval，把 lexical ranking 和 vector ranking 结合起来

这一层会把项目已有的 schema、metadata governance、AI-derived text labeling 和 public/private review status 真正接到可运行的检索系统上。

### IIIF / Mirador / OpenSeadragon: 学 image 与 A/V delivery

IIIF 不是单纯的图片 viewer。它是一个 interoperability layer，让 image、A/V object、metadata、annotation、page/canvas structure 能跨 repository 和 viewer 使用。

当项目需要这些能力时，就应该学习 IIIF：

- stable image delivery
- deep zoom
- page / canvas sequencing
- manuscript、album、scrapbook navigation
- viewer interoperability
- citation-friendly object access
- future annotation workflow

Mirador 是研究型 Digital Reading Room 很合适的默认 viewer，因为它支持比较、metadata display、workspace、annotation support 和 IIIF Presentation API resources。

OpenSeadragon 则适合理解更底层的 high-resolution tiled image viewer：tiles 怎么加载、zoom/pan 怎么工作、viewer 如何嵌入页面，以及 IIIF Image API 和 viewer 之间的关系。

### Fedora / OCFL: 学 preservation-oriented repository layer

Fedora 更适合放在第二阶段。它的核心职责不是 public website，而是 repository backend：保存、管理、长期保全 digital content、metadata 和 object relationships。

Fedora 值得加入的时机：

- 需要 repository API 管 digital objects
- 需要 semantic relationships between objects
- 需要 preservation-oriented persistence
- 需要 OCFL-backed storage
- 需要 fixity 和 version-aware repository behavior
- 需要和 Islandora 这类完整 DAMS stack 集成

OCFL 即使在安装 Fedora 之前也值得学。它能解释 preservation storage 为什么要做到 transparent、predictable、parsable、versioned，以及为什么 repository 应该可以从底层 files 里被理解、验证、迁移甚至重建。

### PostgreSQL: 学 canonical metadata database

PostgreSQL 很适合作为本项目长期的 canonical metadata / workflow database。即使第一个 public app 只是读 JSON 或 CSV，也应该把 durable metadata model 设计成以后能进入 PostgreSQL 的形态。

适合放进 PostgreSQL 的内容：

- canonical record IDs
- source institution references
- normalized date fields
- people / places / subjects
- access status 和 review status
- rights notes
- source links
- import/export job history
- authority crosswalks
- search-index source documents

不建议把 PostgreSQL 当成 preservation file store。它应该存 metadata、relationships、workflow state 和 file/repository object pointers，而不是直接承载 TIFF/WAV/MP4 master files。

## 推荐阶段计划

### Phase 1: Mini Digital Reading Room

先跑：

- ArchivesSpace
- Omeka S
- PostgreSQL
- OpenSearch
- IIIF image service 或 static IIIF-compatible examples
- Mirador

产出：

- 20-100 条 sample records
- 一个小型 collection hierarchy
- 几个 agents / subjects
- Omeka item sets / items / media
- 一个支持 facets 的 search index
- 一两个 IIIF manifests
- 一个 public browse/detail experience

这一阶段的核心学习结果：

团队能清楚区分 archival hierarchy、public collection publishing、canonical metadata、search index、media delivery。

### Phase 2: Repository and Preservation Layer

再评估：

- Fedora
- OCFL
- PREMIS
- fixity workflows
- preservation package layout
- ingest/export boundaries

这一阶段的核心学习结果：

团队能理解 preservation storage 和 repository API 应该如何接到 ArchivesSpace、Omeka S 和 public reading room 之外，而不是和 public website 混成一层。

### Phase 3: Advanced Discovery and Interoperability

再加入：

- authority service
- NARA connector
- OAI-PMH 或其他 export profiles
- vector / hybrid retrieval
- RAG over approved public text
- annotation / citation workflows
- multilingual search and display

这一阶段的核心学习结果：

Digital Reading Room 从 standalone website 进化成 standards-aware discovery interface。

## 系统边界

最重要的架构原则是不要过早把所有职责压进一个系统。

| Responsibility | 第一阶段最佳归属 |
| --- | --- |
| Archival hierarchy / finding-aid structure | ArchivesSpace |
| Public collection / exhibition publishing | Omeka S 或 custom reading-room app |
| Canonical local metadata / workflow state | PostgreSQL |
| Search / retrieval index | OpenSearch |
| Image / A/V manifests and interoperable viewing | IIIF + Mirador |
| High-resolution image zooming | OpenSeadragon 或 IIIF viewer |
| Preservation repository backend | Fedora |
| Preservation file layout / object versioning | OCFL |
| Institutional repository for papers / datasets | DSpace |
| Highly customized repository framework | Samvera / Hyrax / Hyku |

一个系统可能同时有 public page、metadata、file management 和 search integration，但学习和规划时要先把 ownership 拆开。否则后续会很难判断哪个系统是 source of truth，哪个系统只是 presentation 或 index。

## 如果只选三个工具

如果只选三个开源软件自己搭，建议顺序是：

1. ArchivesSpace: 学 archival management。
2. Omeka S: 学 digital collections、metadata template、media、public publishing。
3. OpenSearch: 学 archival retrieval、facets、authority expansion、hybrid search。

IIIF 和 Mirador 应该紧接着加，因为严肃的 Digital Reading Room 最终一定要面对 image / A/V object delivery、manifest、viewer interoperability。

## 对本项目的意义

这个领域很特别的一点是：很多核心基础设施本身就是开源的。因此本项目完全可以不用从商业 vendor 开始，而是先自己搭一个 serious archival / digital collection prototype。

最现实的第一阶段组合是：

```text
ArchivesSpace
  + Omeka S
  + IIIF / Mirador
  + OpenSearch
  + PostgreSQL
```

这已经足够把抽象 framework layer 对应到运行中的软件组件：

- archival intellectual control
- collection metadata
- public access
- media delivery
- search and discovery
- access/review governance
- future preservation repository integration

第二阶段再加入：

- Fedora / OCFL
- PREMIS
- authority service
- NARA connector
- hybrid retrieval
- RAG

这会比只读 architecture 文档有效得多，也能让团队在实现过程中真正理解每一层为什么存在。

## Source Notes

Sources checked on 2026-08-11:

- ArchivesSpace describes itself as an open-source archives information management application for managing and providing access to archives, manuscripts, and digital objects. Its FAQ also clarifies that it is not a DAMS and generally links digital object descriptions to files stored elsewhere: <https://archivesspace.org/> and <https://archivesspace.org/about/faqs>
- Omeka S describes itself as a web publishing platform for institutions connecting digital cultural heritage collections with resources online, with linked open data support and open-source community development: <https://omeka.org/s/> and <https://omeka.org/about/project/>
- Fedora describes itself as a standards-based open-source repository platform for long-term digital preservation, with OCFL-backed persistence and semantic relationships: <https://fedorarepository.org/>
- Islandora documentation describes a Drupal-centered open-source digital asset management/repository ecosystem with microservices, optional Fedora, IIIF, OAI-PMH, JSON-LD, and search integrations: <https://islandora.github.io/documentation/>
- DSpace describes itself as free/open-source repository software commonly used for institutional repositories and durable access to digital content: <https://dspace.org/>
- Hyrax and Hyku are Samvera community repository solutions, with Hyrax as a customizable repository engine and Hyku as a more turn-key application: <https://hyrax.samvera.org/> and <https://hyku.samvera.org/getting-started>
- OpenSearch describes itself as a community-driven, open-source search and analytics suite with support for search, analytics, plugins, ML, and vector retrieval: <https://opensearch.org/about/> and <https://opensearch.org/platform/vector-search/>
- Elastic's licensing FAQ notes the 2021 shift from Apache 2.0 source licensing to SSPL/Elastic License options and the 2024 addition of AGPLv3 as an option, while releases continue under Elastic License: <https://www.elastic.co/pricing/faq/licensing/>
- IIIF defines open standards and APIs for delivering image and audiovisual resources at scale: <https://iiif.io/>
- Mirador describes itself as a configurable, extensible IIIF viewer for image comparison, metadata display, annotations, and IIIF resources: <https://projectmirador.org/>
- OpenSeadragon describes itself as an open-source web viewer for high-resolution zoomable images: <https://openseadragon.github.io/>
- OCFL describes an application-independent storage layout for digital information that supports long-term object management, versioning, transparency, and rebuildability: <https://ocfl.io/>
- PostgreSQL describes itself as an open-source object-relational database system with a liberal open-source license: <https://www.postgresql.org/about/> and <https://www.postgresql.org/about/licence/>
