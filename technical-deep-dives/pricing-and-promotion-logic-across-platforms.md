# Pricing and Promotion Logic Across Platforms

Promotions can survive migration as records and still fail as commercial rules.

A discount code may still exist in the target store, yet the behavior behind it can change because platforms do not always apply pricing rules in the same way. What looks like a simple coupon on the storefront may actually depend on eligibility logic, product or category conditions, customer segmentation, stacking rules, shipping treatment, rounding behavior, or tax interactions. When those underlying rules are represented differently, the promotion may still appear familiar while the commercial outcome changes.

This matters because promotions are rarely isolated marketing elements. They influence conversion, average order value, customer expectations, margin control, and support workload. In many stores, discount logic also depends on how products, categories, customers, and taxes are represented. A promotion that works in one platform can therefore become less predictable when the target platform applies the same intent through a different rule structure.

### Promotions are rules, not just codes

A coupon code and a promotion rule are not the same thing.

The code is the customer-facing trigger. The rule is the logic that decides what the discount does, who can use it, what it applies to, when it stops applying, and whether it combines with anything else. That distinction matters because a code can migrate in name while the rule behind it becomes weaker, broader, narrower, or structurally different.

A promotion rule may include:

* minimum spend thresholds
* product or category eligibility
* customer-group or segment eligibility
* exclusions for specific products or sale items
* usage limits
* time restrictions
* stacking behavior with other offers
* shipping-related conditions

When those elements change, the commercial meaning of the promotion changes even if the discount code remains recognizable.

### Discounts can apply in different layers

Platforms do not always apply discounts in the same place.

A promotion may operate at:

* order level
* line-item level
* shipping level
* customer-group pricing level
* catalog pricing level
* cart-condition level

That difference matters because it affects:

* what the customer sees in the cart
* how totals are distributed across products
* how support teams interpret discounts after purchase
* how margins are affected
* how reporting reads discount impact
* how taxes and shipping calculations interact with the discounted amount

A store can therefore preserve the idea of a promotion while changing how the discount is actually applied. In some cases, the cart total may still look close enough at first glance, while the underlying distribution changes in ways that matter operationally and financially.

### Why similar promotions behave differently after migration

Promotion behavior usually changes because platforms differ in rule structure, not because the business intent was unclear.

Common causes include:

#### Different rule engines

Some platforms support detailed promotion logic natively. Others rely more heavily on apps, plugins, modules, or custom rules. Even when both platforms support promotions, the range of native conditions, exclusions, and combinability can differ.

#### Different eligibility models

A rule tied to products, categories, collections, customer segments, or order thresholds may not map cleanly if the target platform defines those conditions differently. This is especially important when promotions depend on category relationships, product grouping logic, or customer classification.

#### Different stacking behavior

One platform may let discounts combine more freely. Another may restrict how offers interact. That can change whether a promotion works alone, only in specific sequences, or not at all alongside other discounts.

#### Different shipping treatment

Free shipping and shipping-threshold promotions often behave differently across platforms. A store may preserve the headline offer while changing the exact circumstances in which it applies.

#### Different rounding and calculation order

A platform may calculate discounts before or after tax, distribute them differently across items, or round totals differently. Even small changes can affect customer-facing totals, reporting, and margin interpretation.

### Coupons depend on other store structures

Promotions do not operate in isolation.

They often depend on other structures already carrying meaning in the store:

* products
* categories
* customers or customer groups
* shipping logic
* tax logic
* extension-driven merchandising or pricing behavior

That dependency matters because a promotion can appear intact while the conditions it depends on have shifted. A category-based discount becomes less reliable if category structure changes. A customer-specific promotion becomes less reliable if segmentation changes. A cart threshold promotion becomes harder to interpret if line-level and order-level pricing logic is applied differently.

### Where extensions and custom pricing logic raise the risk

Many stores rely on more than native pricing and promotion tools.

Apps, plugins, modules, and custom logic may influence:

* advanced discount rules
* loyalty-based pricing
* customer-tier pricing
* bundle promotions
* subscription pricing
* shipping incentives
* regional pricing behavior
* automated merchandising tied to promotions

In those cases, the migration question is not only whether the code or discount record moves. The more important question is whether the target store can still reproduce the same commercial rule behavior and pricing outcome. Where important promotions depend on extension-driven logic, standard handling may preserve visible records without preserving the business logic that made the promotion work. In those situations, a Custom Job or Custom Migration Service may be the safer path.

### What merchants should define before execution

Before approving a full migration, the business should be able to describe which pricing and promotion outcomes must remain true after launch.

