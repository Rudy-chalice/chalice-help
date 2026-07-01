# DV360 Reporting Setup Guide

Reporting is how we track delivery and measure performance on your Chalice campaigns in DV360. What you need to send us depends on which Chalice product you are running. This guide covers all three products and the exact DV360 reporting each one needs.

If you are not sure which product you are running, your Chalice team can confirm it.

!!! tip "Quick answer"
    For Curate and Growth Audiences, set up a daily DV360 report that covers the last 7 days and email it to service.accounts@chalice.ai. For AI Allocator, we pull the data ourselves through the DV360 API, so there is nothing for you to send.

## At a glance

| Product | Do you send DV360 reporting? | What to send |
| --- | --- | --- |
| Curate | Only if you have performance goals | Daily report, last 7 days |
| Growth Audiences | Yes | Daily report, last 7 days |
| AI Allocator | No, we pull it through the API | Nothing |

---

## How to send DV360 reporting

For Curate and Growth Audiences, the setup is the same. In DV360, build a report with the dimensions and metrics listed under your product below, then schedule it for automated delivery to Chalice.

- Frequency: daily
- Date range: the last 7 days (a rolling 7-day window)
- Send to: service.accounts@chalice.ai

!!! note "Why a rolling 7-day window"
    DV360 keeps updating conversions for prior days after they happen. A daily report that always looks back 7 days makes sure we capture the final numbers, not just same-day figures.

---

## 1. Curate

Curate is our curated PMP deal product. Delivery data comes straight from the exchange, so we already have it on our end. We only need reporting from you if your campaign has performance goals such as conversions.

If you do, send a daily DV360 report covering the last 7 days with the fields below.

**Dimensions**

- Date
- Insertion Order
- Insertion Order ID
- Line Item (filter to the Chalice line item that has our PMP deal assigned)
- Line Item ID
- Inventory Source
- Inventory Source ID
- Inventory Source Group
- Inventory Source ID (External)

**Metrics**

- Revenue (Advertiser Currency)
- Impressions
- Total Conversions

!!! note "Revenue vs media cost"
    Use Revenue (Advertiser Currency). That is your total cost including fees, which is what we pace against. Exchange-side figures show media cost only, so they understate spend.

!!! note "If you use Campaign Manager 360 as your ad server"
    When your conversions live in Campaign Manager 360 (formerly DCM), also send a daily CM360 report for the last 7 days to service.accounts@chalice.ai.

    Dimensions: Date, Campaign, Campaign ID (filtered to the campaign Chalice is included in), Placement (filtered to the Chalice placements), Placement ID.

    Metrics: Clicks, Impressions, Total Conversions (including all Floodlight activities attributed to the campaign).

---

## 2. Growth Audiences

Growth Audiences (formerly AI Audiences) are custom audiences we build and push into your DSP. Reporting comes from wherever the audience runs, so for DV360 activations we need the DV360 report.

Send a daily DV360 report covering the last 7 days with the fields below. This is the same setup as Curate.

**Dimensions**

- Date
- Insertion Order
- Insertion Order ID
- Line Item (filter to the Chalice line item that has our PMP deal assigned)
- Line Item ID
- Inventory Source
- Inventory Source ID
- Inventory Source Group
- Inventory Source ID (External)

**Metrics**

- Revenue (Advertiser Currency)
- Impressions
- Total Conversions

!!! note "If you use Campaign Manager 360 as your ad server"
    Send the same daily CM360 report described under Curate to service.accounts@chalice.ai (Date, Campaign, Campaign ID, Placement, Placement ID, plus Clicks, Impressions, and Total Conversions).

---

## 3. AI Allocator

AI Allocator shifts budget across markets (DMAs) to drive your sales goals. Reporting here is focused on spend by market.

There is nothing for you to send. We pull the DV360 data directly through the API on our end. For reference, here is what we capture.

**Dimensions**

- Date
- Advertiser Name and ID
- Insertion Order Name and ID
- Line Item Name and ID
- Budget Segment Name, Budget, Start Date, and End Date
- DMA Code and DMA Name

**Metrics**

- Impressions
- Revenue (USD)
- Revenue eCPM (USD)
- Media Cost (USD)
- Media Cost eCPM (USD)

---

## Related articles

- [Accepting a PMP Deal in DV360](accepting-a-pmp-deal.md)
- [Line Item Setup Guide for PMP Deals in DV360](line-item-setup-guide-pmp.md)
- [DV360 Deal Setup Best Practices](deal-setup-best-practices.md)
