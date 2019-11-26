# Purpose # {#why-does-this-document-exist}

The guidelines defined in this document support the creation of interoperable services for high-quality video distribution based on MPEG-DASH and related standards. These guidelines are provided in order to address DASH-IF members' needs and industry best practices. The guidelines support the implementation of conforming service offerings as well as DASH client implementations.

While alternative interpretations may be equally valid in terms of standards conformance, services and clients created following the guidelines defined in this document can be expected to exhibit highly interoperable behavior between different implementations.

# Interpretation # {#interpretation}

Requirements in this document describe service and client behaviors that DASH-IF considers interoperable.

If a **service provider** follows these requirements in a published DASH service, the published DASH service is likely to experience successful playback on a wide variety of clients and exhibit graceful degradation when a client does not support all features used by the service.

If a **client implementer** follows the client-oriented requirements described in this document, the DASH client will play content conforming to this document provided that the client device media platform supports all features used by a particular DASH service (e.g. the codecs and DRM systems).

This document uses statements of fact when describing normative requirements defined in referenced specifications such as [[!DASH]] and [[!CMAF]]. References are typically provided to indicate where the requirements are defined.

[[!RFC2119]] statements (e.g. "SHALL", "SHOULD" and "MAY") are used when this document defines a new requirement or further constrains a requirement from a referenced document.

<div class="example">
Statement of fact:

* A DASH presentation **is** a sequence of consecutive non-overlapping periods [[!DASH]].

New or more constrained requirement:

* Segments **SHALL NOT** use the MPEG-TS container format.

</div>

All DASH presentations are assumed to be conforming to these guidelines. A service MAY explicitly signal itself as conforming by including the string `https://dashif.org/guidelines/` in `MPD@profiles`.

There is no strict backward compatibility with previous versions - best practices change over time and what was once considered sensible may be replaced by a superior approach later on. Therefore, clients and services that were conforming to version N of this document are not guaranteed to conform to version N+1.

# Disclaimer # {#legal}

This is a document made available by DASH-IF. The technology embodied in this document may involve the use of intellectual property rights, including patents and patent applications owned or controlled by any of the authors or developers of this document. No patent license, either implied or express, is granted to you by this document. DASH-IF has made no search or investigation for such rights and DASH-IF disclaims any duty to do so. The rights and obligations which apply to DASH-IF documents, as such rights and obligations are set forth and defined in the DASH-IF Bylaws and IPR Policy including, but not limited to, patent and other intellectual property license rights and obligations. A copy of the DASH-IF Bylaws and IPR Policy can be obtained at http://dashif.org/.

The material contained herein is provided on an "AS IS" basis and to the maximum extent permitted by applicable law, this material is provided AS IS, and the authors and developers of this material and DASH-IF hereby disclaim all other warranties and conditions, either express, implied or statutory, including, but not limited to, any (if any) implied warranties, duties or conditions of merchantability, of fitness for a particular purpose, of accuracy or completeness of responses, of workmanlike effort, and of lack of negligence.

In addition, this document may include references to documents and/or technologies controlled by third parties. Those third party documents and technologies may be subject to third party rules and licensing terms. No intellectual property license, either implied or express, to any third party material is granted to you by this document or DASH-IF. DASH-IF makes no any warranty whatsoever for such third party material.

Note that technologies included in this document and for which no test and conformance material is provided, are only published as a candidate technologies, and may be removed if no test material is provided before releasing a new version of this guidelines document. For the availability of test material, please check http://www.dashif.org.

# DASH and related standards # {#dash-is-important}

DASH (dynamic adaptive streaming over HTTP) [[!DASH]] is a technology for adaptive media delivery. Initially published by ISO/IEC in April 2012, it has been continually updated, with the 4th edition published in 2020.

CMAF (common media application format) [[!CMAF]] is a media container format based on ISO Base Media File Format [[!ISOBMFF]]. It defines data structures for media delivery compatible with DASH and other similar technologies such as [[HLS]]. Initially published by ISO/IEC in 2018, it has been updated in 2019 with the publishing of the 2nd edition.

This document is based on the 4th edition DASH [[!DASH]] and 2nd edition CMAF [[!CMAF]] specifications.

DASH together with related standards and specifications is the foundation for an ecosystem of services and clients that work together to enable audio/video/text and related content to be presented to end-users.

<figure>
	<img src="Images/RoleOfIop.png" />
	<figcaption>This document connects DASH with international standards and industry specifications.</figcaption>
</figure>

[[!DASH]] defines a highly flexible set of building blocks that needs to be constrained to ensure interoperable behavior in common scenarios. The necessary media container constraints are largely defined by [[!CMAF]] and [[!DASH-CMAF]]. This document defines further constraints to limit DASH features to those that are considered appropriate for use in interoperable clients and services.

Clients consuming DASH content will need to interact with the host device's media platform. The guidelines in this document assume that the media platform implements APIs that are equivalent to Media Source Extensions [[media-source]] and Encrypted Media Extensions [[encrypted-media]]. API level compatibility is not required but equivalent features are expected.

This document was generated in close coordination with [[DVB-DASH]]. The features are aligned to the extent considered reasonable. The tools and features are aligned to the extent considered reasonable. In addition, DASH-IF worked closely with ATSC to develop a DASH profile for ATSC3.0 for broadcast distribution [[ATSC3]].