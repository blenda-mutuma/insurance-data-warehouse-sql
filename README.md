# Insurance Data Warehouse: Profitability, Risk & Fraud

**SQL Server · dimensional modeling · ETL** 

## The business problem

Analytic Mutual Insurance writes homeowner and auto policies. Its policy, claims, and customer data lives in operational systems built to process transactions, not to answer questions across them, so management can't see which customers, regions, or policy types make or lose money.

## The solution: a data warehouse

**Design: a constellation (galaxy) schema**
- **Fact tables:** home premiums, auto premiums, claims, and property exposure.
- **Shared dimensions:** customer, policy, date, location, home, automobile, property type, claim type, and loss type.
- **Why it works:** because the dimensions are shared, every fact table can be analyzed across lines of business with the same definitions.

**ETL**
- Dimensions are loaded first, then facts.
- Primary and foreign key constraints enforce referential integrity, so analytical joins can be trusted.

## Analyses built on the warehouse

| Analysis | Question answered |
|---|---|
| Customer profitability | Which customers' claims exceed their premiums? |
| Regional underwriting | Which regions run a negative net margin and need a pricing review? |
| Claims by loss type | Which perils are high-frequency, and which are rare but severe (e.g. fire)? |
| Property exposure | Where is insured value concentrated? |
| Driving behavior vs. premium | Do telematics measures (speed, mileage, braking) line up with pricing? |
| Fraud screening | A SQL rule flags claims with a $0 reserve and $0 paid (filed but never processed) for investigation |

The project used realistic sample data to simulate operational loading, so the emphasis is on the design and the logic, not the specific figures.

## Files

| File | Contents |
|---|---|
| `docs/presentation.pdf` | Final presentation: schema diagram, ETL process, and insights |
| `sql/` | *Add the `CREATE TABLE`, `INSERT`, and analysis query scripts here* |

*Team: Blenda Mutuma, Dete Itai, Mo Kothawala, Tafadzwa.*
