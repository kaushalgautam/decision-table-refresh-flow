# Salesforce Decision Table Refresh Flow

A Screen Flow that enables on-demand decision table refreshes directly from your Salesforce interface.

## Overview

This screen flow provides a convenient way to refresh Salesforce decision tables without navigating through Setup menus. The flow accepts a decision table name as input and offers options for both incremental and full refresh operations, while displaying key metrics about the decision table.

![Decision Table Refresh Flow Screenshot - Main Screen](INSERT_SCREENSHOT_HERE)

## Features

- **Contextual Refreshes**: Embed the flow anywhere in your Salesforce environment - Lightning app pages, record pages, home pages, etc.
- **Multiple Refresh Options**: Choose between incremental or full refresh operations.
- **Key Metrics Display**: View important decision table information:
    - Decision table name
    - Current refresh status (color-coded)
    - Last refresh date and time
    - Last incremental refresh date and time
- **Quota Monitoring**: Tracks full refreshes performed within the last hour (helping manage the 20 per hour limit)

## Installation

1. Deploy the flow XML to your Salesforce org with your tool of choice.
2. Configure the flow to accept the appropriate decision table developer name.
3. Add the flow to your desired Lightning pages. You can also use an LWC to wrap it in a button so that it does not launch by default when the page loads (I will release a small wrapper for this soon).

#### Input Variables

| Variable Name              | Data Type | Description                                    |
| -------------------------- | --------- | ---------------------------------------------- |
| DecisionTableDeveloperName | String    | DeveloperName of the decision table to refresh |

Security Consideration: The flow runs in System Mode without sharing, so ensure appropriate access controls.

## Limitations

- Full refresh can be used a maximum of 20 times in an hour - this will be indicated in the first screen of the flow.
- The flow requires appropriate permissions to access decision table metadata.

## Contact

For questions, issues, or enhancement requests, please open an issue and I'll take a look.

## License

This project is licensed under the MIT License - see the LICENSE file for details.
