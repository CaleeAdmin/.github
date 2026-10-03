# Calee Vision

**Status:** Product and network direction

**Purpose:** Record the durable strategic direction that Calee's product, architecture and network work should converge on. This document describes the intended direction; it does not by itself change runtime behaviour, commercial entitlements, pricing, permissions or release status.

## Vision

> **A world where the schedules people depend on come directly from the source and stay current everywhere.**

The vision is intentionally broader than a calendar app, a family display or a catalogue website. Calee should make important schedules easier to publish, trust, discover and keep current wherever people need them.

## Mission

> **Calee connects the organisations that publish schedules with the people who depend on them.**

The mission describes the network Calee is building:

```text
organisations that publish schedules
        ↓
Calee publishing + trust
        ↓
Calee distribution
        ↓
people, families and communities that depend on those schedules
```

## Strategic category

Calee should be designed as a **trusted schedule distribution network**.

The long-term Australian ambition is:

> **Become the default distribution layer for Australian calendar and schedule information.**

This does not mean Calee should merely collect the largest possible database of events. The durable asset is the trusted relationship between:

- the organisation that owns or authorises the schedule;
- the calendar/publication that carries it;
- Calee's verification, provenance and distribution layer; and
- the people who follow and depend on it.

## Product system

Calee has three commercial customer products:

- **Calee Home** — household coordination.
- **Calee Business** — organisational coordination, publishing/distribution and shared displays.
- **Calee Enterprise** — contract/project-defined organisational deployments.

Shared clients and distribution surfaces include Calee Mobile, Calee Display, Web, CalEmbed, subscriptions, Event Links and future approved partner/data interfaces.

Vertical solutions such as **Calee for Education** and **Calee for Sports Clubs** are Calee Business solutions, not separate platform products.

## Network model

The target network is:

```text
                         SUPPLY

        Schools / Clubs / Businesses / Government
                              │
                              ▼
                       Calee Business
                  create / maintain / publish
                              │
                              ▼

                    TRUST + DISTRIBUTION

                      Publisher Identity
                              │
                       Verification
                              │
                      Calendar Catalogue
                              │
              ┌───────────────┼────────────────┐
              ▼               ▼                ▼
          Public Web       Calee Mobile      CalEmbed
              │               │                │
              ├──── Search / AI discovery ─────┤
              │               │                │
              └──────────── Follow ─────────────┘
                              │
                              ▼

                           PEOPLE

                     Calee Home / Mobile
                              │
                 calendars / family coordination
```

The supply, trust and distribution layers are what turn Calee from a collection of calendar products into a network.

## Publisher principle

Calee should make external distribution the easiest entry point into Calee Business.

A small organisation should be able to understand the proposition as:

> **Create your schedule once. Put it on your website, share it with customers or members, and publish it through Calee.**

A future/self-service entry tier may be presented as **Calee Publisher — Free**, while remaining technically and commercially part of Calee Business rather than becoming a parallel product/account system.

The intended self-service journey is:

```text
Discover Calee
    ↓
Self-register
    ↓
Prove identity / organisation claim
    ↓
Create calendar
    ↓
Publish / embed
    ↓
Submit to Calee Calendars
    ↓
Calee moderation
    ↓
Public Catalogue
    ↓
People discover and follow
    ↓
Updates continue to flow from the publisher
```

## Trust model

Trust is part of the product, not a cosmetic badge.

Calee must keep these facts separate:

```text
can register
    != controls a Calee account
    != represents the claimed organisation
    != verified publisher
    != calendar approved
    != calendar discoverable
```

For Australian business self-registration, an ABN can prove that a registered entity exists, but not that the registrant controls it. Business-domain email or DNS control can provide stronger organisation-control evidence, while legitimate applicants without a business-domain mailbox need a manual-review path.

Schools, clubs, community groups and government bodies may require different authoritative evidence. ABN must not become a universal publisher requirement.

Publisher verification remains separate from calendar moderation. A verified publisher does not automatically make every calendar public or every event factually correct.

## Authority and provenance

The strongest long-term Calee calendar is one where:

```text
organisation
    ↓
verified / authorised publisher identity
    ↓
authorised calendar
    ↓
events and schedule updates
    ↓
Calee distribution
```

Calee should prefer publisher-authorised provenance over unauthorised aggregation whenever practical.

Calee-curated authoritative calendars may still be valuable, for example public holidays or school-term information derived from authoritative public sources. They must be labelled truthfully and must not imply that an external organisation itself publishes through Calee unless that relationship actually exists.

## Calendar Catalogue

The Calendar Catalogue is the trusted registry/discovery layer, not the event database itself.

It should answer questions such as:

- What calendar is this?
- Who publishes it?
- Is the publisher verified?
- Is this calendar intentionally discoverable?
- What geography/category/audience does it serve?
- Can a Calee user follow it?

The Catalogue must keep source credentials, public capability tokens, provider internals and tenant/account identifiers private.

## Public Event Index

If Calee later indexes public events at scale, that should be a separate domain from the Calendar Catalogue.

Conceptually:

