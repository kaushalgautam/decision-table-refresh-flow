# Salesforce Decision Table Refresh Flow

A Screen Flow that enables on-demand decision table refreshes directly from your Salesforce interface.

## Overview

This screen flow provides a convenient way to refresh Salesforce decision tables without navigating through Setup menus. The flow accepts a decision table name as input and offers options for both incremental and full refresh operations, while displaying key metrics about the decision table.

![Decision Table Refresh Flow Screenshot - Main Screen](https://github.com/user-attachments/assets/fdb07477-abbd-4627-8b30-d681cdc4ab66)

Pin #1 - Shows full refreshes done in the last hour (Incremental refreshes do not count)

Pin #2 - You can select the type of refresh you want to do before proceeding. 

![Decision Table Refresh Flow Screenshot - Waiting Screen](https://github.com/user-attachments/assets/90ec59e3-b4bd-4f3a-a8d9-cedbfabcc38b)

Once you click on Refresh Table, you are taken to this intermediate screen. You can press the Check Refresh Status button in a second or two (so that we can fetch the updated data) to proceed to the next screen.

![Decision Table Refresh Flow Screenshot - Result Screen](https://github.com/user-attachments/assets/726cdc16-4eb5-446b-b34f-f03ffc2a043a)

This screen shows you the status of your refresh. 

Pin #1 - Shows refresh status of the table

Pin #2 - Tip: If the status is still In Progress (it will be, because it takes some time), and you want to refresh it, you can do so. Just click on Previous, go to the waiting screen, and then click the Check Refresh Status button again to refresh the data. 


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

For questions, issues, or enhancement requests, please open an issue, and I'll take a look.

## License

This project is licensed under the MIT License - see the LICENSE file for details.
