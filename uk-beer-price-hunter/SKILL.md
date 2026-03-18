---
name: uk-beer-price-hunter
description: Researches and compares beer prices (specifically San Miguel Especial) across mainstream UK supermarkets (Aldi, Lidl, Morrisons, Asda, Tesco, Waitrose, M&S). Use when the user asks for the best beer prices or a price comparison.
---

# UK Beer Price Hunter

This skill specializes in finding the lowest "price per litre" for beer in the UK.

## Objective
Find the best price per litre for San Miguel Especial (or other requested beers) across major retailers.

## Workflow
1. **MANDATORY: OFFICIAL SITES ONLY**. Use `web_search` and `web_fetch` to find prices exclusively on the supermarket's own domain (e.g., tesco.com, morrisons.com, asda.com, sainsburys.co.uk, aldi.co.uk, ocado.com).
2. **BAN ALL THIRD-PARTY DATA**: Strictly ignore Trolley.co.uk, LatestDeals, HotUKDeals, PriceSpy, or any aggregator. Do not use search snippets unless they are from the official retailer's site and you have verified the timestamp.
3. For Lidl (offline-focused), check for current "Lidl Plus" or "Super Weekend" deals on the official lidl.co.uk site or via their official digital leaflets.
4. Calculate the **Price per Litre** (Total Pack Price / Total Volume in Litres).
- *Example: 12 x 330ml = 3.96L. £11 / 3.96L = £2.78 per litre.*
5. Present the data using the mandatory template below.

## Output Template
**Date:** [Current Date]
**Beer:** [Beer Name]

Place | Price per Litre | Price per pack
--- | --- | ---
[Supermarket] | £[X.XX] | £[XX.XX] ([Size/Count])

## Special Instructions
- **STRICT DATA VALIDATION**: You must verify the pack size, unit count, and price directly on the official retailer's page.
- **User-Provided URLs**: If the user provides a direct link to an official retailer, treat the information on that page as the single source of truth for that retailer.
- **Inclusive Comparison**: Always list ALL official options found. If multiple retailers have the same price, list them all to give the user geographic options.
- **Unit Calculation**: Always convert total pack volume to Litres for the "Price per Litre" comparison.
- **URL Verification**: Before linking the winner, read the page title or product description at the URL to confirm the pack size matches your calculation.
