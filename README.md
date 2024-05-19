# gics-moodys-map

This repository seeks to create a baseline association between the Global Industry Classification Standard® ("GICS") maintained by MSCI and the Moody's 35 Industry Categories.

The goal of this project is not to provide an industry-standard mapping, but to provide a reasonable thought process as to how to derive such a mapping and to get a user 80.0% - 90.0% of the way to a usable product with some minor tuning for each end use case.

*If you have any comments, questions, or concerns, please use the GitHub Issues Tracker.*

#### **Description of Data:**

GICS industries are categorized into four categories:

| Level   | Level Name     | Example Name                  | Example Code |
|---------|----------------|-------------------------------|--------------|
| Level 1 | Sector         | Industrials                   | 20           |
| Level 2 | Industry Group | Capital Goods                 | 2010         |
| Level 3 | Industry       | Machinery                     | 201060       |
| Level 4 | Sub-Industry   | Agricultural & Farm Machinery | 20106015     |

Moody's industries have a flat structure:

| Industry              |
|-----------------------|
| Transportation: Cargo |

#### **Source Documents:**

|                                               |                                                                                                     |
|-------------------------------------------------------|:---------------:|
| MSCI Global Industry Classification Standard® |                     [Link](https://www.msci.com/index/methodology/latest/GICS)                      |
| Moody's 35 Industry Categories                | [Link](https://www.moodys.com/sites/products/ProductAttachments/MCO_35%20Industry%20Categories.pdf) |

#### **Disclaimer:**

> *(1) This repository is provided for illustrative purposes only. It is intended to demonstrate the translation mapping between GICS Industries and Moody's Industries and should not be relied upon for any other purpose. (2) Identification or classification of risk should be done on a per-investment basis. The translation map provided here may not accurately reflect the risk profile of individual investments or portfolios. (3) Users are advised not to rely on the information in this repository to assess risk for their own portfolios or managed portfolios. Each investment carries its own unique risks and considerations that should be evaluated independently. (4) The contents of this repository should not be used to make any investment decisions. Users should conduct thorough research and seek professional financial advice before making any investment decisions. (5) By accessing and using this repository, you agree that the information provided is for educational and / or informational purposes only, and you assume full responsibility for any actions taken based on the information herein.*

## Methodology & Rationale

The translation map attempts to best categorize the underlying risk with an associated industry in the majority of circumstances. Industry assignments were made with the following viewpoint:

> *If you were an investor looking at a portfolio and you were provided with a chart detailing the portfolio's investments by industry, what Industry would best describe the actual risk taken with each invested dollar?*

This is exemplified in the following mappings:

| GICS Sub-Industry (Level 4) | Ascribed Moody's Industry |
|-----------------------------|---------------------------|
| Hotel & Resort REITs        | Hotel, Gaming, & Leisure  |
| Retail REITs                | Retail                    |
| Telecom Tower REITs         | Telecommunications        |
| Heavy Electrical Equipment  | Utilities: Electric       |
| Highways & Railtracks       | Transportation: Cargo     |

In the example of the REITs, if there was a specific / specialized REIT that lent itself to a Moody's Category, it was assigned to the more specific industry than the simple *Fire: Real Estate* category as it better defines the risk. The argument could be made that the *Heavy Electrical Equipment* GICS sub-industry could translate to the Moody's *Capital Equipment* industry, however most "power generating" electrical equipment will be utilized in utilities, hence the ascribed *Utilities: Electric industry*.

### Problematic Industries:

The GICS *Industrial Conglomerates* industry has been ascribed "*NOT_APPLICABLE*" given there is no one-to-one translation of this industry. It is recommended to use the industry in which the conglomerate derives the largest portion of its revenue, margin, EBITDA, etc.

### Bug Fixes / Corrections:

The description of the Moody's Industry Category: *Fire: Real Estate* in the *.pdf* (accessed 2024-05-18) has the following description:

> *"mortgage finance, non REIT conduit and REIT"*

The "*m*" in *"mortgage*" has been capitalized in the *.csv* file as it is the only category with a starting lowercase description.
