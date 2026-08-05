# GOE

<p>Please review the following descriptions of each GOE API Endpoint to gain a comprehensive understanding of the methodology employed by each endpoint.</p> <section class="content-section"> <div> <h3> <div>Run Pipe</div> </h3> </div> <p>The <a href="#/http/api-endpoints/goe/run-pipe"><strong>Run Pipe API</strong></a> is the Goals Optimization Engine’s (GOE) <strong>core</strong> API. The API helps End Investors achieve their goals by creating a personalized asset allocation plan aimed at <strong>maximizing the chances of success</strong>. If the Platform Partner accepts GOE's recommendation, it will periodically reassess progress and adjust asset allocation to maintain the highest probability of achieving their goal. GOE stands out by reallocating assets based on probability rather than maintaining a fixed asset mix over the goal time period. Throughout the process, GOE provides a probability percentage to keep the Platform Partner informed and <strong>suggests additional recommendations</strong> to improve the probability of reaching the goal. GOE considers the End Investor’s<strong> risk tolerance</strong> to manage risk and may seek to reduce risk exposure by limiting equities based on the stated risk tolerance. GOE calculates a maximum probability percentage for the goal and assigns an initial asset allocation mix based on that probability. Depending on the <strong>Goal Priority</strong> label chosen, GOE may suggest changes to the goal details to improve the probability percentage. GOE uses <strong>Dynamic Probability Programming</strong> to determine the initial asset mix and ongoing changes, working backwards in time from a set endpoint to arrive at the optimal solution. GOE calculates the <strong>optimal portfolio</strong> needed today to achieve the goal, along with the probability of achieving that goal at any possible wealth level during the goal tenure. </p> </section> <section class="content-section"> <div> <h3> <div>Unified Portfolio Advice</div> </h3> </div> <p><a href="#/http/api-endpoints/goe/unified-portfolio-advice"><strong>Unified Portfolio Advice (UPA)</strong></a> is an API built on top of the Goals Optimization Engine (GOE), enabling an End Investor to have a <strong>single portfolio for a suite of goals</strong> which are combined to form a plan. The End Investor could be someone with single or multiple goals. Available as an optional feature, the key value proposition of UPA is housing the business logic that enables it to combine <strong>several goals</strong> into a <strong>single plan</strong>, leading to a unified or a single portfolio – which allows it to utilize additional services of FT or other partners. In addition to the core outputs that GOE provides, UPA allows the End Investor to reduce their goals (UPA provides <strong>“Save More Today”</strong> and <strong>“Save More In Future”</strong> recommendations).</p> </section> <section class="content-section"> <div> <h3> <div>Initial Wealth Splitter</div> </h3> </div> <p><a href="#/http/api-endpoints/goe/initial-wealth-splitter"><strong>Initial Wealth Splitter (IWS)</strong></a> is an API that builds on top of the Goals Optimization Engine (GOE) which is made available as an optional feature. With the objective of <strong>funding goals higher up in the pecking order</strong>, IWS is used to allocate <strong>initial wealth</strong> across <strong>multiple goals</strong>. Put simply, given a lump sum initial wealth and 2 or more goals with different goal priorities, IWS will allocate the initial wealth across the different goals such that the End Investor is starting off with the amount that is most appropriate for each goal. A typical use case of IWS is at the outset of a goals-based End Investor user journey. Usually, an End Investor is limited by the amount they can invest in <strong>multiple goals</strong>; IWS helps apportion the initial wealth as per the pecking order of the goals. </p> </section> <section class="content-section"> <div> <h3> <div>GOE Simulation Engine</div> </h3> </div> <p>Available as an optional feature, the Goals Optimization Engine with <a href="#/http/api-endpoints/goe/goe-simulation-engine"><strong>Simulation of Portfolios (GOE SIMPL)</strong></a> is an API built on top of the Goals Optimization Engine (GOE). This API includes algorithmic calculations to provide recommendations for a given portfolio allocation while considering the <strong>pre & post tax rates</strong> and different <strong>account combinations</strong>, assets held and held away, for an End Investor or a household. The API also computes Social Security and Required Minimum distributions. Furthermore, the API is equipped to handle both <strong>multi-participant & custom portfolios</strong>, which are portfolios where risk and return is specified by the Platform Partner. Platform Partners input tax rates directly into the tool, which will calculate the additional sum to be added to the final goal amount. While meeting the goal, withdrawals are tax-optimized, depleting taxable accounts before retirement accounts. Expected taxes are calculated based on the Platform Partner’s specified rates for each withdrawal. GOE SIMPL builds upon Unified Portfolio Advice (UPA), a feature of the existing core GOE platform, to consolidate multiple financial goals into a single plan. The tool then offsets the plan’s goals with any Social Security benefits, running 10,000 <strong>Monte Carlo simulations</strong> to estimate the probability of achieving the set financial goals.</p> </section> <section class="content-section"> <div> <h3> <div>Goal Calculator</div> </h3> </div> <p>Available as an optional feature, the <a href="#/http/api-endpoints/goe/goal-calculator"><strong>Goal Calculator API</strong></a> is an API built on top of the Goals Optimization Engine (GOE). The API uses the core GOE algorithm to arrive at a <strong>specific goal value</strong> given a set of goal parameters. Platform Partners can use existing payload structure from the Core GOE API. The Goal Calculator API will calculate the <strong>exact goal value</strong> that aligns with the <strong>target probability</strong> and goal priority given other goal parameters. </p> </section> <section class="content-section"> <div> <h3> <div>GOE for Taxes</div> </h3> </div> <p>Available as an optional feature, <a href="#/http/api-endpoints/goe/goe-for-taxes"><strong>GOE for Taxes (GOE TO)</strong></a> is an API built on top of the Goals Optimization Engine (GOE). GOE TO leverages the capabilities of Unified Portfolio Advice (UPA), another API in the GOE ecosystem, to generate <strong>optimal portfolio advice</strong> while accounting for <strong>future tax expenses</strong>. The logic relies upon the input of tax rates, effective & capital gains provided by the Platform Partner in the UI. GOE TO methodology employs UPA to combine goals for an End Investor into a single plan. UPA combines multiple goals into a single plan. The cashflows in the plan are then netted against <strong>Social Security</strong> (if any) to incorporate that cash flow. GOE TO will then convert the remaining goal amount into a <strong>“tax-aware” goal</strong>, a goal that, post taxes, seeks to achieve the highest probability of meeting the End Investor’s requirements. The “tax-aware” goal is, by construction, higher than the original amount specified by the Platform Partner, who is asked to specify goals in post-tax dollars. Recommendations are made if a goal's probability falls below the desired level, including <strong>“Save more today”</strong> and <strong>“Goal reduction”</strong>, sometimes eliminating lower priority goals altogether. </p> </section> <section class="content-section"> <div> <h3> <div>GOE with Annuities (Under Development)</div> </h3> </div> <p><a href="#/http/api-endpoints/goe/goe-with-annuities-under-development"><strong>GOE with Annuities</strong></a> is an API built on top of the Goals Optimization Engine (GOE). This API is for End Investors who are preparing for retirement, providing investment advice, <strong>guaranteed income allocation</strong> advice and spenddown advice post – retirement. This solution takes into account the End Investor’s investment horizon, investable assets, current guaranteed income, and other assets to create a financial plan that adapts over time. By recommending <strong>guaranteed income purchases</strong>, End Investors are provided a safety net - a guaranteed income source that <strong>covers fixed expenses</strong> throughout retirement. While guaranteed income offers stability, End Investors also maintain sufficient exposure to the capital markets. This allows for the potential to capture market upside while safe guarding against downturns. For End Investors interested in deferred income, the solution recommends staggered <strong>deferred annuity purchases</strong> during the pre-retirement accumulation phase. These deferred annuities accumulate income over time aligning with the End Investor’s goals. For End Investors in their post-retirement phase, the solution recommends <strong>immediate annuities</strong>. </p> </section> <section class="content-section"> <div ><h3><div>Advice Status (Under Development)</div></h3></div> <p>The <a href="#/http/api-endpoints/goe/advice-status-under-development"><strong>Advice Status API</strong></a> is leveraged by GOE to track the utilization of an End Investor’s goal lifecycle investment advice by Platform Partners. Each time a Platform Partner calls a GOE API, they receive a <strong>unique Advice ID</strong> in the respective response. On a regular basis, Platform Partners <strong>submit a list</strong> of these provided Advice IDs in a call to the <strong>Advice Status API</strong>. This submission includes the respective Advice IDs and the corresponding timestamps that correlate to the execution status: Completely Traded, Partially Traded, Final Proposal, Draft, and Test. GOE leverages this information to monitor the End Investor’s goal investment lifecycle.</p></section><section class="content-section"><div ><h3><div >Advice Lookup (Under Development)</div></h3></div><p>The <a href="#/http/api-endpoints/goe/advice-lookup-under-development"><strong>Advice Lookup</strong></a> endpoint allows Platform Partners to retrieve detailed information for a <strong>historical API request</strong> by providing an <strong>Advice ID</strong>. This endpoint returns the original request payload, APIresponse, and associated metadata such as ID, API endpoint invoked, and timestamp. It is intended to supportauditing, troubleshooting, and tracking usage of advice implemenation.</p></section><section class="content-section"><div><h3><div>Enhanced Wealth Splitter (Under Development)</div></h3></div><p><a href="#/http/api-endpoints/goe/goe-enhanced-initial-wealth-splitter-under-development"><strong>Enhanced Wealth Splitter (EWS)</strong></a> is an API built on top of the Goals Optimization Engine (GOE), and an evolution of the Initial Wealth Splitter API. Designed for End Investors managing multiple financial goals simultaneously, EWS intelligently distributes account balances and future contributions across goals with a single governing objective: <strong>fund higher-priority goals first</strong>. Goals are ranked by priority, tenure, and withdrawal schedule, and funded sequentially using a <strong>waterfall model</strong> — ensuring needs are secured before wants, and wants before wishes. EWS also respects <strong>goal-level funding constraints</strong> configured at the tenant level, ensuring that each goal draws from only eligible account types in the prescribed order. For instance, education goals draw from education accounts before brokerage, while retirement goals draw from brokerage before retirement accounts. EWS operates both at onboarding and at <strong>every subsequent reallocation</strong>, continuously adapting as the End Investor's financial picture evolves — <strong>redirecting freed-up resources</strong> from completed goals toward remaining ones. This dynamic, rules-driven engine gives Platform Partners a principled and transparent framework for managing complex, multi-goal portfolios across the full financial lifecycle.</p></section>


