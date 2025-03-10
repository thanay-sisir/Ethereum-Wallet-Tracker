# ETHEREUM TRANSACTION ANALYZER

This project develops an Ethereum blockchain analysis tool that retrieves and visualizes transaction history for a given wallet address using the Etherscan API. By integrating external and internal transaction data, the system tracks account balances over time and plots them with Matplotlib, providing clear insights into financial activity. While the tool efficiently processes up to 10,000 transactions, future enhancements aim to improve scalability and real-time data handling.

## METHODOLOGY

This project leverages the Etherscan API to fetch transaction data due to its accessibility and comprehensive blockchain coverage. The methodology focuses on the following steps:

1. **Transaction Retrieval**:
   - Fetches external transactions (`txlist`) and internal transactions (`txlistinternal`) for a specified Ethereum address.
   - Combines datasets and sorts by timestamp for chronological accuracy.

2. **Balance Calculation**:
   - Converts transaction values from wei to Ether (10^18 precision).
   - Accounts for gas fees (gas used × gas price) and transaction direction (incoming vs. outgoing) to compute real-time balance.

Key features analyzed include:
- Transaction timestamps
- Ether value transfers
- Gas costs
- Cumulative balance trends

Redundant API calls are minimized by setting appropriate `offset` and `page` parameters, optimizing data retrieval efficiency.

**Instructions to Follow for Proposed Implementation:**

- **API Configuration**: Securely store the `API_KEY` in an environment variable instead of hardcoding it in the script to enhance security.
- **Data Integration**: Ensure external and internal transaction lists are merged correctly by validating the `timeStamp` sorting logic in `get_transactions`.
- **Visualization**: Customize Matplotlib plot settings in the script to improve readability of balance trends.
- **Scalability**: Implement pagination handling to process beyond 10,000 transactions by iterating over multiple API calls with dynamic `page` increments.
- **Error Handling**: Add try-except blocks in `get_account_balance` and `get_transactions` to manage API rate limits or network failures gracefully.

## SAMPLE OUTPUT

OUTPUT: Represents a time-series plot of the wallet’s Ether balance, reflecting key features such as:
- Incoming transactions increasing the balance
- Outgoing transactions and gas fees decreasing the balance
- Historical trends over the retrieved transaction period

The plot is displayed using Matplotlib and can be saved in the same directory with a minor code adjustment 

![image](https://github.com/user-attachments/assets/4ba1f7a0-8935-48a3-b8b2-cfa888e5f005)


![image](https://github.com/user-attachments/assets/d62302df-b807-49a4-a12c-6567b579bdbb)


