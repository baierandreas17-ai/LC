# Pre-migration Preparation Checklist for Square

Square migrations rarely fail because data cannot be moved. They fail because the business model behind the storefront shifts in subtle ways: the catalog becomes harder to shop, fulfillment rules do not match real operations, inventory behaves differently across locations, or customers lose familiar purchase paths.

Square is a unified commerce platform. Your online store, POS workflows, customer directory, and item library are designed to work as one system. That creates a major advantage after migration, but it also means “pre-migration preparation” is less about exporting files and more about aligning your data to Square’s operating model before you commit.

Use the checklist below to reduce surprises, define what “done” means, and make your Demo Migration results more meaningful.

#### Checklist: prepare your store for a Square migration

1. **Confirm your Square target model (online-only vs unified commerce)**

* **Prepare**
  * Decide whether Square will be used for online selling only, or as a unified system (POS plus online).
  * Define your location strategy (single location vs multiple locations) and who needs access (teams, reporting owners).
  * If you plan multiple storefronts, confirm whether you will run one site or multiple Square Online sites under the same account.
* **Why this matters**
  * Square’s catalog and operations are tightly connected. If you migrate “as if it’s just a storefront,” you can end up with a catalog that looks acceptable but does not support the daily workflow your team expects.
* **Output**
  * A one-page operating definition covering: channels in scope, number of locations, number of storefronts, and what must work on day one.

2. **Normalize your catalog around Square’s item and variation model**

* **Prepare**
  * Classify your products into practical groups: simple items, multi-option items, bundles, and add-on driven items.
  * Identify products with extreme option complexity (large option sets, many SKU combinations, or deeply nested configuration).
  * Decide how you will represent each group in Square so customers can reliably choose the correct purchasable unit.
* **Why this matters**
  * Square’s core catalog logic is built around items and purchasable variations. If your current platform relies on a different structure, you need a deliberate mapping plan before migration to avoid “variant confusion” and SKU drift.
* **Output**
  * A catalog mapping table that lists each product group and the intended Square representation (item, variation strategy, SKU strategy).

3. **Separate “true choices” from “add-ons” (variations vs modifiers)**

* **Prepare**
  * Audit options and customization inputs and split them into:
    * **True product choices** (changes what is being sold and stocked, usually needs a SKU).
    * **Add-ons / personalization** (changes how the item is prepared, packaged, or personalized).
  * For add-ons, decide what must be selectable at checkout and what can be absorbed into item pricing.
* **Why this matters**
  * Many stores mistakenly force add-ons into the variation structure, which inflates variation counts and makes the catalog harder to maintain. Conversely, treating true variants as add-ons can break inventory accuracy and reporting.
* **Output**
  * A written rule set: “These attributes become variations; these become modifiers or add-ons; these become internal metadata only.”

4. **Define inventory behavior by location**

* **Prepare**
  * Confirm whether inventory is tracked centrally or per location.
  * Identify SKUs that must have location-specific availability (for pickup, local delivery, or regional assortment).
  * Clean up inventory anomalies in the source platform: negative stock, duplicate SKUs, outdated warehouse locations, and inconsistent units of measure.
* **Why this matters**
  * Inventory is not just a product attribute. In Square, inventory and fulfillment are closely tied to locations. If location logic is unclear, you can accidentally allow checkout for items that should not be available.
* **Output**
  * A “location inventory truth” document that defines which SKUs are stockable, where they are stockable, and how out-of-stock behavior should be handled.

5. **Plan navigation and browse logic as a customer experience decision**

* **Prepare**
  * Identify the browsing paths that currently drive revenue: category paths, best-seller routes, branded collections, and seasonal landing pages.
  * Decide which paths must be preserved and which can be simplified.
  * If using multiple Square sites, define how categories and items will be assigned per site to prevent cross-site confusion.
* **Why this matters**
  * Most migrations validate totals. Customers validate the ability to find, compare, and buy. If browsing logic shifts, conversion can drop even when the product count is correct.
* **Output**
  * A prioritized list of “must-work browsing paths” (10 to 30 is typical) that will be tested after Demo Migration and again after Full Migration.

6. **Set pricing expectations and edge-case rules**

* **Prepare**
  * Identify price types in the source platform: base price, sale price, customer-specific pricing, tiered pricing, and bundle pricing.
  * Decide which pricing behaviors must exist in Square on day one, and which can be simplified or deferred.
  * Document rounding rules and tax display expectations (especially for mixed tax scenarios or multi-location selling).
* **Why this matters**
  * Price correctness is not only “a number on a product.” It includes rules and edge cases. If those rules are not defined early, teams often discover gaps only after the catalog is already built.
* **Output**
  * A pricing rule sheet: what is supported immediately, what will be approximated, and what will require customization.

7. **Prepare customer data with relationship integrity in mind**

* **Prepare**
  * Clean duplicates and define your “customer identity” logic (email, phone, or both).
  * List customer fields that must remain usable after migration (addresses, notes, tax identifiers, segments, loyalty indicators, B2B flags).
  * Decide how you will store customer metadata in Square (standard fields vs custom metadata strategy).
* **Why this matters**
  * Customer data is only valuable if it remains actionable. A migration can preserve names and emails but still break segmentation, support workflows, or repurchase journeys.
* **Output**
  * A customer data map that specifies: identity rules, required fields, and what must be searchable or reportable after migration.

8. **Decide how orders should be interpreted after migration**