```python
goe_api = client.goe
```

## Class Name

`GoeApi`

## Methods

* [Run Pipe](../../doc/controllers/goe.md#run-pipe)
* [Unified Portfolio Advice](../../doc/controllers/goe.md#unified-portfolio-advice)
* [Initial Wealth Splitter](../../doc/controllers/goe.md#initial-wealth-splitter)
* [GOE Simulation Engine](../../doc/controllers/goe.md#goe-simulation-engine)
* [Goal Calculator](../../doc/controllers/goe.md#goal-calculator)
* [GOE for Taxes](../../doc/controllers/goe.md#goe-for-taxes)
* [GOE with Annuities Under Development](../../doc/controllers/goe.md#goe-with-annuities-under-development)
* [GOE Enhanced Initial Wealth Splitter Under Development](../../doc/controllers/goe.md#goe-enhanced-initial-wealth-splitter-under-development)
* [Advice Status Under Development](../../doc/controllers/goe.md#advice-status-under-development)
* [Advice Lookup Under Development](../../doc/controllers/goe.md#advice-lookup-under-development)


# Run Pipe

The <b>Run Pipe API</b> is the core of the Goals Optimization Engine (GOE), dynamically generating and adjusting personalized asset allocations using backward-looking <b>dynamic programming</b> to maximize goal success probability while factoring in risk tolerance, goal priority, and real-time progress.

```python
def run_pipe(self,
            body,
            version="4")
```

## Authentication

This endpoint requires [JWTBearer](../../doc/auth/oauth-2-bearer-token.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`RunPipeInputModel`](../../doc/models/run-pipe-input-model.md) | Body, Required | - |
| `version` | `str` | Header, Optional | **Default**: `"4"` |

## Response Type

**200**: Successful response

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`RunPipeResponseModelV4`](../../doc/models/run-pipe-response-model-v4.md).

## Example Usage

```python
body = RunPipeInputModel(
    is_new_goal_priority=True,
    is_new_investment_tenure=True,
    is_new_risk_profile=True,
    is_new_goal=True,
    get_path=True,
    reallocation_freq=ReallocationFreq.YEARLY,
    goal_amount=1000000,
    initial_investment=250000,
    current_wealth=250000,
    start_date='13-01-2025',
    end_date='10-10-2059',
    goal_priority=GoalPriority1.NEED,
    current_portfolio_id=None,
    infusions=[
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0
    ],
    risk_profile=RiskProfile5.AGGRESSIVE,
    scenario_type=ScenarioType4.REGULAR,
    infusion_type=InfusionType1.YEARLY,
    reallocate=True,
    cashflow_date='11-10-2025',
    curr_date='13-01-2025',
    current_age=39
)

version = '4'

result = goe_api.run_pipe(
    body,
    version=version
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | [`MessageException`](../../doc/models/message-exception.md) |
| 404 | Not Found | [`ValidationMessageOneException`](../../doc/models/validation-message-one-exception.md) |
| 500 | Internal Server Error | [`InternalServerMessageException`](../../doc/models/internal-server-message-exception.md) |


# Unified Portfolio Advice

<b>Unified Portfolio Advice (UPA)</b> is an API layer built on top of the Goals Optimization Engine (GOE) that consolidates <b>multiple financial goals</b> into a <b>single portfolio plan</b>, enabling integration with Platform Partner services, while also offering goal reduction recommendations to enhance plan success.

```python
def unified_portfolio_advice(self,
                            body,
                            detailed_response=None)
```

## Authentication

This endpoint requires [JWTBearer](../../doc/auth/oauth-2-bearer-token.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`UnifiedPortfolioAdviceInputModelV4`](../../doc/models/unified-portfolio-advice-input-model-v4.md) | Body, Required | - |
| `detailed_response` | `str` | Header, Optional | - |

## Response Type

**200**: Successful response

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`UpAv4ResponseModel`](../../doc/models/up-av-4-response-model.md).

## Example Usage

```python
body = UnifiedPortfolioAdviceInputModelV4(
    is_new_goal_priority=True,
    is_new_risk_profile=True,
    is_new_investment_tenure=True,
    is_new_goal=True,
    get_path=True,
    reallocation_freq=ReallocationFreq2.YEARLY,
    initial_investment=86000,
    current_wealth=None,
    current_portfolio_id=None,
    infusions=[
        0,
        4000,
        4000,
        4000,
        4000,
        4000,
        4000,
        4000,
        4000,
        4000,
        -21000,
        -19000,
        -75000,
        -23000,
        -23000,
        -23000
    ],
    risk_profile=RiskProfile6.AGGRESSIVE,
    infusion_type=Infusiontype5.YEARLY,
    goal_profile_list=[
        GoalProfile(
            goal_id='Goal1',
            goal_amt=[
                25000
            ],
            start_date='01-01-2021',
            end_date='01-01-2031',
            priority=Priority.NEED,
            scenario_type=Scenariotype2.REGULAR
        ),
        GoalProfile(
            goal_id='Goal2',
            goal_amt=[
                52000
            ],
            start_date='01-01-2021',
            end_date='01-01-2033',
            priority=Priority.NEED,
            scenario_type=Scenariotype2.REGULAR
        ),
        GoalProfile(
            goal_id='Goal3',
            goal_amt=[
                2000,
                2000,
                2000,
                2000,
                2000,
                2000,
                2000,
                2000,
                2000,
                2000,
                2000,
                2000,
                2000,
                2000,
                2000
            ],
            start_date='01-01-2022',
            end_date='01-01-2036',
            priority=Priority.NEED,
            scenario_type=Scenariotype2.RETIREMENT
        ),
        GoalProfile(
            goal_id='Goal4',
            goal_amt=[
                21000,
                21000,
                21000,
                21000,
                21000
            ],
            start_date='01-01-2032',
            end_date='01-01-2036',
            priority=Priority.NEED,
            scenario_type=Scenariotype2.RETIREMENT
        )
    ],
    cashflow_date='01-01-2021',
    curr_date='04-01-2021',
    calibrate_goal_rec=True
)

result = goe_api.unified_portfolio_advice(body)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | [`ValidationMessageOneException`](../../doc/models/validation-message-one-exception.md) |
| 404 | Not Found | [`MessageException`](../../doc/models/message-exception.md) |
| 500 | Internal Server Error | [`InternalServerMessageException`](../../doc/models/internal-server-message-exception.md) |


# Initial Wealth Splitter

<b>Initial Wealth Splitter (IWS)</b> is an optional API built on top of GOE that allocates an <b>End Investor’s lump-sum</b> initial wealth across <b>multiple goals</b> based on their priority, ensuring higher-priority goals are funded first and transparently displaying the prioritization logic to Platform Partners.

```python
def initial_wealth_splitter(self,
                           body)
```

## Authentication

This endpoint requires [JWTBearer](../../doc/auth/oauth-2-bearer-token.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`WealthSplitterInputModel`](../../doc/models/wealth-splitter-input-model.md) | Body, Required | - |

## Response Type

**200**: Successful response

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`WealthSplitterOutputModel`](../../doc/models/wealth-splitter-output-model.md).

## Example Usage

```python
body = WealthSplitterInputModel(
    start_date='1-01-2020',
    risk_profile=RiskProfile8.CONSERVATIVE,
    goal_profile_list=[
        GoalProfileListWealthSplitterModel(
            goal_id='Goal_1',
            goal_value=1000000,
            purpose='Saving',
            curr_wealth=141412,
            goal_priority=WeathSplitterGoalPriorityAttribute.NEED,
            cashflow_type='monthly',
            cashflow=[
                0,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                400,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                -15000,
                0
            ],
            end_date='10-10-2080',
            scenario_type=ScenarioType3.RETIREMENT,
            cashflow_date='15-06-2020',
            additional_properties={
                'goal_priority_prob': jsonpickle.decode('0.85')
            }
        ),
        GoalProfileListWealthSplitterModel(
            goal_id='Goal_2',
            goal_value=1000000,
            purpose='Fixed',
            curr_wealth=897494,
            goal_priority=WeathSplitterGoalPriorityAttribute.DREAM,
            cashflow_type='yearly',
            cashflow=[
                0,
                4000,
                -30000,
                0
            ],
            end_date='10-10-2023',
            scenario_type=ScenarioType3.RETIREMENT,
            cashflow_date='11-10-2020',
            additional_properties={
                'goal_priority_prob': jsonpickle.decode('0.5')
            }
        )
    ],
    curr_date='13-01-2021'
)

result = goe_api.initial_wealth_splitter(body)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | [`ValidationMessageOneException`](../../doc/models/validation-message-one-exception.md) |
| 404 | Not Found | [`MessageException`](../../doc/models/message-exception.md) |
| 500 | Internal Server Error | [`InternalServerMessageException`](../../doc/models/internal-server-message-exception.md) |


# GOE Simulation Engine

<b>GOE SIMPL</b> is an advanced API built on the Goals Optimization Engine that simulates portfolio outcomes using <b>tax-aware logic</b>, Social Security offsets, and <b>Monte Carlo</b> simulations to optimize multi-goal financial plans for individuals or households, including support for custom portfolios and pre/post-tax account structures.

```python
def goe_simulation_engine(self,
                         body)
```

## Authentication

This endpoint requires [JWTBearer](../../doc/auth/oauth-2-bearer-token.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`GoeSimulationEngineInputModel`](../../doc/models/goe-simulation-engine-input-model.md) | Body, Required | - |

## Response Type

**200**: Successful response

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`GoeSimulationEngineOutputModel`](../../doc/models/goe-simulation-engine-output-model.md).

## Example Usage

```python
body = GoeSimulationEngineInputModel(
    reallocate=False,
    current_portfolio_id=None,
    risk_profile=RiskProfile3.AGGRESSIVE,
    is_new_risk_profile=False,
    infusion_type=InfusionType2.YEARLY,
    tax_rates=TaxRates2(
        ltcg_pre_retirement=0.15,
        ltcg_post_retirement=0.1,
        etr_pre_retirement=0.15,
        etr_post_retirement=0.2
    ),
    household=Household2(
        household_id='1',
        member_list=[
            Member(
                member_type=MemberType1.PRIMARY,
                member_id='6c60b501-8957-4393-9323-1dbf6195a00f',
                dob='01-1980',
                current_age=45,
                retirement_age=65,
                current_salary=1,
                social_security_start_age=65,
                existing_monthly_social_security_amount=51,
                additional_properties={
                    'lifeExpectancy': jsonpickle.decode('93')
                }
            )
        ],
        state_of_residence='TX'
    ),
    accounts=[
        Account(
            account_id='81571',
            taxability_type='T',
            member_i_ds=[
                '6c60b501-8957-4393-9323-1dbf6195a00f'
            ],
            current_balance=20000,
            current_holdings=[
                Category(
                    category_name='CASH',
                    category_id='10',
                    category_price=1,
                    quantity=20000,
                    cost_basis=20000
                )
            ],
            cashflow_details=CashflowDetails2(
                start_date='02-05-2025',
                end_date='02-05-2045',
                cashflow_amt=[
                    0,
                    0,
                    0,
                    0,
                    0,
                    0,
                    0,
                    0,
                    0,
                    0,
                    0,
                    0,
                    0,
                    0,
                    0,
                    0,
                    0,
                    0,
                    0,
                    0,
                    0
                ]
            )
        )
    ],
    goal_profile_list=[
        GoalProfileSimulationEngine(
            goal_id='39643636326436662d633738642d346230652d386136302d353162363338656162396366',
            start_date='02-05-2045',
            end_date='02-05-2073',
            priority=Priority2.NEED,
            goal_purpose='non-education',
            goal_amt=[
                60000,
                60000,
                60000,
                60000,
                60000,
                60000,
                60000,
                60000,
                60000,
                60000,
                60000,
                60000,
                60000,
                60000,
                60000,
                60000,
                60000,
                60000,
                60000,
                60000,
                60000,
                60000,
                60000,
                60000,
                60000,
                60000,
                60000,
                60000,
                60000
            ],
            scenario_type='retirement'
        )
    ],
    is_new_goal_priority=False,
    curr_date='02-05-2025',
    compute_social_security=False,
    use_social_security_for_goals=True,
    cashflow_date='02-05-2025',
    is_new_investment_tenure=False,
    is_new_goal=False,
    cola_rate=0,
    target_portfolio=TargetPortfolio2(
        mean_return=0.032,
        standard_deviation=0.006
    )
)

result = goe_api.goe_simulation_engine(body)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | Not Found | [`MessageException`](../../doc/models/message-exception.md) |
| 500 | Internal Server Error | [`InternalServerMessageGeneralException`](../../doc/models/internal-server-message-general-exception.md) |


# Goal Calculator

The <b>Goal Calculator API</b> is a GOE-based tool that computes a <b>precise goal value</b> aligned with a <b>target probability</b> and goal priority using the core GOE algorithm and existing payload structures.

```python
def goal_calculator(self,
                   body)
```

## Authentication

This endpoint requires [JWTBearer](../../doc/auth/oauth-2-bearer-token.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`GoalCalculatorInputModel`](../../doc/models/goal-calculator-input-model.md) | Body, Required | - |

## Response Type

**200**: Successful Response

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`GoalCalculatorOutputModel`](../../doc/models/goal-calculator-output-model.md).

## Example Usage

```python
body = GoalCalculatorInputModel(
    is_new_goal=True,
    is_new_risk_profile=True,
    is_new_investment_tenure=True,
    is_new_goal_priority=True,
    reallocation_freq=ReallocationFreq.YEARLY,
    get_path=False,
    current_portfolio_id=None,
    scenario_type=ScenarioType1.RETIREMENT,
    risk_profile=RiskProfile1.CONSERVATIVE,
    initial_investment=941897,
    current_wealth=941897,
    goal_priority=GoalCalculatorGoalPriorityAttribute.NEED,
    goal_amount=0,
    start_date='01-01-2020',
    end_date='10-10-2023',
    infusion_type=InfusionType1.YEARLY,
    infusions=[
        0,
        4000,
        4000,
        -1,
        0
    ],
    reallocate=True,
    curr_date='13-01-2021',
    cashflow_date='25-01-2020',
    current_age=15,
    retirement_age=60
)

result = goe_api.goal_calculator(body)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | [`ValidationMessageOneException`](../../doc/models/validation-message-one-exception.md) |
| 404 | Not Found | [`MessageException`](../../doc/models/message-exception.md) |
| 500 | Internal Server Error | [`InternalServerMessageException`](../../doc/models/internal-server-message-exception.md) |


# GOE for Taxes

<b>GOE for Taxes (GOE TO)</b> is a <b>tax-aware</b> API built on the Goals Optimization Engine and Unified Portfolio Advice that <b>optimizes asset allocation</b> and generates trade recommendations, adjusting goals and cashflows to maximize post-tax goal success probability through dynamic planning and Social Security offsets.

```python
def goe_for_taxes(self,
                 body)
```

## Authentication

This endpoint requires [JWTBearer](../../doc/auth/oauth-2-bearer-token.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`GoeForTaxesInputModel`](../../doc/models/goe-for-taxes-input-model.md) | Body, Required | - |

## Response Type

**200**: Successful response

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`GoeForTaxesOutputModel`](../../doc/models/goe-for-taxes-output-model.md).

## Example Usage

```python
body = GoeForTaxesInputModel(
    reallocate=False,
    is_new_risk_profile=False,
    is_new_investment_tenure=False,
    is_new_goal_priority=False,
    is_new_goal=False,
    get_path=True,
    current_portfolio_id=None,
    risk_profile=RiskProfile2.AGGRESSIVE,
    infusion_type=InfusionType2.YEARLY,
    tax_rates=TaxRatesDic2(
        ltcg_pre_retirement=0.15,
        ltcg_post_retirement=0.1,
        etr_pre_retirement=0.15,
        etr_post_retirement=0.2
    ),
    household=HouseholdGoeForTaxesObj2(
        household_id='1',
        member_list=[
            MemberGoeForTaxesObj(
                member_type=MemberType.PRIMARY,
                member_id='eff63fdb-1ed8-41be-a0f8-7788fdac728c',
                dob='02-1959',
                current_age=66,
                retirement_age=93,
                current_salary=400,
                social_security_start_age=65,
                existing_monthly_social_security_amount=10,
                additional_properties={
                    'lifeExpectancy': jsonpickle.decode('93')
                }
            )
        ],
        state_of_residence='KS'
    ),
    accounts=[
        GoeToAccountAttr(
            account_id='dbcd5e3d-55fb-45f6-a654-d720f056a071',
            taxability_type='D',
            member_i_ds=[
                'eff63fdb-1ed8-41be-a0f8-7788fdac728c'
            ],
            current_balance=2,
            current_holdings=[
                GoeToCategory(
                    category_name='CASH',
                    category_id='10',
                    category_price=1,
                    quantity=2,
                    cost_basis=2
                )
            ],
            cashflow_details=GoeToCashflowDetails2(
                start_date='02-05-2025',
                end_date='02-05-2051',
                cashflow_amt=[
                    2500,
                    2575,
                    2652,
                    2732,
                    2814,
                    2898,
                    2985,
                    3075,
                    3167,
                    3262,
                    3360,
                    3461,
                    3564,
                    3671,
                    3781,
                    3895,
                    4012,
                    4132,
                    4256,
                    4384,
                    4515,
                    4651,
                    4790,
                    4934,
                    5082,
                    5234,
                    5391
                ]
            ),
            account_type='IRA'
        )
    ],
    goal_profile_list=[
        GoalProfileGoeForTaxesAttr(
            goal_id='39623865346539642d366234362d343639362d393332332d356134356563653030336130',
            start_date='02-05-2052',
            end_date='02-05-2052',
            priority=Priority1.NEED,
            goal_purpose='non-education',
            goal_amt=[
                666
            ],
            scenario_type='retirement'
        )
    ],
    is_near_term_volatility=False,
    curr_date='02-05-2025',
    compute_social_security=False,
    use_social_security_for_goals=True,
    cashflow_date='02-05-2025',
    cola_rate=0.03
)

result = goe_api.goe_for_taxes(body)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | Not Found | [`MessageException`](../../doc/models/message-exception.md) |
| 500 | Internal Server Error | [`InternalServerMessageGeneralException`](../../doc/models/internal-server-message-general-exception.md) |


# GOE with Annuities Under Development

<b>GOE with Annuities</b> is a retirement-focused API built on the Goals Optimization Engine that provides adaptive financial planning by recommending deferred and immediate <b>annuity purchases</b> to ensure guaranteed income for fixed expenses, while maintaining market exposure to support long-term growth.

```python
def goe_with_annuities_under_development(self,
                                        body)
```

## Authentication

This endpoint requires [JWTBearer](../../doc/auth/oauth-2-bearer-token.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`GoeWithAnnuitiesInputModel`](../../doc/models/goe-with-annuities-input-model.md) | Body, Required | - |

## Response Type

**200**: Successful response

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`AnnuitiesResponseModel`](../../doc/models/annuities-response-model.md).

## Example Usage

```python
body = GoeWithAnnuitiesInputModel(
    include_annuities=True,
    date_of_birth='01-01-1981',
    retirement_age=61,
    drawdown_age=66,
    planning_age=82,
    current_salary=350000,
    total_account_balance=1260000,
    periodic_contributions=8750,
    contribution_freq=ContributionFreq.MONTHLY,
    outside_assets=210000,
    current_portfolio_id=None,
    current_date='01-01-2024',
    risk_profile=RiskProfile4.AGGRESSIVE,
    other_guaranteed_income=100,
    reallocate=False,
    user_input_update=False,
    annuity_price=[
        AnnuityPrice(
            age=43,
            value=[
                Value(
                    year=2024,
                    rate=120
                )
            ]
        ),
        AnnuityPrice(
            age=44,
            value=[
                Value(
                    year=2025,
                    rate=115
                )
            ]
        ),
        AnnuityPrice(
            age=45,
            value=[
                Value(
                    year=2026,
                    rate=110
                )
            ]
        ),
        AnnuityPrice(
            age=46,
            value=[
                Value(
                    year=2027,
                    rate=105
                )
            ]
        ),
        AnnuityPrice(
            age=47,
            value=[
                Value(
                    year=2028,
                    rate=100
                )
            ]
        ),
        AnnuityPrice(
            age=48,
            value=[
                Value(
                    year=2029,
                    rate=95
                )
            ]
        ),
        AnnuityPrice(
            age=49,
            value=[
                Value(
                    year=2030,
                    rate=90
                )
            ]
        ),
        AnnuityPrice(
            age=50,
            value=[
                Value(
                    year=2031,
                    rate=85
                )
            ]
        ),
        AnnuityPrice(
            age=51,
            value=[
                Value(
                    year=2032,
                    rate=80
                )
            ]
        ),
        AnnuityPrice(
            age=52,
            value=[
                Value(
                    year=2033,
                    rate=75
                )
            ]
        ),
        AnnuityPrice(
            age=53,
            value=[
                Value(
                    year=2034,
                    rate=70
                )
            ]
        ),
        AnnuityPrice(
            age=54,
            value=[
                Value(
                    year=2035,
                    rate=65
                )
            ]
        ),
        AnnuityPrice(
            age=55,
            value=[
                Value(
                    year=2036,
                    rate=64
                )
            ]
        ),
        AnnuityPrice(
            age=56,
            value=[
                Value(
                    year=2037,
                    rate=63
                )
            ]
        ),
        AnnuityPrice(
            age=57,
            value=[
                Value(
                    year=2038,
                    rate=62
                )
            ]
        ),
        AnnuityPrice(
            age=58,
            value=[
                Value(
                    year=2039,
                    rate=61
                )
            ]
        ),
        AnnuityPrice(
            age=59,
            value=[
                Value(
                    year=2040,
                    rate=60
                )
            ]
        ),
        AnnuityPrice(
            age=60,
            value=[
                Value(
                    year=2041,
                    rate=59
                )
            ]
        ),
        AnnuityPrice(
            age=61,
            value=[
                Value(
                    year=2042,
                    rate=58
                )
            ]
        )
    ],
    current_annuity_balance=35000,
    retirement_income_goal=25000,
    drawdown_age_ss=64,
    income_from_ss=10000,
    other_income=25000,
    calculate_retirement_income_goal=False,
    additional_properties={
        'balanceProportion': jsonpickle.decode('0.1'),
        'currAge': jsonpickle.decode('43'),
        'jobTenure': jsonpickle.decode('31'),
        'maritalStatus': jsonpickle.decode('"married"'),
        'spousalSalary': jsonpickle.decode('250000')
    }
)

result = goe_api.goe_with_annuities_under_development(body)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | [`ValidationMessageOneException`](../../doc/models/validation-message-one-exception.md) |
| 404 | Not Found | [`MessageException`](../../doc/models/message-exception.md) |
| 500 | Internal Server Error | [`InternalServerMessageException`](../../doc/models/internal-server-message-exception.md) |


# GOE Enhanced Initial Wealth Splitter Under Development

<b>Enhanced Wealth Splitter (EWS)</b> is an evolution of the Initial Wealth Splitter API, both built on top of the core GOE Engine. Given a pool of accounts and future contributions, EWS <b>optimally apportions available balances</b> across <b>multiple End Investor goals</b> — while ensuring, higher-ranked goals are fully funded before resources flow to lower-priority ones.

```python
def goe_enhanced_initial_wealth_splitter_under_development(self,
                                                          body)
```

## Authentication

This endpoint requires [JWTBearer](../../doc/auth/oauth-2-bearer-token.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`EwsInputModel`](../../doc/models/ews-input-model.md) | Body, Required | - |

## Response Type

**200**: Successful response

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`EwsResponseModel`](../../doc/models/ews-response-model.md).

## Example Usage

```python
body = EwsInputModel(
    goal_profile=EwsGoalProfile(
        goal_profile_list=[
            EwsGoalProfileItem(
                goal_amount=600000,
                goal_start_date='01-01-2028',
                goal_end_date='01-12-2030',
                goal_id='G_1',
                goal_priority=Goalpriority.NEED,
                scenario_type=Scenariotype.RETIREMENT,
                goal_frequency=Goalfrequency.YEARLY,
                bequest_amount=0,
                goal_name='Retirement Living Expenses',
                goal_rank=1,
                current_portfolio_id=None,
                portfolio_set_label='default',
                account_mapping=[
                    EwsAccountMappingItem(
                        funding_sequence=1,
                        account_id='A_1'
                    )
                ]
            ),
            EwsGoalProfileItem(
                goal_amount=550000,
                goal_start_date='01-12-2030',
                goal_end_date='01-12-2030',
                goal_id='G_2',
                goal_priority=Goalpriority.WANT,
                scenario_type=Scenariotype.REGULAR,
                goal_frequency=Goalfrequency.YEARLY,
                bequest_amount=0,
                goal_name='Child\'s College Fund',
                goal_rank=2,
                current_portfolio_id=None,
                portfolio_set_label='default',
                account_mapping=[
                    EwsAccountMappingItem(
                        funding_sequence=1,
                        account_id='A_1'
                    )
                ]
            )
        ]
    ),
    investment_details=EwsInvestmentDetails2(
        current_age=45,
        investment_list=[
            EwsInvestmentItem(
                investment_id='A_1',
                lumpsum_amount=160000,
                account_infusion=[
                    EwsAccountInfusionItem(
                        date='08-01-2026',
                        value=0
                    ),
                    EwsAccountInfusionItem(
                        date='01-01-2027',
                        value=180000
                    ),
                    EwsAccountInfusionItem(
                        date='01-01-2028',
                        value=180000
                    ),
                    EwsAccountInfusionItem(
                        date='01-01-2029',
                        value=180000
                    ),
                    EwsAccountInfusionItem(
                        date='01-01-2030',
                        value=180000
                    )
                ],
                end_date='01-01-2030',
                infusion_type=Infusiontype.YEARLY,
                funding_type='incomeSources'
            )
        ],
        curr_date='08-01-2026'
    ),
    risk_profile=Riskprofile.AGGRESSIVE
)

result = goe_api.goe_enhanced_initial_wealth_splitter_under_development(body)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | [`ValidationMessageOneException`](../../doc/models/validation-message-one-exception.md) |
| 404 | Not Found | [`MessageException`](../../doc/models/message-exception.md) |
| 500 | Internal Server Error | [`InternalServerMessageException`](../../doc/models/internal-server-message-exception.md) |


# Advice Status Under Development

The <b>Advice Status API</b> is utilized by Platform Partners to provide GOE with a list of unique Advice IDs with their corresponding execution status. GOE leverages this information to monitor the End Investor’s goal investment lifecycle.

```python
def advice_status_under_development(self,
                                   body)
```

## Authentication

This endpoint requires [JWTBearer](../../doc/auth/oauth-2-bearer-token.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`AdvicePayload`](../../doc/models/advice-payload.md) | Body, Required | - |

## Response Type

**200**: Successful response

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`BulkUpsertAdvice`](../../doc/models/bulk-upsert-advice.md).

## Example Usage

```python
body = AdvicePayload(
    completely_traded=[
        CompletelyTradedEntry(
            advice_id=[
                '68cb7e2eb6434ec5aeb0e7d721e48e9e'
            ],
            date='20250722T145113Z'
        ),
        CompletelyTradedEntry(
            advice_id=[
                'd9b057db6c3c4814968edfa1708f3924',
                '5ede8559226b4b688c654aac75a59a12',
                'ca646c91dcee4ff58ce2a989f0240451'
            ],
            date='20250722T145113Z'
        )
    ],
    draft=[
        DraftEntry(
            advice_id='0b0d0b9afa5940a188ff6c1f65b887f9'
        )
    ],
    test=[
        TestEntry(
            advice_id=[
                '4c5c903f955d402f9cb0aa5029c60267',
                'test999-888888'
            ],
            date='20251130T145113Z'
        )
    ]
)

result = goe_api.advice_status_under_development(body)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Example Response *(as JSON)*

```json
{
  "status": "success",
  "updated": [
    "68cb7e2eb6434ec5aeb0e7d721e48e9e",
    "d9b057db6c3c4814968edfa1708f3924",
    "5ede8559226b4b688c654aac75a59a12",
    "ca646c91dcee4ff58ce2a989f0240451",
    "d43eaa626d53431695275bbe52a9e7c7",
    "38818da94653452aaa0f16d730b9de62",
    "89a8a5ade9bf433180e21b8b8369df56",
    "0b0d0b9afa5940a188ff6c1f65b887f9"
  ],
  "failed": [],
  "invalid_ids": [],
  "total_processed": 8,
  "chunks_processed": 1,
  "message": "success",
  "adviceID": "902cd72bbe644001a5606cb0d83a3982"
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | [`ValidationMessageOneException`](../../doc/models/validation-message-one-exception.md) |
| 500 | Internal Server Error | [`InternalServerMessageGeneralException`](../../doc/models/internal-server-message-general-exception.md) |


# Advice Lookup Under Development

The <b>Advice Lookup</b> endpoint returns request, response, and related metadata for a historical API request when provided with an Advice ID. Due to API security constraints, clients can only retrieve data for Advice IDs that they originally generated. As a result, the sample payload is only valid when used with the default GOE Developer Hub ID.

```python
def advice_lookup_under_development(self,
                                   body)
```

## Authentication

This endpoint requires [JWTBearer](../../doc/auth/oauth-2-bearer-token.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`AdviceLookupRequest`](../../doc/models/advice-lookup-request.md) | Body, Required | - |

## Response Type

**200**: Successful response with historical audit data

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`AdviceLookupResponse`](../../doc/models/advice-lookup-response.md).

## Example Usage

```python
body = AdviceLookupRequest(
    advice_id='e0623d22d2d843ee94634438e64375b4'
)

result = goe_api.advice_lookup_under_development(body)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Example Response *(as JSON)*

```json
{
  "statusCode": 200,
  "message": "Success",
  "body": {
    "adviceId": "e0623d22d2d843ee94634438e64375b4",
    "createdAt": "2025-12-16T19:37:07.368138",
    "userEmail": "goe-api-portal@franklintempleton.com",
    "apiName": "/v3/runPipe",
    "payload": {
      "isNewRiskProfile": true,
      "isNewInvestmentTenure": true,
      "isNewGoalPriority": true,
      "isNewGoal": true,
      "cashflowDate": "01-01-2028",
      "getPath": true,
      "reallocationFreq": "yearly",
      "goalAmount": 13000,
      "initialInvestment": 11000,
      "currentWealth": 11000,
      "startDate": "01-10-2024",
      "endDate": "01-01-2028",
      "goalPriority": "Need",
      "infusions": [
        0,
        100,
        100,
        100,
        0
      ],
      "riskProfile": "aggressive",
      "scenarioType": "regular",
      "infusionType": "yearly",
      "currDate": "01-10-2024",
      "reallocate": false,
      "requiredDataAvailable": true
    },
    "response": {
      "statusCode": 200,
      "message": "Success",
      "body": {
        "analysisReport": {
          "currentGoalProbability": 0.5842,
          "pDeltaCurrentGoalProbability": 0.5386,
          "recommendedPortfolioId": 16,
          "meetGoalPriority": false,
          "isGoalRealistic": true,
          "oneTimeTopUp": 1458,
          "yearlyTopUpAccumulation": 490,
          "monthlyTopUpAccumulation": 0,
          "yearlyTopUpDecumulation": 0,
          "monthlyTopUpDecumulation": 0,
          "recommendedTenure": "Goal probability at T+2 years : 76% ; Goal probability at T+4 years : 86%",
          "bankruptcyMsg": "NA"
        },
        "pathReport": {
          "portfolioPath": [
            16,
            16,
            16,
            16
          ],
          "wealthPath": {
            "default": [
              11000,
              11238,
              11338,
              11438,
              11438
            ],
            "pessimistic": [
              11000,
              11238,
              11338,
              11438,
              11438
            ],
            "optimistic": [
              11000,
              12405,
              14036,
              14932,
              15589
            ],
            "defaultPercentile": "85%",
            "pessimisticPercentile": "90%",
            "optimisticPercentile": "10%"
          }
        }
      },
      "adviceID": "e0623d22d2d843ee94634438e64375b4"
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | [`ValidationMessageOneException`](../../doc/models/validation-message-one-exception.md) |
| 500 | Internal Server Error | [`InternalServerMessageGeneralException`](../../doc/models/internal-server-message-general-exception.md) |