The most important questions are:

#### 1. Which promotions matter most commercially?

These are the offers that drive meaningful revenue, conversion, customer retention, or margin outcomes.

#### 2. Which rules depend on products, categories, or customer segmentation?

These rules usually carry more structural risk than simple fixed discounts.

#### 3. Which promotions combine with others?

Stacking behavior often exposes differences between promotion engines quickly.

#### 4. Which shipping-related incentives matter?

Free shipping, threshold-based offers, and shipping discounts often deserve their own review because they are handled differently across platforms.

#### 5. Which pricing outcomes depend on apps, modules, or custom logic?

This is where apparently familiar promotions often become less predictable after migration.

### What to validate first

Pricing and promotion logic should be validated through realistic carts, not by checking whether a code exists.

A practical first review should include:

* top-performing promotions
* promotions with product or category restrictions
* customer-group or segment-specific pricing scenarios
* threshold-based discounts
* stacked discount scenarios
* shipping-related promotions
* carts where tax treatment affects the expected total

The first questions to ask are:

* does the promotion apply to the right products or categories?
* does it exclude what should be excluded?
* do customer-specific conditions still behave correctly?
* does stacking work as intended?
* does shipping behavior remain consistent with the commercial offer?
* do totals still make sense at line level and order level?

A useful validation sample is usually representative rather than random. It should reflect the discount scenarios that matter most to real customers and real margin outcomes. A Demo Migration is often the fastest way to expose whether the target representation still supports those scenarios before the project scales further.

### When standard handling may not be enough

Not every store with discount rules needs bespoke handling. But some signals should raise the threshold for confidence.

Risk is higher when:

* promotions depend heavily on category or product eligibility
* customer groups or pricing tiers affect what different buyers should see
* stacked promotions are common
* shipping incentives are important to conversion
* tax interaction materially affects expected totals
* pricing or discount behavior depends on extensions or custom logic
* the target platform can only approximate the original rule set rather than represent it directly

In those situations, the real issue is not whether discount records can move. It is whether the target store can preserve the intended commercial behavior clearly enough through standard handling alone. If important pricing outcomes depend on non-standard rules, custom segmentation, or extension-driven logic, Managed Migration Service or Custom Migration Service may be the safer path, with Custom Jobs used where scoped adaptation is required.

### Conclusion

Promotion migration succeeds when commercial intent survives the platform change, not when coupon names simply reappear in the target store.

A discount can look familiar while behaving differently if eligibility rules, stacking logic, shipping treatment, or calculation order changes underneath it. That is why pricing and promotion logic should be judged by real cart outcomes, customer-facing totals, and rule accuracy, not only by whether codes and discount records exist after migration.

If your store depends on layered discount logic, customer-specific pricing, or promotion behavior shaped by apps or custom rules, use a Demo Migration to review representative carts early. Where the sample shows that standard handling preserves records but weakens pricing or promotion behavior, Live Chat can help determine whether Standard Migration Service remains suitable or whether Managed Migration Service, Custom Migration Service, or a Custom Job is the safer path.

### FAQs

<details>

<summary><strong>Why can a coupon code migrate and still stop working as expected?</strong></summary>

Because the code is only the trigger. The actual behavior depends on the rule behind it, including eligibility, exclusions, stacking, thresholds, and how the discount is applied. If the target platform represents those rules differently, the code can survive while the commercial result changes.

</details>

<details>

<summary><strong>What should be reviewed first when promotions matter to revenue?</strong></summary>

Start with the promotions that drive the most sales or customer response, especially those with category restrictions, customer-group logic, shipping incentives, or stacking behavior. Those scenarios reveal structural differences faster than simple one-code tests.

</details>

<details>

<summary><strong>Why do discount totals sometimes look similar but still create problems?</strong></summary>

Because the distribution of the discount can change even when the final total looks close. A platform may apply discounts at a different layer, round differently, or interact with tax and shipping rules in another order. That can affect reporting, margins, and customer expectations.

</details>

<details>

<summary><strong>Can customer groups or category relationships affect promotion migration outcomes?</strong></summary>

Yes. Many promotions depend on customer classification, category assignment, or product eligibility. If those underlying structures change, the promotion can become broader, narrower, or less predictable after migration.

</details>

<details>

<summary><strong>When is a Custom Job more likely to be necessary for pricing and promotions?</strong></summary>

Usually when important discount behavior depends on non-standard rules, extension-driven pricing logic, custom segmentation, or platform-specific rule structures that do not map cleanly through standard handling alone.

</details>