* **Prepare**
  * Define the purpose of order history in the new system:
    * Support reference only
    * Customer self-service reference
    * Operational workflows (rare for historical orders)
  * Identify sensitive order artifacts that can cause confusion if misinterpreted: refunds, chargebacks, fulfillment state, internal notes, manual adjustments.
  * Decide the cutover logic for “what becomes live operational truth” vs “what remains historical.”
* **Why this matters**
  * Orders are where “surface correctness” can hide functional problems. A store can show historical orders but still fail the operational workflows staff rely on.
* **Output**
  * A documented order policy: what you migrate, what you do not, and how staff should treat migrated orders in daily work.

9. **Lock fulfillment requirements before you validate the catalog**

* **Prepare**
  * Define which fulfillment methods are required: shipping, pickup, local delivery, and any location-specific restrictions.
  * For multi-location stores, define which items are eligible for which methods by location.
  * Identify products with special fulfillment logic (perishables, oversized, regulated products, made-to-order).
* **Why this matters**
  * Fulfillment configuration influences item availability and checkout behavior. If fulfillment is decided late, you will rework catalog decisions that were already “validated.”
* **Output**
  * A fulfillment matrix by location: shipping, pickup, delivery, and exceptions.

10. **Inventory your integrations and extension-driven data**

* **Prepare**
  * List the systems that currently create or store business-critical data: subscriptions, bookings, loyalty, ERP/accounting, shipping tools, marketplace connectors, product personalization apps, POS add-ons.
  * Identify which systems will be replaced by Square-native capabilities and which must remain integrated.
  * Flag any extension-driven data that is not part of core entities but still required (custom identifiers, membership tiers, entitlement flags, warranties).
* **Why this matters**
  * Extension-driven data is one of the most common sources of “migration hallucination,” where the storefront looks correct but key workflows fail because the business logic lives outside core entities.
* **Output**
  * A dependency register with three tags per system: replace, integrate, or retire.

11. **Keep SEO and URL continuity proportional to your channel reality**

* **Prepare**
  * If organic search matters, identify your priority URLs (top landing pages, top product pages, top categories, high-performing content).
  * Decide whether you will preserve the same domain and define how your new URL structure will differ from the old.
  * If SEO is not material, minimize effort and focus validation on shopping behavior and checkout.
* **Why this matters**
  * Redirect work is only valuable when it protects meaningful traffic and preserves customer intent. Over-emphasizing redirects in low-SEO businesses wastes time that should be spent validating catalog and checkout behavior.
* **Output**
  * A practical SEO scope statement: which URLs must be preserved and how success will be measured post-launch.

12. **Design a Demo Migration sample that can actually reveal risk**

* **Prepare**
  * Build a sample that includes complexity, not just volume:
    * Multi-option items and add-on heavy items
    * Products with multiple images and edge-case naming
    * Customers with imperfect data (duplicates, missing fields)
    * Orders with discounts, shipping variations, and different fulfillment outcomes
  * Assign owners for validation and define pass conditions before you run the Demo Migration.
  * Use findings to decide whether the project should remain simple or requires a more guided approach.
* **Why this matters**
  * A Demo Migration is only useful when it tests the behaviors that can break the store after launch. A “clean” sample produces false confidence.
* **Output**
  * A Demo Migration plan with: sample definition, validation checklist, and sign-off criteria.

### Conclusion

A well-prepared Square migration is not “export everything and import it.” It is a controlled translation of your selling model into Square’s unified catalog, fulfillment, and customer experience. If you complete the checklist above before running your Demo Migration, your results will be clearer, your risk will be lower, and the final migration scope will be easier to define.

If you want a fast way to validate your readiness, run a Demo Migration using a sample designed to test real complexity, then review the results against your pass conditions. If you prefer, you can also share your sample data and requirements and ask Next-Cart to run the Demo Migration for you and walk you through what the results mean. For scoping questions, edge-case mapping, or complexity concerns, Live Chat is the most efficient way to align expectations before you commit to a full migration.

#### FAQs

<details>

<summary><strong>Should I clean all my data before migrating to Square?</strong></summary>

Usually no. Focus on high-impact areas that affect buying behavior, navigation, and validation confidence, then use early validation to surface the few patterns that create most surprises.

</details>

<details>

<summary><strong>Do I need to fully build my Square Online website before migrating?</strong></summary>

Not fully. You do need a clear operating model and basic structure decisions (locations, fulfillment methods, and how products will be represented). The goal is to ensure the migrated data will behave correctly once the storefront is assembled.

</details>

<details>

<summary><strong>How do I decide what must be included in scope?</strong></summary>

Define scope by outcomes first, then map those outcomes to core categories like products/variations, customers, and orders, plus supporting content such as priority URLs.

</details>

<details>

<summary><strong>How much data should be included in a Square Demo Migration sample?</strong></summary>

Enough to expose complexity, not just prove counts. Include at least a handful of multi-option items, one or two add-on heavy products, representative customers, and orders that reflect real discounting and fulfillment patterns.

</details>

<details>

<summary><strong>How should I handle products with a very large number of options?</strong></summary>

Start by separating true variants from add-ons. If your option structure creates an extremely high number of SKU combinations, you may need a redesigned representation in Square (for example, splitting into multiple items or simplifying certain choice structures).

</details>

<details>

<summary><strong>What is the most important “data cleanup” task before migrating to Square?</strong></summary>

SKU and identity discipline. Resolve duplicate or inconsistent SKUs and define how customers are uniquely identified (email, phone, or both). These two decisions prevent many downstream issues across catalog accuracy, inventory, and customer history.

</details>
