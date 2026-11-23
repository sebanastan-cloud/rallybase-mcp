# Rallybase MCP server

Rallybase is a remote MCP server for US public government records. It lets an AI assistant look up who holds office, and read public data about the governments themselves, with the source and date on each row.

- **Endpoint:** `https://rallybase.org/mcp` (Streamable HTTP)
- **Auth:** OAuth 2.1, authorization code with PKCE. Sign in at rallybase.org/connect with a free Rallybase account and press Allow.
- **Docs:** https://rallybase.org/api/docs
- **Listed in:** the Claude connectors directory, LobeHub, the Official MCP Registry and Agensi (as a skill)

## Tools (16, all read-only)
| Tool | What it returns |
|---|---|
| `get_state_officials` | A state's U.S. senators and representatives, statewide officials, and legislators by chamber and district, with office phone, email and website |
| `lookup_officials` | County officers by state and county name |
| `get_official` | One county office by county FIPS and office key |
| `get_county` | One county by FIPS, with its coverage finding |
| `lookup_city` | A city's council and elected offices |
| `search_bills` | Federal and state bills saved by Rallybase, by title words or bill number |
| `get_coverage` | What Rallybase holds for a state |
| `get_ballot` | A state's upcoming elections, with the candidates and measures held |
| `get_registration_deadlines` | A state's next elections and their voter registration deadlines |
| `get_finance` | A county's, city's, school district's or state's revenue and spending, from the U.S. Census Bureau |
| `search_nonprofits` | Tax-exempt organisations in the IRS file, by EIN or by name in a state |
| `search_federal_register` | Recent Federal Register documents with agencies, comment deadlines and official-text links |
| `get_tax_rates` | Texas property tax rates for the taxing units in a county, or one unit, as the Texas Comptroller prints them |
| `get_county_labor_force` | A county's monthly labor force, employment and unemployment, from the Bureau of Labor Statistics |
| `search_water_systems` | Community water systems serving a county or state, or one system by EPA id, from EPA records |
| `search_federal_judges` | Federal judges by district court or state, from the Federal Judicial Center |

## How it answers
- Each row carries its source and the day it was read or recorded.
- Where Rallybase has not read a county or city, the answer says "not yet read". It never guesses.
- Questions are asked by name or code (state, county, city, FIPS, EIN), never by street address.
- Nothing is sent or changed. Office contacts only, never personal ones.
- Connector lookups count toward the same monthly allowance as the Rallybase API.

Rallybase is independent and nonpartisan, and it is not a government website. The server's source code is not public; this repository holds its public description.
