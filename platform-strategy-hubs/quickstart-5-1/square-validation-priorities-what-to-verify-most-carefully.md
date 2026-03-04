# Square Validation Priorities: What to Verify Most Carefully

Square migrations should be validated behavior-first, not totals-first. Square is designed to run commerce across channels, which means a store can look correct on the surface while the underlying selling logic is misaligned. The highest-value validation work confirms that items sell the way customers expect, inventory behaves the way staff relies on, and orders remain usable across the workflows that matter.

A Square migration is validated when:

* Shoppers can find the right item, choose the intended configuration, and complete checkout without confusion.
* The same catalog logic supports how you sell in real life (pricing, modifiers, inventory, fulfillment).
* Operational workflows still work, including order handling, refunds, and basic customer support tasks.
* If SEO continuity matters, priority URL paths resolve intentionally after launch.

Before diving into the priority areas, define what you will validate and with what sample. The most useful first pass uses a representative Demo Migration sample, not random records.

A high-quality validation sample typically includes:

* Best sellers and the items that drive the most support volume
* The most configuration-heavy items (many options, add-ons, bundles, or customizations)
* Items where pricing differs by selection or add-on
* Products where inventory accuracy is operationally critical
* A mix of fulfillment types (shipping, pickup, local delivery) if applicable
* A small set of real-world orders that represent typical workflows if order history is in scope
* Priority URLs only if SEO is a deliverable for your project

#### Priority 1: Sellable item and variation integrity

In Square, items are not validated when they “exist.” They are validated when the correct sellable choice is created and customers can buy it. This matters because Square’s catalog model relies on variations as the sellable unit, and many behaviors attach to variation-level data.

**Validate**:

* Each product has the correct sellable variation structure for how you sell it (single-SKU items versus multi-option items).
* Variation names and selection labels match what customers recognize.
* The correct variation is what gets added to cart and purchased.
* Variation-level identifiers that operations rely on (such as SKU conventions) are consistent and visible where needed.

**High-risk indicators**:

* Items display correctly but the wrong selection is purchasable, or a key option is missing.
* Products appear “flattened” into a single sellable choice even though the source store sells multiple variants.
* The store shows choices but purchasing does not reflect the intended sellable unit.

**What to include in your sample**:

* Your most variation-heavy best sellers.
* Items with option-dependent pricing.
* Items where fulfillment or inventory differs by selection.

#### Priority 2: Options, add-ons, and modifier behavior

Square stores often rely on add-ons and customizations that shape what customers actually buy. A migration can move the base item record but still fail in practice if option structures, modifier rules, or price adjustments do not behave correctly.

**Validate**:

* Options and add-ons appear in a way that matches shopper expectations.
* Required versus optional selections behave correctly.
* Price adjustments for add-ons or upgraded selections apply as intended.
* Any constraints that matter to selling behavior (such as selection limits) are respected.

**High-risk indicators**:

* Add-ons exist but do not change the line item outcome the way your business expects.
* Price changes are missing, doubled, or applied to the wrong selection.
* Customers can select combinations that should not be purchasable.

**What to include in your sample**:

* Items with multiple add-ons and a mix of required and optional selections.
* Items where add-ons are the primary profit driver or a frequent cause of support tickets.

#### Priority 3: Pricing, taxes, and discount behavior

Square validation should confirm that the money behaves correctly, not only that numbers were migrated. This is where many “looks fine” migrations break down because price presentation can differ from the actual checkout calculation.

**Validate**:

* Base prices and variation prices match your intended selling model.
* Discounts behave correctly for representative scenarios (item-level versus order-level patterns).
* Tax behavior matches your operating reality, especially if your business has multiple locations or mixed product types.

**High-risk indicators**:

* Prices appear correct on item pages but differ at checkout.
* Discount logic works for simple items but fails for configured items.
* Taxes apply unexpectedly to products that should be treated differently in your business context.

**What to include in your sample**:

* A mix of high-volume items, high-price items, and items with add-ons.
* A few real promotional scenarios you run frequently.

#### Priority 4: Inventory, locations, and fulfillment readiness

Square is often chosen because it connects selling and operations. That makes inventory and fulfillment validation a top priority, especially for multi-location merchants or stores that sell both online and in person.

**Validate**:

* Inventory counts reflect the expectations of your operational workflow.
* Stock status and availability match how you actually fulfill items.
* Fulfillment methods that matter to your store are represented and usable (shipping, pickup, local delivery, or other applicable methods).
* Items that should not be fulfillable in certain ways are restricted appropriately.

**High-risk indicators**:

* Items show as in stock but cannot be fulfilled correctly.
* Inventory looks correct in one context but not in another (location-specific behavior).
* Pickup or delivery scenarios work for some products but fail for configured products.