```text
Publisher
    ↓
Catalogue Entry
    ↓
Approved Publication
    ↓
ingestion / normalisation
    ↓
Public Event Index
    ↓
Web / Search / AI / partner interfaces
```

The Event Index must preserve provenance, recurrence identity, revisions, cancellations/reschedules, freshness and public/search-indexability. Not every public calendar event should automatically become a search-indexed event page.

## Distribution channels

One publisher calendar may eventually distribute through:

- Calee Business;
- the publisher's own website/embed;
- Calee Calendars on the public web;
- Calee Mobile;
- Calee Home and Calee Display;
- external calendar subscriptions where supported;
- search engines and AI discovery;
- approved future partner/data APIs.

The publisher should not have to maintain separate copies for every channel.

## Business model direction

Calee can create value on both sides of the network.

The product vision can be stated simply as:

> **Calee Business and Calee Family into one network.**

The Business side supplies and maintains useful schedules; the Family/consumer side discovers, follows and depends on them. Free publishing can therefore create network value even before a publisher becomes a paid Business customer.

The approved Publisher-Free V1 entry entitlement is:

```text
1 active Business user
3 qualifying Business-owned calendars
public publishing encouraged
```

Public followers, viewers and search/AI discovery reach are not the primary commercial quota. Paid Calee Business should monetise organisational operating complexity — additional users, calendars and later approved capabilities — while preserving the network incentive to publish useful calendars.

Paid Business plan names, prices and higher limits remain deliberately undecided and belong to the Core commercial/product-policy process rather than this vision record.

Publisher-side opportunities include:

- Business plans;
- additional calendars/users/displays/features;
- analytics;
- integrations;
- enterprise/vertical solutions.

Consumer-side opportunities include:

- Calee Home;
- Calee AI;
- Calee Display;
- future services built on trusted schedule data.

Platform-side opportunities may eventually include:

- partner APIs;
- data licensing;
- trusted event/calendar distribution.

No future API or licensing model should bypass publisher rights, provenance or revocation.

## Network effect

The intended flywheel is:

```text
more verified publishers
        ↓
more useful trusted calendars
        ↓
more discovery and followers
        ↓
more value to publishers
        ↓
more organisations choose Calee
        ↓
stronger publisher relationships and provenance
```

The moat is not simply the number of database rows.

The defensible asset is the combination of:

- verified publisher relationships;
- authoritative provenance;
- freshness and lifecycle handling;
- distribution reach;
- subscriptions/followers;
- publisher website relationships/backlinks;
- operational trust.

## Primary network KPI

The most important long-term network metric should be:

> **Number of verified organisations for which Calee is an official calendar publishing or distribution endpoint.**

Supporting measures may include:

- active verified publishers;
- active approved calendars;
- source freshness;
- follower/subscription counts;
- publisher website embeds/backlinks;
- public discovery/search reach;
- successful follow conversion;
- publisher retention;
- paid Business conversion.

Metrics must preserve the privacy and evidence standards of the underlying product contracts.

## Product principles

1. **Publish once, distribute everywhere.**
2. **Trust must be proved, not implied by display text.**
3. **Public does not automatically mean discoverable.**
4. **Discoverable does not automatically mean search-indexable.**
5. **Publisher verification does not automatically approve every calendar.**
6. **A public URL or ICS capability is not publisher authority.**
7. **Source credentials and capability tokens stay server-side.**
8. **Reuse Calee's existing identity, tenant, entitlement and moderation authorities; do not create parallel models.**
9. **Prefer stable Calee identities over provider URLs/tokens as product identity.**
10. **Keep Home, Business and Enterprise commercially distinct while sharing the Calee platform and clients.**
11. **Preserve publisher rights and revocation in every distribution channel.**
12. **Build network quality before maximising catalogue quantity.**

## Near-term strategic sequence

The current direction is:

1. operate and expand the approved Calee Calendar Catalogue;
2. complete reliable Web → Calee follow handoff;
3. implement trusted Business/Publisher self-registration;
4. give publishers one coherent Share / Publish workflow;
5. prove the publisher → catalogue → follower loop with real organisations;
6. grow authoritative schools, clubs, schedule-publishing small businesses and other useful publishers;
7. add scalable catalogue taxonomy and discovery as catalogue size requires it;
8. build a public event index only after provenance/freshness demand justifies it;
9. consider partner API/data licensing only when rights and network scale support it.

## What Calee is not

Calee is not intended to become:

- an unauthorised scraper of every public event on the internet;
- a generic social network;
- a second competing identity system for each product;
- a public database that leaks publisher source URLs or tokens;
- a directory where anyone can claim a famous organisation by typing its name;
- a system that calls every Calee-hosted calendar "official" without evidence;
- a collection of disconnected vertical products.

## Decision test

When evaluating a new Calee feature, ask:

1. Does it help an authorised organisation publish or maintain schedules?
2. Does it improve trust, provenance or freshness?
3. Does it help people discover, follow or use the schedule?
4. Does it strengthen the publisher ↔ Calee ↔ follower relationship?
5. Does it preserve Calee's authority and privacy boundaries?
6. Does it reuse the existing platform instead of creating another parallel product model?

Features that strengthen this loop are aligned with the Calee vision.