**What to include in your sample**:

* Items with fast-moving inventory.
* Items sold in multiple channels.
* Items with different fulfillment constraints (bulky, fragile, made-to-order, local-only).

#### Priority 5: Customer identity and continuity

Customer validation is not only “did contacts migrate.” It is whether Square can recognize customers in a way that supports your operations, marketing, and support workflows. This becomes especially important if your source platform had strong account functionality and you want continuity in how customers identify themselves.

**Validate**:

* Customer profiles are accurate enough to support your key workflows (contact, support, segmentation).
* Duplicates and identity conflicts are understood and manageable (for example, multiple records that represent the same person).
* Customer account expectations are aligned with what Square will provide, especially around order history visibility and reordering behavior.

**High-risk indicators**:

* Customer records exist but cannot be used reliably for support or marketing.
* The store expects rich account history behavior, but the new customer experience is more limited than anticipated.

**What to include in your sample**:

* A set of repeat customers.
* Customers with multiple addresses or meaningful profile attributes.
* A few customers tied to representative orders if orders are in scope.

#### Priority 6: Order usability and support workflows

If order history is included in your migration scope, validate whether orders remain usable for real work. A migration can move an order record but still fail the operational outcome if staff cannot find what they need, interpret the order correctly, or manage common post-purchase scenarios.

**Validate**:

* Order visibility supports customer support needs (what was bought, key identifiers, and basic order context).
* Fulfillment outcomes match expectations (status handling, shipping versus pickup behavior).
* Refund and cancellation workflows are understood and workable for your operating model.

**High-risk indicators**:

* Orders exist but are not actionable for support workflows.
* Status expectations do not map cleanly to how your team works.
* Post-purchase actions become slower or require manual workarounds that you did not anticipate.

**What to include in your sample**:

* A small range of orders that represent typical workflows: fulfilled, partially fulfilled, cancelled, refunded, and edited scenarios where applicable.

#### Priority 7: Merchandising and discoverability in Square Online

Once selling logic is correct, the next risk is whether shoppers can find what they want. Discoverability issues often show up as “missing products,” even when the underlying records exist.

**Validate**:

* Category structures and browse paths align with how customers shop your store.
* Search and filtering behavior supports your most important buying journeys.
* Product pages display meaning-critical information where shoppers rely on it (key specs, compatibility cues, or selection guidance).

**High-risk indicators**:

* Customers can buy an item if they find it, but discovery is weaker than before.
* Category membership is correct in data but not effective in storefront behavior.
* Key buying information is missing or placed where shoppers will not see it.

**What to include in your sample**:

* Your top revenue categories.
* A few categories that represent different merchandising patterns (seasonal, brand-led, collection-led).

#### Priority 8: Priority URLs if SEO continuity matters

Not every Square migration needs SEO continuity as a core deliverable. If SEO is important, validate it deliberately, but keep it focused.

**Validate**:

* A priority list of URLs resolves intentionally after launch.
* New URL paths align with your category and product organization.
* Redirect readiness exists for pages whose paths must change.

**High-risk indicators**:

* The store launches with broken priority paths.
* Paths resolve, but to the wrong destination, creating user confusion and wasted traffic.

**What to include in your sample**:

* Top product URLs, top category URLs, and a short list of campaign or organic landing pages that drive meaningful traffic.

### Conclusion

Square validation is most reliable when it is based on real outcomes. Start with a representative sample, define pass conditions in terms of buying and operating behavior, and validate in a sequence that matches business risk. If you can only validate a few areas deeply, prioritize sellable variation integrity, option and add-on behavior, and fulfillment readiness first. Those three areas surface structural mismatches faster than any record-count check.

Run a Demo Migration using best sellers, your most configurable items, and fulfillment-sensitive products, then review results against clear acceptance criteria. If you prefer, you can provide sample data and ask Next-Cart to run the Demo Migration and share the results. For complex catalogs or multi-location operations, Live Chat is the fastest way to align scope and confirm what must remain true after launch.

#### FAQs

<details>

<summary><strong>What is the most common reason a Square migration looks correct but fails in real usage?</strong></summary>

Misaligned sellable structure. Items and images can appear correct while variation logic, add-ons, or fulfillment behavior differs from how your store actually sells

</details>

<details>

<summary><strong>What should I validate first if time is limited?</strong></summary>

Start with product purchase behavior for best sellers and complex products, then category navigation, then customer and order workflows. These areas usually drive most revenue and support load.

</details>

<details>

<summary><strong>Do I need to validate orders if order history is not included in scope?</strong></summary>

You should still validate your order workflow from new purchases (checkout, fulfillment, refunds) because that is what your team will use immediately after launch.

</details>

